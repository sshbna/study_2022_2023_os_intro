---
## Front matter
title: "Отчет по 3 этапу индивидуального проекта"
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
# Выполнение
Список достижений.

(рис. [-@fig:001],[-@fig:002]).

![Написание достижений](image/1.png){#fig:001 width=70%}

![Список достижений](image/2.png){#fig:002 width=70%}

Добавить информацию о навыках (Skills).
(рис. [-@fig:003],[-@fig:004]).

![Написание навыков ](image/3.png){#fig:003 width=70%}

![Список навыков](image/4.png){#fig:004 width=70%}

Добавить информацию об опыте (Experience).
(рис. [-@fig:005],[-@fig:006]).

![Написание опыта](image/5.png){#fig:005 width=70%}

![Список опыта](image/6.png){#fig:006 width=70%}

Сделать пост по прошедшей неделе.
(рис. [-@fig:007],[-@fig:008]).

![Написание поста](image/7.png){#fig:007 width=70%}

![Пост по прошедшей неделе](image/8.png){#fig:008 width=70%}

Добавить пост на тему по выбору:
Легковесные языки разметки.
(рис. [-@fig:009],[-@fig:010]).

![Написание поста по выбору ](image/9.png){#fig:009 width=70%}

![Пост по выбору](image/10.png){#fig:010 width=70%}

# Выводы
Я выполнила все требуемые заданияБ=, научилась добавлять новую информацию и менять иконки.

# Список литературы{.unnumbered}

::: {#refs}
:::
