---
## Front matter
title: "Индивидуальный проект(часть 2)"
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
Добавить к сайту данные о себе 

# Задание
Список добавляемых данных.
Разместить фотографию владельца сайта.
Разместить краткое описание владельца сайта (Biography).
Добавить информацию об интересах (Interests).
Добавить информацию от образовании (Education).
Сделать пост по прошедшей неделе.
Добавить пост на тему по выбору:
Управление версиями. Git.
Непрерывная интеграция и непрерывное развертывание (CI/CD).
[@tuis_rudn]

# Выполнение лабораторной работы
1)Для начала надо добавить свою фотографию для сайта
/home/sashubina/work/block/content/authors/admin
c названием avatar.jpg
 (рис. [-@fig:001]).

![Фотография на сайте](image/1.png){#fig:001 width=70%}

2)Далее размещаем краткое описание владельца сайта
(рис. [-@fig:002],[-@fig:003]).

![Краткое описание на сайте](image/2.png){#fig:002 width=70%}

![Краткое описание написание](image/6.png){#fig:003 width=70%}

3)Добавить информацию об интересах
(рис. [-@fig:004]).

![Информация об интересах на сайте ](image/2.png){#fig:004 width=70%}

4)Добавить информацию об образовании
(рис. [-@fig:005]).

![Информация об интересах на сайте ](image/6.png){#fig:005 width=70%}
 
5)Добавить пост по прошедшей неделе
(рис. [-@fig:006],[-@fig:007]).

![Пост о прошедшей неделе](image/4.png){#fig:006 width=70%}

![Пост о прошедшей неделе](image/7.png){#fig:007 width=70%}

6)Добавить пост на тему по выбору, я выбрала Непрерывная интеграция и непрерывное развертывание (CI/CD)
(рис. [-@fig:008]).

![Пост на тему CI/CD](image/5.png){#fig:008 width=70%}
# Выводы

Я добавила к сайту данные о себе

# Список литературы{.unnumbered}

::: {#refs}
:::
