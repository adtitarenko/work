---
## Front matter
lang: ru-RU
title: "Лабораторная работа №5"
subtitle: "Дискреционное разграничение прав в Linux. Исследование влияния дополнительных атрибутов"
author:
    Титаренко Анастасия
    НПИбд-02-19\inst{1}
institute: |
	\inst{1}RUDN University, Moscow, Russian Federation
date: 2022, 8 October, Moscow, Russian Federation  

## Formatting
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
toc: false
slide_level: 2
theme: metropolis
header-includes: 
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
 - \usepackage[T2A]{fontenc}
 - \usepackage{amsmath}
aspectratio: 43
section-titles: true
---

# Цель работы
Изучение механизмов изменения идентификаторов, применения SetUID- и Sticky-битов. Получение практических навыков работы в консоли с дополнительными атрибутами. Рассмотрение работы механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.

# Создание программы


# Листинг программы simpleid.c

![Листинг программы simpleid.c](img/1.png){ #fig:001 width=70% }

# Компилирование программы simpleid.c

![Компилирование программы simpleid.c](img/2.png){ #fig:002 width=70% }

# Сравнение результата команд ./simpleid и id

![Сравнение результата команд ./simpleid и id](img/3.png){ #fig:003 width=70% }

# Листинг программы simpleid2.c

![Листинг программы simpleid2.c](img/4.png){ #fig:004 width=70% }

# Компилирование и запуск программы simpleid2.c

![Компилирование и запуск программы simpleid2.c](img/5.png){ #fig:005 width=70% }

# Изменение прав доступа файла simpleid2

![Изменение прав доступа файла simpleid2](img/6.png){ #fig:006 width=70% }

# Проверка правильности установки новых атрибутов и смены владельца файла simpleid2

![Проверка правильности установки новых атрибутов и смены владельца файла simpleid2](img/7.png){ #fig:007 width=70% }

# Сравнение результата команд ./simpleid2 и id

![Сравнение результата команд ./simpleid2 и id](img/8.png){ #fig:008 width=70% }

# Изменения относительно SetGID-бита файла simpleid2

![Изменения относительно SetGID-бита файла simpleid2](img/9.png){ #fig:009 width=70% }

# Листинг программы readfile.c

![Листинг программы readfile.c](img/10.png){ #fig:010 width=70% }

# Компилирование программы readfile.c

![Компилирование программы readfile.c](img/11.png){ #fig:011 width=70% }

# Изменения прав файла readfile.c

![Изменения прав файла readfile.c](img/12.png){ #fig:012 width=70% }

# Установка SetU’D-бита и изменения владельца файла readfile.c

![Установка SetU’D-бита и изменения владельца файла readfile.c](img/13.png){ #fig:013 width=70% }


# Исследование Sticky-бита


# Выполнение команды: ls -l / | grep tmp

![Выполнение команды: ls -l / | grep tmp](img/14.png){ #fig:014 width=70% }

# Создание файла file01.txt

![Создание файла file01.txt](img/15.png){ #fig:015 width=70% }

# Просмотр аттрибутов и изменение прав файла file01.txt

![Просмотр аттрибутов и изменение прав файла file01.txt](img/16.png){ #fig:016 width=70% }

# Попытка прочитать файл file01.txt от пользователя, не являющегося владельцем

![Попытка прочитать файл file01.txt от пользователя, не являющегося владельцем](img/17.png){ #fig:017 width=70% }

# Изменение файла file01.txt и просмотр содержимого

![Изменение файла file01.txt и просмотр содержимого](img/18.png){ #fig:018 width=70% }

# Изменение файла file01.txt и просмотр содержимого

![Изменение файла file01.txt и просмотр содержимого](img/19.png){ #fig:019 width=70% }

# Попытка удалить файл file01.txt]

![Попытка удалить файл file01.txt](img/20.png){ #fig:020 width=70% }

# Сняла атрибут -t с директории /tmp и покинула режим суперпользователя
 
![Сняла атрибут -t с директории /tmp и покинула режим суперпользователя](img/21.png){ #fig:021 width=70% }

# Проверка: атрибута -t нет у директории /tmp

![Проверка: атрибута -t нет у директории /tmp](img/22.png){ #fig:022 width=70% }

# Повтор предыдущих шагов

![Повтор предыдущих шагов](img/23.png){ #fig:023 width=70% }

# Вернула атрибут -t с директории /tmp

![Вернула атрибут -t с директории /tmp](img/24.png){ #fig:024 width=70% }


# Вывод
Изучила механизмы изменения идентификаторов, применения SetUID- и Sticky-битов. Получила практические навыки работы в консоли с дополнительными атрибутами. Рассмотрела работы механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.
