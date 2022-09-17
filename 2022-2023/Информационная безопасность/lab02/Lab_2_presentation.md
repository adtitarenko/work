---
## Front matter
lang: ru-RU
title: "Лабораторная работа №2"
subtitle: "Дискреционное разграничение прав в Linux. Основные атрибуты"
author:
    Титаренко Анастасия
    НПИбд-02-19\inst{1}
institute: |
	\inst{1}RUDN University, Moscow, Russian Federation
date: 2022, 17 September, Moscow, Russian Federation  

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
Получение практических навыков работы в консоли с атрибутами файлов, закрепление теоретических основ дискреционного разграничения доступа в современных системах с открытым кодом на базе ОС Linux.


# Создание пользователя guest

![Создание пользователя guest](img/1.png){ #fig:001 width=70% }

# Вход под пользователем guest

![Вход под пользователем guest](img/2.png){ #fig:002 width=70% }

# Определение домашней директории

![Определение директории](img/3.png){ #fig:003 width=70% }

# Команда whoami

![Команда whoami](img/4.png){ #fig:004 width=70% }

# Информация о пользователе

![Информация о пользователе](img/5.png){ #fig:005 width=70% }

# Просмотр информации о пользователе в файле /etc/passwd

![Просмотр информации о пользователе в файле /etc/passwd](img/6.png){ #fig:006 width=70% }

# Просмотр директорий и поддиректорий

![Просмотр директорий и поддиректорий](img/7.png){ #fig:007 width=70% }

# Создание директории dir1

![Создание директории dir1](img/8.png){ #fig:008 width=70% }

# Просмотр прав доступа директории dir1

![Просмотр прав доступа директории dir1](img/9.png){ #fig:009 width=70% }

# Просмотр расширенных атрибутов

![Просмотр расширенных атрибутов](img/10.png){ #fig:010 width=70% }

# Изменение прав доступа

![Изменение прав доступа](img/11.png){ #fig:011 width=70% }

# Создание файла file1

![Создание файла file1](img/12.png){ #fig:012 width=70% }

# Таблица 2.1 «Установленные права и разрешённые действия»

![Таблица 2.1 «Установленные права и разрешённые действия»](img/13.png){ #fig:013 width=70% }

# Таблица 2.2 «Минимальные права для совершения операций»

![Таблица 2.2 «Минимальные права для совершения операций»](img/14.png){ #fig:014 width=70% }


# Вывод
Приобрела практические навыки работы в консоли с атрибутами файлов, закрепила теоретические основы дискреционного разграничения доступа в современных системах с открытым кодом на базе ОС Linux. 
