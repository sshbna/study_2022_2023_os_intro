---
## Front matter
lang: ru-RU
title: Презентация по лабораторной работе №5
author:
  - Шубина С.А.
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 10 марта 2024

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
---

# Информация

## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Шубина София Антоновна
  * Студентка НПИбд-02-23
  * факультет физико-математических и естественных наук
  * Российский университет дружбы народов
  * [1132232885@pfur.ru](mailto:1132232885@pfur.ru)

::::::::::::::

# Цель работы
Научиться работать с менеджером паролей.

# Выполнение лабораторной работы

## Менеджер паролей pass
Установка
Fedora
pass
dnf install pass pass-otp
gopass
dnf install gopass

![Установка](1.png){.column width="30%"}
![Установка](2.png){.column width="30%"}

## Настройка
Ключи GPG
Просмотр списка ключей:
gpg --list-secret-keys

![Просмотр списка ключей](image/3.png){.column width="30%"}

## Если ключа нет, нужно создать новый:
gpg --full-generate-key
Инициализация хранилища
Инициализируем хранилище:
pass init <gpg-id or email>

![Инициализация хранилища](image/4.png){.column width="30%"}

## Синхронизация с git
Создадим структуру git:
pass git init

![Создем структуру git](image/5.png){{.column width="30%"}

## Также можно задать адрес репозитория на хостинге (репозиторий необходимо предварительно создать):
pass git remote add origin git@github.com:<git_username>/<git_repo>.git

![Создаем репозиторий](image/6.png){.column width="30%"}

![Задаем адрес репозитория на хостинге](image/7.png){{.column width="30%"}

## Для синхронизации выполняется следующая команда:
pass git pull
pass git push

![Синхронизация](image/8!.png){.column width="30%"}

## Прямые изменения
Следует заметить, что отслеживаются только изменения, сделанные через сам gopass (или pass).
Если изменения сделаны непосредственно на файловой системе, необходимо вручную закоммитить и выложить изменения:
cd ~/.password-store/
git add .
git commit -am 'edit manually'
git push

![Выкладываем изменения](image/9.png){.column width="30%"}

## Проверить статус синхронизации модно командой
pass git status

![Проверка статуса синхронизации](image/10.png){.column width="30%"}

## Настройка интерфейса с броузером
Для взаимодействия с броузером используется интерфейс native messaging.
Поэтому кроме плагина к броузеру устанавливается программа, обеспечивающая интерфейс native messaging.
Fedora
dnf copr enable maximbaz/browserpass
dnf install browserpass

![Настройка интерфейса с браузером](image/11.png){.column width="30%"}
![Настройка интерфейса с браузером](image/12.png){{.column width="30%"}

## Сохранение пароля
Добавить новый пароль
Выполните:
pass insert [OPTIONAL DIR]/[FILENAME]
OPTIONAL DIR: необязательное имя каталога, определяющее файловую структуру для вашего хранилища паролей;
FILENAME: имя файла, который будет использоваться для хранения пароля.
Отобразите пароль для указанного имени файла:
pass [OPTIONAL DIR]/[FILENAME]
Замените существующий пароль:
pass generate --in-place FILENAME

![Манипуляции с паролем](image/13.png){.column width="30%"}

## Управление файлами конфигурации
Дополнительное программное обеспечение
Установите дополнительное программное обеспечение:
sudo dnf -y install \
dunst \
fontawesome-fonts \
powerline-fonts \
light \
fuzzel \
swaylock \
kitty \
waybar swaybg \
wl-clipboard \
mpv \
grim \
slurp

![Установка доп. программного обеспечения](image/14.png){.column width="30%"}

## Установите шрифты:
sudo dnf copr enable peterwu/iosevka
sudo dnf search iosevka
sudo dnf install iosevka-fonts iosevka-aile-fonts iosevka-curly-fonts iosevka-slab-fonts iosevka-etoile-fonts iosevka-term-fonts

![Установка шрифтов](image/15.png){.column width="30%"}

## Установка
Установка бинарного файла. Скрипт определяет архитектуру процессора и операционную систему и скачивает необходимый файл:
с помощью wget:
sh -c "$(wget -qO- chezmoi.io/get)"

![Установка бинарного файла](image/16.png){.column width="30%"}

## Создание собственного репозитория с помощью утилит
Будем использовать утилиты командной строки для работы с github.
Создадим свой репозиторий для конфигурационных файлов на основе шаблона:
gh repo create dotfiles --template="yamadharma/dotfiles-template" --private

![Создание репозитория с помощью утилит](image/17.png){.column width="30%"}

## Подключение репозитория к своей системе
Инициализируйте chezmoi с вашим репозиторием dotfiles:
chezmoi init git@github.com:<username>/dotfiles.git

![Инициализация](image/18.png){.column width="30%"}

## Проверьте, какие изменения внесёт chezmoi в домашний каталог, запустив:
chezmoi diff
Если вас устраивают изменения, внесённые chezmoi, запустите:
chezmoi apply -v

![Проверка и одобрение изменений](image/19.png){.column width="30%"}

## Использование chezmoi на нескольких машинах
На второй машине инициализируйте chezmoi с вашим репозиторием dotfiles:
chezmoi init https://github.com/<username>/dotfiles.git
Или через ssh:
chezmoi init git@github.com:<username>/dotfiles.git
Также можно вызвать инструмент слияния, чтобы объединить изменения между текущим содержимым файла, файлом в вашей рабочей копии и измененным содержимым файла:
chezmoi merge file_name
При существующем каталоге chezmoi можно получить и применить последние изменения из вашего репозитория:
chezmoi update -v
Настройка новой машины с помощью одной команды
 Можно установить свои dotfiles на новый компьютер с помощью одной команды:
сhezmoi init --apply https://github.com/<username>/dotfiles.git
(рис. [-@fig:020]).

![Использованиие chemoi на второй виртуальной машине](image/21.png){.column width="30%"}

## Ежедневные операции c chezmoi
Извлеките последние изменения из репозитория и примените их
Можно извлечь изменения из репозитория и применить их одной командой:
chezmoi update
Это запускается git pull --autostash --rebase в вашем исходном каталоге, а затем chezmoi apply.
Извлеките последние изменения из своего репозитория и посмотрите, что изменится, фактически не применяя изменения
Выполните:
chezmoi git pull -- --autostash --rebase && chezmoi diff
Это запускается git pull --autostash --rebase в вашем исходном каталоге, а chezmoi diff затем показывает разницу между целевым состоянием, вычисленным из вашего исходного каталога, и фактическим состоянием.
(рис. [-@fig:021]).

![Извлечение последних изменений](image/24.png){.column width="30%"}

## Если вы довольны изменениями, вы можете применить их:
chezmoi apply
Можно автоматически фиксировать и отправлять изменения в исходный каталог в репозиторий.
Эта функция отключена по умолчанию.
Чтобы включить её, добавьте в файл конфигурации ~/.config/chezmoi/chezmoi.toml следующее:
 [git]
autoCommit = true
autoPush = true
(рис. [-@fig:022]).

![Листинг](image/25.png){.column width="30%"}

# Выводы
Я научилась работать с менеджером паролей


