---
## Front matter
lang: ru-RU
title: "Лабораторная работа №3"
subtitle: "Дискреционное разграничение прав в Linux. Два пользователя"
author:
    Титаренко Анастасия
    НПИбд-02-19\inst{1}
institute: |
	\inst{1}RUDN University, Moscow, Russian Federation
date: 2022, 24 September, Moscow, Russian Federation  

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
Получение практических навыков работы в консоли с атрибутами файлов для групп пользователей.


# Создание пользователя guest

![Создание пользователя guest](img/1.png){ #fig:001 width=70% }

# Создание пароля для пользователя guest

![Создание пароля для пользователя guest](img/2.png){ #fig:002 width=70% }

# Создание пользователя guest2

![Создание пользователя guest2](img/3.png){ #fig:003 width=70% }

# Добавление пользователя guest2 в группу guest

![Добавление пользователя guest2 в группу guest](img/4.png){ #fig:004 width=70% }

# Вход под двумя пользователями

![Вход под двумя пользователями](img/5.png){ #fig:005 width=70% }

# Определение домашней директории

![Определение домашней директории](img/6.png){ #fig:006 width=70% }

# Определение имени пользователя, его группы, кто входит в неё и к каким группам принадлежит он сам

![Определение имени пользователя, его группы, кто входит в неё и к каким группам принадлежит он сам](img/7.png){ #fig:007 width=70% }

# Просмотр информации о пользователях в файле /etc/group

![Просмотр информации о пользователях в файле /etc/group](img/8.png){ #fig:008 width=70% }

# Регистрация пользователя guest2 в группе guest

![Регистрация пользователя guest2 в группе guest](img/9.png){ #fig:009 width=70% }

# Изменение прав директории /home/guest

![Изменение прав директории /home/guest](img/10.png){ #fig:010 width=70% }

# Изменение прав директории /home/guest/dir1

![Изменение прав директории /home/guest/dir1](img/11.png){ #fig:011 width=70% }

# Таблица 3.1 «Установленные права и разрешённые действия для групп»

![Таблица 3.1 «Установленные права и разрешённые действия для групп»](img/12.png){ #fig:012 width=70% }

# Таблица 3.2 «Минимальные права для совершения операций от имени пользователей входящих в группу»

![Таблица 3.2 «Минимальные права для совершения операций от имени пользователей входящих в группу»](img/13.png){ #fig:013 width=70% }

# Вывод
Приобрела практические навыки работы в консоли с атрибутами файлов для групп пользователей.
