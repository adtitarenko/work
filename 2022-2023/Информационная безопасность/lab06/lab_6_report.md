---
# Front matter
title: "Лабораторная работа №6"
author: "Титаренко Анастасия Дмитриевна"

# Generic otions
lang: ru-RU
toc-title: "Содержание"

# Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

# Pdf output format
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n
polyglossia-lang:
  name: russian
  options:
  - spelling=modern
  - babelshorthands=true
polyglossia-otherlangs:
  name: english
### Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Misc options
indent: true
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
marp: false
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Развить навыки администрирования ОС Linux. Получить первое практическое знакомство с технологией SELinux. Проверить работу SELinx на практике совместно с веб-сервером Apache.


# Выполнение лабораторной работы
1. Вошла в систему с полученными учётными данными и убедилась, что SELinux работает в режиме enforcing политики targeted с помощью команд getenforce и sestatus.

![Проверка, что SELinux работает в режиме enforcing политики targeted](img/1.png){ #fig:001 width=70% }

2. Обратилась с помощью браузера к веб-серверу, запущенному на компьютере, и убедилась, что последний работает:
service httpd status
или
/etc/rc.d/init.d/httpd status

![Проверка, что веб-сервис запущен](img/2.png){ #fig:002 width=70% }

3. Нашла веб-сервер Apache в списке процессов, определила его контекст безопасности. Используя команду: ps auxZ | grep httpd

![Нахождение веб-сервер Apache в списке процессов](img/3.png){ #fig:003 width=70% }

4. Посмотрела текущее состояние переключателей SELinux для Apache с помощью команды: sestatus -bigrep httpd. Обратила внимание, что многие из них находятся в положении «off»

![Текущее состояние переключателей SELinux для Apache](img/4.png){ #fig:004 width=70% }

5. Посмотрела статистику по политике с помощью команды seinfo, также определила множество пользователей, ролей, типов.

![Статистика по политике с помощью команды seinfo](img/5.png){ #fig:005 width=70% }

6. Определила тип файлов и поддиректорий, находящихся в директории /var/www, с помощью команды: ls -lZ /var/www

![Типы файлов и поддиректорий, находящихся в директории /var/www](img/6.png){ #fig:006 width=70% }

7. Определила тип файлов, находящихся в директории /var/www/html: ls -lZ /var/www/html

![Типы файлов, находящихся в директории /var/www/html](img/7.png){ #fig:007 width=70% }

8. Определила круг пользователей, которым разрешено создание файлов в директории /var/www/html.

9. Создала от имени суперпользователя html-файл /var/www/html/test.html следующего содержания:
<html>
<body>test</body>
</html>

![Создание html-файла test.html](img/9.png){ #fig:009 width=70% }

10. Проверила контекст созданного файла. 

![Контекст созданного файла](img/10.png){ #fig:010 width=70% }

11. Обратилась к файлу через веб-сервер, введя в браузере адрес http://127.0.0.1/test.html. Убедилась, что файл был успешно отображён.

![Обращение к файлу через веб-сервер](img/11.png){ #fig:011 width=70% }

12. Изучила справку man httpd_selinux и выяснила, какие контексты файлов определены для httpd. 

![Справка man httpd](img/12.png){ #fig:012 width=70% }

13. Изменила контекст файла /var/www/html/test.html с httpd_sys_content_t на любой другой, к которому процесс httpd не должен иметь доступа, например, на samba_share_t:
chcon -t samba_share_t /var/www/html/test.html
ls -Z /var/www/html/test.html
После этого проверила, что контекст поменялся.

![Изменение контекста файла /var/www/html/test.html](img/13.png){ #fig:013 width=70% }

14. Попробуйте ещё раз получить доступ к файлу через веб-сервер, введя в браузере адрес http://127.0.0.1/test.html. Вы должны получить сообщение об ошибке: Forbidden. You don't have permission to access /test.html on this server.

![Доступ к файлу через веб-сервер](img/14.png){ #fig:014 width=70% }

15. Проанализируйте ситуацию. Почему файл не был отображён, если права доступа позволяют читать этот файл любому пользователю?
ls -l /var/www/html/test.html
Просмотрите log-файлы веб-сервера Apache. Также просмотрите системный лог-файл:
tail /var/log/messages
Если в системе окажутся запущенными процессы setroubleshootd и audtd, то вы также сможете увидеть ошибки, аналогичные указанным выше, в файле /var/log/audit/audit.log. Проверьте это утверждение самостоятельно.

![log-файлы веб-сервера Apache](img/15.png){ #fig:015 width=70% }

16. Попробовала запустить веб-сервер Apache на прослушивание ТСР-порта 81 (а не 80, как рекомендует IANA и прописано в /etc/services). Для этого в файле /etc/httpd/httpd.conf нашла строчку Listen 80 и заменила её на Listen 81.

![Запуск веб-сервер Apache на прослушивание ТСР-порта 81](img/16.png){ #fig:016 width=70% }

17. Выполнила перезапуск веб-сервера Apache. Произошёл сбой.

![Перезапуск веб-сервера Apache](img/17.png){ #fig:017 width=70% }

18. Проанализировала лог-файлы: tail -nl /var/log/messages. Просмотрела файлы /var/log/http/error_log, /var/log/http/access_log и /var/log/audit/audit.log и выяснила, в каких файлах появились записи.

![Лог-файлы: tail -nl /var/log/messages](img/18.png){ #fig:018 width=70% }

![Файл /var/log/http/error_log](img/19.png){ #fig:019 width=70% }

![Файлы /var/log/http/access_log и /var/log/audit/audit.log](img/20.png){ #fig:020 width=70% }

19. Выполнила команду: semanage port -a -t http_port_t -р tcp 81. После этого проверила список портов командой: semanage port -l | grep http_port_t. Убедилась, что порт 81 появился в списке.

![Список портов](img/21.png){ #fig:021 width=70% }

20. Попробовала запустить веб-сервер Apache ещё раз. 
21. Вернула контекст httpd_sys_cоntent__t к файлу /var/www/html/test.html: chcon -t httpd_sys_content_t /var/www/html/test.html. После этого попробовала получить доступ к файлу через веб-сервер, введя в браузере адрес http://127.0.0.1:81/test.html. 

![Возвращение контекста httpd_sys_cоntent__t к файлу /var/www/html/test.html](img/22.png){ #fig:022 width=70% }

![Доступ к файлу через веб-сервер](img/23.png){ #fig:023 width=70% }

22. Исправила обратно конфигурационный файл apache, вернув Listen 80.

![Исправление конфигурационного файла apache (Listen 80)](img/24.png){ #fig:024 width=70% }

23. Удалила привязку http_port_t к 81 порту: semanage port -d -t http_port_t -p tcp 81. Проверила, что порт 81 удалён.

![Удаление привязки http_port_t к 81 порту](img/25.png){ #fig:025 width=70% }

24. Удалила файл /var/www/html/test.html: rm /var/www/html/test.html

![Удаление файла /var/www/html/test.html](img/26.png){ #fig:026 width=70% }


# Вывод
Развила навыки администрирования ОС Linux. Получила первое практическое знакомство с технологией SELinux. Проверила работу SELinx на практике совместно с веб-сервером Apache.

# Список литературы
1. [Лабораторная работа № 6.  Мандатное разграничение прав в Linux](https://esystem.rudn.ru/pluginfile.php/1652027/mod_resource/content/2/006-lab_selinux.pdf)