---
layout: single
title:  "Работа с записями блога"
author_profile: true
author: Andrew
categories: [jekyll]
tags: [перевод]
---
Записи (POSTS) блога размещаются, как правило, в каталоге `_POSTS` и должны иметь формат 
`ГОД-МЕСЯЦ-ДЕНЬ-заголовок-записи.md`, где год это 4 цифры, а месяц и день по 2. 

Например, эта страница имеет имя 
```
2019-04-10-work-with-posts.md
```

Расширение может быть любым, например, `.html`. 
Но, если вы собрались писать с использованием MARKDOWN, тогда ставьте `.md`.

**Значения по умолчанию:**
```yaml
defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: true
      comments: # true
      share: true
      related: true
      sidebar:
        nav: "left_navigation_menu"
```
(эти значения установлены в файле _config.yml, см. в конце файла)

**Значения записи:**
```yaml
layout: single
title:  "Работа с записями блога"
author_profile: true
author: Andrew
categories: [jekyll]
tags: [перевод]
```
(эти значения установлены в файле этой записи, см. заголовок страницы)
