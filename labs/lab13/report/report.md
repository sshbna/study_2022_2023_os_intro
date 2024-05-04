---
## Front matter
title: "Отчет по лабораторной раблте № 13"
author: "Шубина София Антоновна"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
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
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы
Изучить основы программирования в оболочке ОС UNIX. Научится писать более
сложные командные файлы с использованием логических управляющих конструкций
и циклов.
[@tuis_rudn]

# Выполнение лабораторной работы
1. Используя команды getopts grep, написать командный файл, который анализирует
командную строку с ключами:
– -iinputfile — прочитать данные из указанного файла;
– -ooutputfile — вывести данные в указанный файл;
– -pшаблон — указать шаблон для поиска;
– -C — различать большие и малые буквы;
– -n — выдавать номера строк.
а затем ищет в указанном файле нужные строки, определяемые ключом -p.
2. Написать на языке Си программу, которая вводит число и определяет, является ли оно
больше нуля, меньше нуля или равно нулю. Затем программа завершается с помощью
функции exit(n), передавая информацию в о коде завершения в оболочку. Команд-
ный файл должен вызывать эту программу и, проанализировав с помощью команды
$?, выдать сообщение о том, какое число было введено.
3. Написать командный файл, создающий указанное число файлов, пронумерованных
последовательно от 1 до 𝑁 (например 1.tmp, 2.tmp, 3.tmp,4.tmp и т.д.). Число файлов,
которые необходимо создать, передаётся в аргументы командной строки. Этот же ко-
мандный файл должен уметь удалять все созданные им файлы (если они существуют).
4. Написать командный файл, который с помощью команды tar запаковывает в архив
все файлы в указанной директории. Модифицировать его так, чтобы запаковывались
только те файлы, которые были изменены менее недели тому назад (использовать
команду find).
 (рис. [-@fig:001]).

![Название рисунка](image/placeimg_800_600_tech.jpg){#fig:001 width=70%}
#1. Каково предназначение команды getopts?**

Команда `getopts` используется для разбора параметров командной строки. Она позволяет программе обрабатывать флаги и параметры, передаваемые ей при запуске.

# 2. Какое отношение метасимволы имеют к генерации имён файлов?**

Метасимволы, такие как `*`, `?` и `[]`, используются в оболочках UNIX для генерации имён файлов. Например, команда `ls *.txt` выведет список всех файлов с расширением `.txt` в текущем каталоге.

# 3. Какие операторы управления действиями вы знаете?**

* `if`
* `elif`
* `else`
* `fi`
* `test`
* `[[]]`

# 4. Какие операторы используются для прерывания цикла?**

* `break`
* `continue`

# 5. Для чего нужны команды false и true?**

Команды `false` и `true` используются для возврата значения выхода 1 (ложь) и 0 (истина) соответственно. Они могут быть полезны для управления потоком выполнения скрипта.

# 6. Что означает строка `if test -f man$s/$i.$s`, встреченная в командном файле?**

Эта строка проверяет, существует ли файл с именем `man$s/$i.$s` в текущем каталоге. Если файл существует, команда `if` выполнит перечисленные после нее команды.

# 7. Объясните различия между конструкциями while и until**

Конструкция `while` выполняет блок команд, пока условие истинно, а конструкция `until` выполняет блок команд, пока условие ложно.
# Выводы

Я изучила основы программирования в оболочке ОС UNIX. Научилась писать более сложные командные файлы с использованием логических усправляющих конструкций и циклов.
# Список литературы{.unnumbered}

::: {#refs}
:::
