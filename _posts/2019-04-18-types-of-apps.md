---
layout: single
title:  "Різновид мобільних додатків та особливості їх розробки"
author_profile: true
author: Danil
tags: 
    - университет
    - публикация
category:
    - university
--- 

УДК 004.451.9:621.395.721.5
{: .text-right}

#### Дудченко А.В., Гахов Д.А., Кострик В.О.,ст.гр.КМ-18
{: .text-right}  
<cite>Центральноукраїнський національний технічний університет</cite>
{: .small}
{: .text-right}

Сьогодення не стоїть на місці. Технологічний прогрес створює нове підґрунтя для розвитку різних видів професій 
таких, як: веб-дизайнер або ж кібер-спортсмен. Як відомо сучасні професії вимагають сучасних рішень. Одним із них є 
використання мобільних додатків.

Критерієм класифікації програмного забезпечення може бути що завгодно. Ми зупинимось на найбільш популярних видах, 
які зможуть надати позитивний вплив на різні аспекти життя.

*Інформаційні додатки.*  
Основна мета – інформування користувача (потенційного клієнта). Розповідає про новинки компанії. 
Автономно від ресурсу допускається виключно новинний додаток, орієнтований на певний сегмент новин або ж на все 
відразу. Використовується для реклами – інформаційні додатки одні з самих благодатних майданчиків розміщення реклами серед додатків.

*Служби.*  
Додатки, які переносять онлайн-ресурс на мобільний телефон. Підійде банкам, компаніям, що надають послуги онлайн. 
Не підійде таке створення мобільних додатків для продажу рекламних майданчиків, основна мета – зручність послуг 
клієнтам. Підвищує репутацію компанії.

*Ігри.*  
Лідер додатків сьогодні. Підійдуть для продажу рекламних майданчиків, “вірусна” гра може захопити користувача 
надовго: поїздки в метро, нудні лекції – кожна вільна хвилина з грою. Заробляти можна платним контентом або 
рекламою. Створення мобільних додатків такого типу – привабливий дизайн, захоплюючий сюжет. Складний вид розробки 
додатків для iOS або Android.

*Додаток.*  
Використовується супутнім елементом до техніки. Може бути пультом від нового телевізора, помічником управління 
автомобілем, стереосистемою будинку, іншої побутової технікою. Тип – схожий на службові, але носить більш 
розважальний характер.

*Інтернет-магазини.*  
Тепер онлайн торгівля стала доступнішою. Розробка програми для Android — це зростання продажів на третину 
(за статистикою більше половини користувачів СНД використовують продукт від Google на мобільних девайсах). Основна 
мета – можливість швидко зробити покупку, привабливий інтерфейс, оплата за допомогою тих же мобільних банківських 
служб.

*Органайзери.*  
Програмне забезпечення, що завжди можна знайти на смартфоні за будь-якої нагоди – це органайзери. Ціль таких 
додатків – спростити виконання буденних справ користувача. Прикладом можна привести проект мобільного додатку 
«Course Manager» описаного [в минулій статті](/course-manager/).

Яким би не був різновид додатку, але існує три основних типи розробки: нативне, гібридне та веб (рис.1).

[<img src="/assets/images/apps1.jpg" width="100%" />](/../../assets/images/apps1.jpg)
{: .text-center}  
<cite>Рис.1 – Три основні види розробки мобільних додатків</cite>
{: .text-right}

Нативний додаток є рідним для кожної операційної системи і пишеться спеціально для нього на визначеній мові 
програмування. Для написання нативного додатку для IOS використовують Swift або Objective-C, а для Android – Java 
або Kotlin.
 
На відміну від нативних додатків гібридні розроблюються для двох середовищ одразу використовуючи універсальну мову 
програмування.

У свою чергу веб – додаток, у якому клієнт є оглядачем Інтернету, а сервером – веб-сервер. Він є незалежним від 
операційної системи клієнта і в основному використовує такі мови програмування, як HTML, CSS, DOM та інші. 

Зважаючи на все вищесказане, ми можемо порівняти приведені нами види розробки мобільних додатків й обрати найбільш 
раціональний спосіб розв’язання поставленої задачі:  привести зручний для використання кінцевим споживачем продукт. 
Наша команда підійшла до рішення цієї задачі неоднозначно. Так, як проект «Course Manager» є органайзером  і 
створений для оптимізації навчального процесу, то логічно буде зазначити, що він орієнтований в основному на 
студентів, і функціонал програми  є найбільш актуальним безпосередньо під час навчання, тобто у вузі.

Додаток “підкаже” час до кінця пари, допоможе старості ввести зручний список групи,  записати важливу інформацію та 
багато іншого. Майже весь набір функцій потрібен студенту саме в навчальному закладі; до того ж дуже швидко – 
мобільний телефон чи смартфон стане в нагоді у 90% випадках. 

Із цього відповідно випливає те, що проект мобільного додатку “Course Manager” є цілком нативним, але використовує 
для своєї реалізації мову програмування “Java”, адже працює на смартфонах на базі ОС “Android”: дана операційна 
система є найбільш популярною в Україні. 

Тобто наша команда зосередилася саме на нативній розробці, спираючись саме на раціональність тому, що 
“Android-девайси” будуть використовуватись набагато частіше усіх інших. Але слід згадати те, що одна з найзначніших 
переваг мови програмування “Java” – кросплатформеність, тобто можливість підтримки ПО двома і більше апаратними 
платформами або ж операційними системами. 

Це означає, що наш додаток на даний момент оптимізований саме для найпоширеніших смартфонів під “Android”, але 
JVM дозволяє завантажити і використовувати органайзер з ОС “Windows” чи іншими, при цьому залишаючись нативним 
проектом. Користувачі не зможуть використовувати програму через “web”; робота на базі ОС для пристроїв фірми 
“Apple” найближчим часом також буде недоступною. Але в перспективі реалізація версій додатку для даних систем 
буде теж нативною, спираючись на всі переваги даного підходу.

<br/><br/><br/><br/>

```html
 Список використаних посилань:
    1. https://smile-ukraine.com/ua/mobile-apps/mobile-apps-types
    2. http://texnonews.com/Rozrobka-mobilnih-dodatkiv.-Vimogi-vidi-priznachennya.html
    3. https://webmedia.te.ua/rozrobka-mobilnyh-dodatkiv/
    4. https://spark.ru/startup/componentix/blog/4445/chem-nativnoe-prilozhenie-ot-razrabotchika-otlichaetsya-ot-prilozheniya-sozdannogo-v-konstruktore
    5. http://app-global.ru/blog/chto-vazhno-znat-razrabotchiku-o-prilozheniyah/
    6. https://umbrellait.com/ru/native-vs-hybrid-app
    7. https://wezom.com.ua/blog/chem-otlichajutsja-nativnoe-i-gibridnoe-mobilnye-prilozhenija
    8. http://sites.znu.edu.ua/webprog/lect/1191.ukr.html
```