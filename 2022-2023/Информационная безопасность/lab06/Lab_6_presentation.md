---
## Front matter
lang: ru-RU
title: "Лабораторная работа №6"
subtitle: "Мандатное разграничение прав в Linux"
author:
    Титаренко Анастасия
    НПИбд-02-19\inst{1}
institute: |
	\inst{1}RUDN University, Moscow, Russian Federation
date: 2022, 15 October, Moscow, Russian Federation  

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
Развить навыки администрирования ОС Linux. Получить первое практическое знакомство с технологией SELinux. Проверить работу SELinx на практике совместно с веб-сервером Apache.


# Проверка, что SELinux работает в режиме enforcing политики targeted

![Проверка, что SELinux работает в режиме enforcing политики targeted](img/1.png){ #fig:001 width=70% }

# Проверка, что веб-сервис запущен

![Проверка, что веб-сервис запущен](img/2.png){ #fig:002 width=70% }

# Нахождение веб-сервер Apache в списке процессов

![Нахождение веб-сервер Apache в списке процессов](img/3.png){ #fig:003 width=70% }

# Текущее состояние переключателей SELinux для Apache

![Текущее состояние переключателей SELinux для Apache](img/4.png){ #fig:004 width=70% }

# Статистика по политике с помощью команды seinfo

![Статистика по политике с помощью команды seinfo](img/5.png){ #fig:005 width=70% }

# Типы файлов и поддиректорий, находящихся в директории /var/www

![Типы файлов и поддиректорий, находящихся в директории /var/www](img/6.png){ #fig:006 width=70% }

# Типы файлов, находящихся в директории /var/www/html

![Типы файлов, находящихся в директории /var/www/html](img/7.png){ #fig:007 width=70% }

# Создание html-файла test.html

![Создание html-файла test.html](img/9.png){ #fig:009 width=70% }

# Контекст созданного файла

![Контекст созданного файла](img/10.png){ #fig:010 width=70% }

# Обращение к файлу через веб-сервер

![Обращение к файлу через веб-сервер](img/11.png){ #fig:011 width=70% }

# Справка man httpd

![Справка man httpd](img/12.png){ #fig:012 width=70% }

# Изменение контекста файла /var/www/html/test.html

![Изменение контекста файла /var/www/html/test.html](img/13.png){ #fig:013 width=70% }

# Доступ к файлу через веб-сервер

![Доступ к файлу через веб-сервер](img/14.png){ #fig:014 width=70% }

# log-файлы веб-сервера Apache

![log-файлы веб-сервера Apache](img/15.png){ #fig:015 width=70% }

# Запуск веб-сервер Apache на прослушивание ТСР-порта 81

![Запуск веб-сервер Apache на прослушивание ТСР-порта 81](img/16.png){ #fig:016 width=70% }

# Перезапуск веб-сервера Apache

![Перезапуск веб-сервера Apache](img/17.png){ #fig:017 width=70% }

# Лог-файлы: tail -nl /var/log/messages

![Лог-файлы: tail -nl /var/log/messages](img/18.png){ #fig:018 width=70% }

# Файл /var/log/http/error_log

![Файл /var/log/http/error_log](img/19.png){ #fig:019 width=70% }

# Файлы /var/log/http/access_log и /var/log/audit/audit.log

![Файлы /var/log/http/access_log и /var/log/audit/audit.log](img/20.png){ #fig:020 width=70% }

# Список портов

![Список портов](img/21.png){ #fig:021 width=70% }

# Возвращение контекста httpd_sys_cоntent__t к файлу /var/www/html/test.html

![Возвращение контекста httpd_sys_cоntent__t к файлу /var/www/html/test.html](img/22.png){ #fig:022 width=70% }

# Доступ к файлу через веб-сервер

![Доступ к файлу через веб-сервер](img/23.png){ #fig:023 width=70% }

# Исправление конфигурационного файла apache (Listen 80)

![Исправление конфигурационного файла apache (Listen 80)](img/24.png){ #fig:024 width=70% }

# Удаление привязки http_port_t к 81 порту

![Удаление привязки http_port_t к 81 порту](img/25.png){ #fig:025 width=70% }

# Удаление файла /var/www/html/test.html

![Удаление файла /var/www/html/test.html](img/26.png){ #fig:026 width=70% }


# Вывод
Развила навыки администрирования ОС Linux. Получила первое практическое знакомство с технологией SELinux. Проверила работу SELinx на практике совместно с веб-сервером Apache.
