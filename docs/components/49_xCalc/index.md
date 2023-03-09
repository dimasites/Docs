xCalc - это универсальный конструктор калькуляторов.

Хотелось разработать что-то универсальное, что могло бы решить большинство задач по калькуляторам (не без кастомизации, конечно). Я считаю, что у меня это получилось!

## Особенности

* Компонент разрабатывается с опорой на универсальность и внешнюю кастомизацию.
* Для произведения расчётов в каждом конкретном калькуляторе используется свой сниппет (PHP).
* Каждый конкретный калькулятор можно стилизовать, как угодно (HTML + CSS + Fenom).
* Поля не привязываются жёстко к конкретному калькулятору. Это значит, что одно поле можно использовать в нескольких калькуляторах сразу.
* Полю можно указать шаблон вывода, а при подключении к калькулятору подменить его, тоже самое и со значениями по-умолчанию.
* Можно задать обязательность заполнения любого поля.

## Для кого

Любой калькулятор требует определённой степени настройки. Для произведения расчётов в каждом конкретном калькуляторе используется свой сниппет. Следовательно, **разработчик взявшийся за настройку калькулятора, должен хоть немножко знать PHP**, чтобы можно было в сниппете описать взаимодействие полей друг с другом.