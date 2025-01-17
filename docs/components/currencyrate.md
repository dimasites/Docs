---
title: CurrencyRate
description: Курсы иностранных валют с сайта Банка России
logo: https://modstore.pro/assets/extras/currencyrate/logo-lg.jpg
author: vgrish
modstore: https://modstore.pro/packages/other/currencyrate
repository: https://github.com/vgrish/currencyrate
---
# CurrencyRate

Информация о курсах иностранных валют по отношению к рублю, опубликованная на официальном сайте Банка России в сети Интернет.

![CurrencyRate](https://file.modx.pro/files/5/7/0/570b9fc1fad81b67bd03bf28374acf42.png)

## Настройки компонента

— Включить / Выключить растановку плейсходеров с курсом валют
— Адрес сервиса - url для запроса курса валют
— Дата обновления - записывается время последнего обновления

## Плейсходеры **курса валют**

Если активна настройка **Включить растановку плейсходеров** - то курс валюты доступны по плейсходеру `[[++код_валюты]]`
например:

```modx
[[++USD]]
```

## Корректировка значения курса

Есть поправочный коэф-т — можно самостоятельно корректировать курс валюты. Задается либо числом, либо значением в процентах.

## Сниппет **CRcalc**

Для расчета цен в указанной валюте относительно значения заданного в админке.
**input** - входящее значение (стоимость товара)

**divider** - делитель, если указан - будет выполнена операция деления (указать код валюты)

**multiplier** - множитель, если указан - будет выполнена операция умножения (указать код валюты)

**format** - формат цены

**noZeros** - Убрать лишние нули в цене

## Скрипт для **Cron**

Для автоматического обновления курса валют в комплекте скрипт для cron.
