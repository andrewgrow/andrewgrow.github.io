---
layout: single
title:  "Анимация перехода от списка к Activity"
author_profile: true
author: Andrew
categories: 
    - android
tags: 
    - android
    - useful
    - development
    - programming
---

## Как настроить анимацию перехода между списком и новой активностью в Android

![Android Transition Animation](https://github.com/andrewgrow/AndroidTransitionAnimation/raw/master/transition-animation.gif)

Этот небольшой проект поможет создать свою собственную анимацию перехода между элементом списка и 
новой активностью с помощью [Shared Elements](https://developer.android.com/training/transitions/start-activity)

Полностью код находится [на github](https://github.com/andrewgrow/AndroidTransitionAnimation/), а здесь я лишь расскажу 
основные момент, которые могут быть непонятны при создании перехода.

### Создание каркаса приложения.

Я использую 2 активности для отображения перехода. 

*MainActivity* - основная активность, в которой отображается список объектов, при нажатии на любой из которых и будет 
происходить переход. Активность реализует интерфейс `VerticalAdapter.OnItemCustomClickListener` который позволяет ей слушать нажатия на объекты.

*DetailActivity* - экран на который мы переходим. Имеет общий элемент (логотип) с тем объектом, на который было сделано
 нажатие.

*VerticalAdapter* - адаптер, который отображает объекты, который были получены с помощью вспомогательного класса 
`ObjectGenerator`. При создании объекта берётся код цвета, картинка и номер позиции (из которой делается имя).

*ObjectGenerator* - хранит у себя захардкодженный список цветов для бэкграунда логотипа и такой же список картинок. Из 
всего это умеет создать список объектов, которые, собственно, содержат только цвет и картинку.

### Как работает приложение

-Стартует *MainActivity*, которая запрашивает адаптер у *VerticalAdapter* (передавая ему количество элементов, которые 
нужны. По умолчанию 50 штук должно быть). Новый адаптер идёт к генератору объектов *ObjectGenerator*, получает объекты, 
заполняет адаптер и возвращает в MainActivity, которая ставит этот адаптер в RecyclerView.

-Так как в конструкторе адаптера указано, что слушателем нажатий будет MainActivity, при нажатии на любой элемент активность 
получает информацию об объекте (код цвета, адрес картинки, позицию объекта в списке).

-Получив информацию создаётся Intent, к которому крепится информация об объекте и специальный Bundle, где мы описываем 
View, которое должно быть анимировано.

-Запускается *DetailActivity*, где извлекаются параметры объекта (цвет и картинка) и назначаются новому View. 

### Как работает сама анимация

Под капотом собственно анимацией занимается Андроид. Нам остаётся лишь указать, что именно мы будем анимировать. Для 
этого нам надо передать инфомацию андроиду - стартовое View (с которого начинается анимация) и его уникальный ключ.

В принимающей активности (или фрагменте) - надо указать View на котором будет завершена анимация. Для этого надо назначить 
ему тот же уникальный ключ. Всё.

В данном примере делается так:

(На отправляющем экране)
```java
// это список всех вьюх, который будут анимироваться
// список хранит пары (Pairs) состоящие из вью и ключа
        List<Pair<View, String>> listOfViews = new ArrayList<>();
// в нашем случае есть только одна вьюха - логотип. Назначаем ему уник ключ "ivLogo"
// и добавляем в список
// чтобы создать пару можно использовать метод create класса Pair и сразу передать туда оба значения.
        listOfViews.add(Pair.create((View)ivLogo, "ivLogo"));
        
// список всех вьюх помещаем в Bundle через специальный метод makeSceneTransitionAnimation
// обязательно переводим список в массив (toArray).
        Bundle bundle = ActivityOptions.makeSceneTransitionAnimation(
                MainActivity.this, listOfViews.toArray(new android.util.Pair[]{})).toBundle();

// теперь нам надо передать принимающему экрану информацию о том, какой цвет
// и какую картинку использовать для логотипа
// Создадим обычное намерение
        Intent intent = new Intent(MainActivity.this, DetailActivity.class);
// получим информацию про объект от адаптера
        Pair<String, Integer> object = verticalAdapter.getItem(position);
// поместим в интент информацию про объект (цвет, картинка, позиция)
        intent.putExtra("color", object.first);
        intent.putExtra("logo", object.second);
        intent.putExtra("position", position);

// запустим новую активность используя намерение с информацией про объект + бандл с инфорацией о вьюхах.
        startActivity(intent, bundle);
```

(На принимающем экране)
```java
// Достаём переменную цвета
        String color = getIntent().getStringExtra("color");
// достаём переменную картинки
        int logo = getIntent().getIntExtra("logo", 0);
// достаём позицию
        int position = getIntent().getIntExtra("position", 0);

// новому объекту где будет логотип, присваиваем цвет и картинку
// и в конце обязательно ставим setTransitionName так же, как писали при отправке ("ivLogo")
        ImageView ivLogo = findViewById(R.id.ivLogo);
        ivLogo.setBackgroundColor(Color.parseColor(color));
        ivLogo.setImageResource(logo);
        ivLogo.setTransitionName("ivLogo");

// Из позиции сделаем такое же имя как в адаптере
        TextView tvName = findViewById(R.id.tvName);
        tvName.setText("Item position " + position);

// и в конце метода onCreate запустим анимацию
        supportStartPostponedEnterTransition(); 
```

Готово!

(напоминаю, код находится [на github](https://github.com/andrewgrow/AndroidTransitionAnimation/), можно собрать и посмотреть)

Happy coding and have fun!