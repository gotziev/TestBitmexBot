# BitmexBot

This is some test project!

## Бот для работы с криптобиржей BITMEX  
####  TASK

Написать бота для работы с криптобиржей BITMEX для выставления и отмены ордеров
в аккаунте клиента по следующему алгоритму.
Считываем последнюю цену биткоин и выставляем level ордеров на покупку 
биткоин по (последняя цена - step) при сумме каждого ордера coef. Далее следим за ордерами и
в случае исполнения ордера - сразу выставляем другой ордер на продажу по цене (Покупка + step).

Шаги.
#### 1.Принимаем данные от клиента
Принять через WEB интерфейс
от клиента входные данные:
-принять String ключ API доступа к аккаунту клиента.  
-принять String Секрет API доступа к аккаунту клиента. 
-принять long step - разница между ценами ордеров 200 долларов
-принять long level - количество ордеров.
-принять double coef - сумма ордера.
##### 2.Установить ордера на покупку Long
Проверяем валидность Api ключей и выводим на экран.
Получаем текущую цену биткоина запрашивая последний исполненный ордер
на покупку например 20_000.
Устанавливаем первый ордер на покупку по цене 19_800.
Устанавливаем второй ордер на покупку по цене 19_600.
Устанавливаем третий ордер на покупку по цене 19_400.

Сумма ордера это coef.

##### 3.Следим за измененнием цены
как только купили первый ордер - тут же выставляем его на продажу
выше на step.
т.е. купили по 19_800 степ 200 - выставляем на продажу по 20_000
и так со всеми ордерами.
По мере срабатывания ордеров на продажу или покупку
действия повторяются.