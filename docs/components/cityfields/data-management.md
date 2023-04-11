# Управление списком городов

У компонента имеется страница, на которой вы можете управлять списком городов, добавлять, изменять и удалять их, а также включать и отключать города.

![Список городов](https://file.modx.pro/files/0/3/9/039c0b08a2aab54e3d10aa1d489e34bas.jpg)

Необходимые города добавляются вручную. При определении города по IP сравниваются названия города, определённого в базе SypexGeo, и города, добавленного в список. Если такого города в списке нет или он отключен, то будет установлен город по умолчанию.

## Использование доменов, поддоменов и подкаталогов

Если вы хотите использовать для города поддомен или подкаталог, достаточно указать только ключ (например, `surgut`) и включить опцию "Город в домене" или "Город в подпапках" соответственно в настройках. Тогда город будет доступен по адресу `surgut.site.ru` или `site.ru/surgut/` соответственно. Вы также можете указывать разные полные домены для разных городов.

Также опции определения города по домену и подкаталогу можно использовать совместно. В этом случае в качестве ключа указывается полный домен и подкаталог, при необходимости.

При использовании доменов, поддоменов и подкаталогов необходимо добавить актуальную ссылку на город в тег `base` внутри блока `head`:

``` modx
<base href="[[!+cf.current_city.url]]" />
```

А в качестве плейсхолдера со ссылкой на главную страницу сайта использовать

``` modx
[[!+cf.current_city.url]]
```

## Вывод списка городов и информации о текущем городе

Для вывода списка городов с возможностью переключаться между ними достаточно просто вызвать сниппет:

``` modx
[[!cfCities]]
```

На любой странице сайта также вам будет доступна информация о выбранном городе, а именно:

``` modx
[[!+cf.current_city]]     - Наименование
[[!+cf.current_city.id]]  - ID
[[!+cf.current_city.key]] - Домен или ключ
[[!+cf.current_city.url]] - Ссылка на город
```

## Управление данными

На той же странице находится вкладка «Данные» для управления информацией для каждого города.

![Управление данными](https://file.modx.pro/files/c/c/4/cc49489f96b06b28a9699e1649acd8b4s.jpg)

Добавление и изменение данных происходит с этой страницы. В качестве плейсхолдера вы можете указать своё наименование плейсхолдера или выбрать из списка существующих.

## Вывод данных

В компоненте есть два метода вывода уникальной информации на страницах сайта.

1. По умолчанию включена запись полей в плейсхолдеры, которые имеют префикс. И для вывода информации достаточно добавить в ваши чанки или шаблоны необходимый плейсходер, но главное — **вызвать его не кешируемым**. Например, так:

    ``` modx
    [[!+cf.phone]]
    ```

2. Плейсхолдеры записываются при загрузке страницы, что может тормозить систему в некоторых случаях. Поэтому есть возможность отключить запись полей в плейсхолдеры. В этом случае для вывода информации для каждого города нужно вызвать сниппет `cfField` с нужным ключом/плейсхолдером:

    ``` modx
    [[!cfField ?&key=`phone`]]
    ```