C TESTED
========
Версия 0.1.4b NOT TESTED
Программа предназначена для тестирования кода на языке c.  
Основным отличием является то, что тесты находятся все кода, то есть исходный код остаётся чистым; за это, правда, приходится платить скоростью.   

ОПИСАНИЕ НЕ СООТВЕТСТВУЕТ ДЕЙСТВИТЕЛЬНОСТИ
==========================================

--help
------
```
usage: tested.py [-h] [-f FOLDER]

Utility for testing C-code v0.1.1b

optional arguments:
  -h, --help            show this help message and exit
  -f FOLDER, --folder FOLDER
                        Project location for tests
```

Как это работает
----------------
С помощью ключа -f/--folder можно указать расположение тестируемого проекта. По умолчанию поиск происходит в ./
Тесты к *.c файлам и конфигурационный файл должны располагаться в папке %project_directory%/tests/.
Так, например, если натравить программу на папку *project*:
```
./project/
    tests/
        test_fact
        test_str_wrest
        tested.conf
    fact.c
    str_wrest.c
    not_tested.c
```
То будут протестированы файлы *fact.c* и *str_wrest.c* тестами из файлов *test_fact* и *test_str_wrest* соответственно, файл *not_tested.c* протестирован не будет в силу отсутсвия теста для него в папке tests/. Информация про него не попадёт в html файл.    
Тесты компилируются (в конфигурационном файле можно указать компилятор, ключи и имя html файла с информацией о тестировании), прогоняются и собирается информация, которая преобразовывается в html-ку.

Конфигурационный файл (tested.conf)
-----------------------------------
Пример стандартного конфигурационного файла:
```
# Помощь можно получить вот тут: https://github.com/ktulhy-kun/c_tested
# Модулем будем называть файл .с с исходными текстами

# Модулем будем называть файл .с с исходными текстами

# Компилятор, с помощью которого будет происходить сборка
compiler: gcc

# Флаги компиляции
compiler_flags: -pipe -O2 -std=c99

# Префикс имени файла с тестами для модуля. Например, для файла func.c файл с тестами должен
# называться test_func и располагаться в папке %project_directory%/tests/
test_file_prefix: test_

# Файл с результатами тестов
out_file: Tests_Results_Project.html

# Сервисные параметры

# Префикс файла с исходным кодом теста для модуля (генерируется автоматически, после использования
# удаляется)
c_file_prefix: t_source_

# Префикс исполнемого файла теста модуля (генерируется автоматически, после использования
# удаляется)
exec_file_prefix: t_exec_

# Префикс файла с результатами теста модуля (генерируется автоматически, после использования
# удаляется)
test_result_file_prefix: t_result_
```

Результаты тестов
-----------------
Отображаются сообщения компилятора для каждого файла и краткая информация о тестах.
Посмотреть пример рузельтатов можно в файле Tests_Results_Project.html


Тесты
-----
В процессе написания

Типы тестов
-----------
В процессе написания

В планах
--------
* Тестирование
* Тест для структур
* Многопоточность
* Логирование
* Навигация по html файлу
* Выборочная проверка
* Допроверка при аварийном завершении тестовой программы






