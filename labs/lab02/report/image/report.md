---
## Front matter
title: "Доклад на тему: "Обзор виртуальных файловых систем""

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
#Цель работы
Рассказать об виртуальных файловых системах, об основах файловых систем,историю возникновения и кратко изложить суть использования.

#Введение
Виртуальная файловая система:
Она обеспечивает удобный механизм работы без необходимости привязки к конкретной реализации. С ее помощью программы способны оперировать файлами независимо от того, какая физическая файловая система используется. Виртуальная файловая система также обеспечивает поддержку различных операций, таких как чтение, запись, удаление и перемещение файлов, а также навигацию по директориям.

#Основы файловых систем
Основами являются:
• файлы – это основная единица хранения данных в файловой системе;
• каталоги, также известные как папки, – выполняют функцию организации файлов в иерархическую структуру;
• путь – это уникальный идентификатор расположения файла или папки в системе;
• расширение файла – указывает на тип данных, который содержится в файле;
• файловая система – может предоставлять различные уровни доступа к файлам и папкам;
• фрагментация – процесс разделения файлов на фрагменты, которые хранятся несколькими физическими блоками на диске;
• индексирование – создание структуры данных для быстрого доступа к документам;
• резервное копирование – создание копии файлов и папок для защиты от потери данных.
#История создания
Первые файловые типы были созданы одновременно с появлением компьютеров, в 50-х годах. Тогда файлы хранились на перфокартах или магнитных лентах, имела место "неупорядоченная организация файлов", при которой они просто хранились друг за другом без какой-либо организации или управления.
С развитием жестких дисков в 60-х годах появились более сложные типы, к примеру сегментирование с перемещением на диск. В 70-х годах появилась первая широко применяемая система управления иерархической базой данных. В конце 60-х и начале 70-х годов создана ОС UNIX, использовавшая иерархическую структуру каталогов. В 80-х годах Microsoft разработала FAT, ставшую стандартной для дискет и жестких дисков. Впоследствии появилась также NTFS для ОС Windows NT.
#Устройство VFS
VFS является программным или аппаратным устройством, представляющим собой интерфейс для управления. Оно работает на уровне ОС, скрывая сложности конкретной файловой системы. Это позволяет программам взаимодействовать с системой независимо от ее конкретной реализации. Обеспечивается абстракция файловой системы, и появляется возможность монтировать различные типы (FAT, NTFS, ext4) и обращаться к ним через API. Устройство может быть реализовано как часть ОС внутри ядра или как отдельный модуль, загружаемый в ОС при необходимости.
#Применение в современных ОС
ОС активно используют VFS, чтобы поддерживать различные типы файловых систем, такие как FAT, NTFS, ext4 и другие. Это позволяет пользователям работать с файлами и директориями, хранящимися на разных носителях и сетевых хранилищах, будто они находятся на локальном диске.
Их поддержка позволяет подключать удаленные сетевые файловые системы и работать с файлами и директориями, расположенными на удаленных серверах через протоколы сетевого доступа. VFS позволяет ОС контролировать доступ к файлам и директориям с помощью прав доступа и аутентификации пользователя. Это обеспечивает удобство и гибкость, универсальность поддержки различных типов файловых систем и возможность работы с сетевыми хранилищами.
#Структура VFS
Структура включает в себя несколько основных компонентов, которые позволяют абстрагироваться от конкретной системы и предоставляют унифицированный интерфейс для работы с файлами и каталогами. Сюда относятся:
• интерфейсы;
• файловая таблица;
• таблица дескрипторов файлов;
• драйверы;
• кэш;
• системные вызовы.
#Принцип работы
Он заключается в том, что представляет файловую систему как набор операций на файловых объектах, таких как чтение, запись, открытие и закрытие файлов, создание и удаление директорий. Программы и приложения взаимодействуют с VFS через стандартные системные вызовы операционной системы. Когда приложение запрашивает доступ, устройство перенаправляет его соответствующей конкретной системе, обрабатывающей запрос. Далее она возвращает результат.Устройство может обрабатывать различные типы систем, скрывая от приложений и пользователя детали реализации. Это позволяет создавать приложения, которые могут работать с различными файловыми системами и не зависеть от их конкретной реализации.
#Слежение за VFS
Данный процесс относится к отслеживанию или мониторингу действий, связанных с VFS. Он включает в себя следующее:
1. Мониторинг файловых операций.
2. Регистрация и аудит доступа к файлам.
3. Обнаружение изменений.
4. Создание резервных копий.
5. Мониторинг производительности.
Слежение полезно для различных научных, административных целей или безопасности.
#Bind и overlay монтирование
Это два разных способа монтирования файловых систем в Linux. Bind-монтирование позволяет создавать "связи" между каталогами. Ваша система может перемещать файлы из одного места в другое. Это особенно полезно, когда требуется обращаться к данным из разных мест, или когда необходимо создать несколько точек монтирования для одного и того же исходного каталога. При bind-монтировании изменения, вносимые в одну директорию, будут отображаться в другой.
Overlay-монтирование позволяет объединить несколько файловых систем в одну, создавая слой поверх основной системы. Он позволяет отображать содержимое одного каталога поверх другого без изменения исходных файлов.
#Реализация директорий
Это зависит от конкретной ОС и файловой системы. Однако в большинстве случаев директории представляют собой специальные типы файлов, которые содержат ссылки на другие файлы и поддиректории. В Windows они реализованы в виде папок, имеют имя и путь, содержат ссылки на другие файлы и папки. В Linux директории реализованы в виде inode объектов. Каждая имеет запись с именем файла или поддиректории, индексным номером inode. В macOS они также реализованы в виде папок аналогично Windows. Везде существуют API, позволяющие программистам работать с директориями из их приложений.
#Методы размещения файлов
Существуют методы:
1. Список индексных дескрипторов. Используется в FAT16, FAT32 и exFAT. Он представляет собой таблицу, в которой каждому файлу или директории сопоставлен индексный дескриптор, содержащий информацию о его местоположении на диске.
2. Дерево каталогов. Файлы и директории организованы в виде древовидной структуры, где каждый из них является узлом дерева. Корневой узел представляет собой верхний уровень файловой системы.
3. Индексный дескриптор. Каждому файлу или директории сопоставлен индексный дескриптор, который содержит метаданные о файле.
4. Хэш-таблицы. Используется в ZFS и Btrfs. Применяет хэш-функции для определения местоположения файлов на диске, обеспечивая более эффективные операции поиска и доступа к данным.
#Текущий и корневой каталоги процесса
Текущий каталог процесса – директория, в которой процесс в настоящий момент находится. Корневой каталог – верхняя и остальные директории являются подкаталогами. Каждый процесс имеет свою собственную текущую директорию, указывающую на конкретное место в файловой системе. Это означает, что разные процессы могут находиться в разных директориях одновременно. Процесс может изменить свою текущую директорию с помощью системного вызова, позволяющего осуществить переход.
#Какая файловая система относится к виртуальным?
Виртуальные файловые системы не являются конкретными файловыми системами сами по себе. Они служат в качестве промежуточного слоя между ядром ОС и конкретными системами.
Соответственно, ext4, NTFS, FAT32 и другие могут быть подключены к виртуальной файловой системе для доступа к данным на диске. VFS обеспечивает абстракцию, благодаря которой приложения могут работать с файлами и каталогами в разных файловых системах через одинаковый интерфейс.
#В чем разница между NTFS и FAT32?
NTFS и FAT32 – это две различные файловые системы, которые используются в ОС для организации и управления файлами и каталогами. NTFS поддерживает гораздо большие размеры томов по сравнению с FAT32. Максимальный размер тома в ней зависит от версии операционной системы, но в целом может быть достаточно большим. В FAT32 максимальный размер тома ограничен 2 ТБ.
NTFS также поддерживает более большие размеры файлов. Максимальный размер зависит от версии ОС, но может достигать нескольких петабайтов. В FAT32 максимальный размер файла ограничен 4 ГБ. NTFS использует более эффективный алгоритм распределения файлов на диске. Он позволяет более компактно хранить данные и более эффективно использовать свободное пространство. FAT32 имеет более простую структуру, что делает ее менее эффективной для хранения и управления файлами.
#Что такое виртуальная файловая система тест?
Она представляет собой специальную систему файлов, разработанную для проведения тестов и демонстраций. С ее помощью можно создавать виртуальные файлы и директории, симулируя реальную файловую систему и ее операции. ВФС-тест часто используется для оценки программ, работающих с файлами и директориями, чтобы проверить их корректность и надежность при различных сценариях использования. Это предоставляет разработчикам возможность создавать и модифицировать файлы, проверять права доступа, обрабатывать ошибки и испытывать программы на различных платформах и операционных системах. Ее применение способствует улучшению качества программного обеспечения, упрощает отладку и повышает надежность приложений.
#Что включает в себя файловая система?
Файловая система включает в себя следующие компоненты:
• файлы;
• директории;
• имена файлов;
• файловые атрибуты;
• операции над файлами;
• файловые дескрипторы;
• файловую система ввода-вывода.
Эти компоненты взаимодействуют друг с другом, образуя общую систему, обеспечивающую организацию данных на устройстве хранения и доступ к ним. Если вам требуется подобрать сервер с  ВФС, то IT-инженеры ittelo.ru отлично разбираются в этой теме. Поэтому они смогут предложить оптимальное решение в разумном бюджете
 
#Вывод
Изучение виртуальных файловых систем важно для оптимизации управления файлами и данными, обеспечивая удобство и эффективность взаимодействия приложений с хранилищами данных. Различные типы виртуальных файловых систем имеют практическое значение для улучшения производительности информационных систем и обеспечения надежного доступа к информации. Внедрение и использование виртуальных файловых систем способствует оптимизации работы с данными и повышению эффективности обработки информации в различных областях деятельности.
#Источники информации
1)https://www.ittelo.ru/news/virtualnaya-faylovaya-sistema/
2)https://habr.com/ru/companies/otus/articles/446614/
3)https://habr.com/ru/amp/publications/768462/