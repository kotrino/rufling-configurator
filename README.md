# Информация о вилке
Этот проект основан на [https://github.com/betaflight/betaflight-configurator.git!(https://github.com/betaflight/betaflight-configurator.git)

---

# Betaflight Configurator

! [Betaflight] (http://static.rcgroups.net/forums/attachments/6/1/0/3/7/6/a9088900-228-bf_logo.jpg)

[! [Последняя версия] (https://img.shields.io/github/v/release/betaflight/betaflight-configurator)] (https://github.com/betaflight/betaflight-configurator/releases) [!Build] (https://img.shields.io/github/actions/workflow/status/betaflight/betaflight-configurator/nightly.yml?branch=master)] (https://github.com/betaflight/betaflight-configurator/actions/workflows/nightly.yml) [! [Crowdin] (https://d322cqt584bo4o.cloudfront.net/betaflight-configurator/localized.svg)] (https://crowdin.com/project/betaflight-configurator)! [Статус качества ворота] (https://sonarcloud.io/api/project_badges/measure?Лицензия: GPL V3] (https://img.shields.io/badge/license-gplv3-blue.svg)] (https://www.gnu.org/licenses/gpl-3.0) [! [Присоединяйтесь к намDiscord!] (Https://img.shields.io/discord/868013470023548938)] (https://discord.gg/n4e6ak4u3c)


Betaflight Configurator - это инструмент конфигурации кроссплатформы для системы управления полетом BetaFlight.

Он работает как приложение в различных операционных системах и позволяет настроить программное обеспечение Betaflight, работающее на любой поддерживаемой цели Betaflight.[Загрузки доступны в выпусках.] (Https://github.com/betaflight/betaflight-configurator/releases)

Различные типы самолетов поддерживаются инструментом и Betaflight, например,Квадрокоптеры, гексакоптеры, октокоптеры и самолеты с фиксированным крылом.

## Авторы

Betaflight Configurator - это [fork] (#cutrits) конфигуратора Cleanflight с поддержкой Betaflight вместо Cleanflight.

Этот конфигуратор является единственным конфигуратором с поддержкой специфических функций Betaflight.Скорее всего, потребуется, чтобы вы запустили новейшую прошивку на контроллере полета.

Если у вас возникают какие -либо проблемы, убедитесь, что вы запускаете [последнюю версию прошивки] (https://github.com/betaflight/betaflight/releases/).

## Установка

### автономный

Мы предоставляем автономную программу для Windows, Linux, Mac и Android.

Загрузите установщик из [RELEASES.] (Https://github.com/betaflight/betaflight-configurator/releases)

### Примечания

#### Пользователи Windows

Минимальная требуемая версия Windows - Windows 8.

#### пользователи MacOS X

Изменения в модели безопасности, используемой в последних версиях MacOS X 10.14 (MOJAVE) и 10.15 (Catalina) означают, что операционная система будет отображать сообщение об ошибке («Betaflight Configurator.App» повреждена и не может быть открыта. Выдолжен переместить его в мусор. ') При попытке установить приложение.Чтобы обойти это, запустите следующую команду в терминале после установки:`sudo xattr -rd com.apple.quarantine /Applications/Betaflight\ Configurator.app`Полем

#### Пользователи Linux

Первый шаг - загрузить установщик и сохранить его в рабочем каталоге, что можно сделать со следующей командой:```
wget https://github.com/betaflight/betaflight-configurator/releases/download/10.10.0/betaflight-configurator_10.10.0_amd64.deb
```В большинстве распределений Linux ваш пользователь не будет иметь доступа к последовательным интерфейсам по умолчанию.Чтобы добавить этот доступ к этому доступу правый тип следующей команды в терминал, войдите в систему и войдите снова:```
sudo usermod -aG dialout ${USER}
```Ошибки после установки могут быть предотвращены, чтобы убедиться, что каталог`/usr/share/desktop-directories`существует.Чтобы убедиться, что он существует, запустите следующую команду перед установкой пакета:```
sudo mkdir /usr/share/desktop-directories/
```А`libatomic`Библиотека также должна быть установлена ​​перед установкой конфигуратора Betaflight.(Если библиотека отсутствует, установка будет успешной, но конфигуратор Betaflight не запустится.) Некоторые дистрибутивы Linux (например, Fedora) будут установить его автоматически.На Debian или Ubuntu вы можете установить его следующим образом:```
sudo apt install libatomic1
```На Ubuntu 23.10, пожалуйста, выполните эти альтернативные шаги для установки:```
sudo echo "deb http://archive.ubuntu.com/ubuntu/ lunar universe" > /etc/apt/sources.list.d/lunar-repos-old.list
sudo apt update
sudo dpkg -i betaflight-configurator_10.10.0_amd64.deb
sudo apt-get -f install
```На Ubuntu 24.10 и выше следуйте этим шагам, так как некоторые устаревшие модули больше не доступны через APT на этом дистрибутиве:```
sudo apt update
wget http://archive.ubuntu.com/ubuntu/pool/universe/g/gconf/libgconf-2-4_3.2.6-4ubuntu1_amd64.deb
wget http://archive.ubuntu.com/ubuntu/pool/universe/g/gconf/gconf2-common_3.2.6-4ubuntu1_all.deb
sudo dpkg -i gconf2-common_3.2.6-4ubuntu1_all.deb
sudo dpkg -i libgconf-2-4_3.2.6-4ubuntu1_amd64.deb
sudo dpkg -i betaflight-configurator_10.10.0_amd64.deb
sudo apt-get -f install
```#### Графические проблемы

Если вы испытываете проблемы с графическим отображением или размахиваемые/рассеянные шрифты отображаются в конфигураторе Betaflight, попробуйте вызовать`betaflight-configurator`исполняемый файл с`--disable-gpu`коммутатор командной строки.Это отключит аппаратную графику ускорения.Аналогичным образом, установка опции Antialiasing вашей графической карты на выключение (например, параметр FXAA на графических картах NVIDIA) также может быть лекарством.

### нестабильные версии тестирования

Будущее конфигуратора переходит в PWA (прогрессивное веб -приложение).Таким образом, будет проще поддерживать специально для поддержки различных устройств, таких как телефоны, планшеты.и т.д. находится работа в процессе, но вы можете иметь доступ к последнему снимку в PWA Way, не устанавливая ничего (примите во внимание, что некоторые вещи не работают и находятся в разработке).

- Последний снимок конфигуратора PWA Master: https://master.dev.app.betaflight.com/

** Имейте в виду, что эта версия предназначена только для тестирования / обратной связи, и может быть глюкой или сломанной, и может вызвать повреждение настройки контроллера полета.Внимание рекомендуется при использовании этой версии. **

## языки

** Пожалуйста, не отправляйте запросы на перевод для изменений перевода, но прочитайте и следуйте инструкциям ниже! **

Конфигуратор Betaflight был переведен на несколько языков.Приложение попытается обнаружить и использовать ваш язык системы, если будет доступен перевод на этот язык.Вы можете помочь [перевести приложение на свой язык] (https://github.com/betaflight/betaflight/tree/master/readme.md#translators);

Если вы предпочитаете иметь приложение на английском или любом другом языке, вы можете выбрать желаемый язык на первом экране приложения.

## сборка и разработка

### Технические детали

Следующими версиями конфигуратора станут современный инструмент, основанный на PWA (прогрессивное веб -приложение) и использует основные узлы, пряжу, VITE и VUE для разработки и строительства.Для Android мы используем конденсатор в качестве обертки над PWA.Чтобы построить и развиваться над этим, следуйте инструкциям ниже.

### Подготовьте окружающую среду

1. Установить [node.js] (https://nodejs.org/) (см.
2. Установите пряжу:`npm install yarn -g`### PWA версия

#### запустить версию разработки

1. Переключить в папку проекта и запустить`yarn install`Полем
2. бежать`yarn dev`Полем

Веб -приложение будет доступно по адресу http: // localhost: 8000 с полным HMR.

#### запустить производственную версию

1. Переключить в папку проекта и запустить`yarn install`Полем
2. бежать`yarn build`Полем
3. Беги`yarn preview`после того, как сборка закончилась.

В качестве альтернативы вы можете бежать`yarn review`Чтобы построить и предварительный просмотр за один шаг.

Веб -приложение должно вести себя непосредственно, как в производстве, доступно по адресу http: // localhost: 8080.

### версия Android

Примечание. Версия Android еще не полностью функциональна.Это в разработке.

#### Предварительные условия

Вам необходимо установить [Android Studio] (https://developer.android.com/studio), поскольку приложения конденсатора настроены и управляются через него.

#### запустить версию разработки

1. Переключить в папку проекта и запустить`yarn install`Полем
2. бежать`yarn android:run`Полем

Команда попросит устройство запустить приложение.Вам нужно создать некоторую виртуальную машину Android или немного телефона Android [подключен с помощью ADB] (https://developer.android.com/tools/adb).

В качестве альтернативы шагу 2 вы можете выполнить`yarn android:open`Чтобы открыть DE Project в Android Studio и запустить или отлаживать приложение оттуда.

#### Запустите версию разработки с Live Reload

1. Переключить в папку проекта и запустить`yarn install`Полем
2. бежать`yarn dev --host`ПолемОн запустит сервер VITE и покажет вам IP -адрес, где слушает сервер.
3. Беги`yarn android:dev`Это запрашивает IP, где работает сервер (если существует более одного сетевого интерфейса).Вам нужно создать некоторую виртуальную машину Android или немного телефона Android [подключен с помощью ADB] (https://developer.android.com/tools/adb).
Любое изменение в коде перезагружает приложение в устройстве Android.

### Запуск тестов`yarn test`## Канал поддержки и разработчиков

Здесь есть выделенный сервер дискордов:

https://discord.gg/n4e6ak4u3c

У нас также есть группа Facebook.Присоединяйтесь к нам, чтобы получить место, чтобы поговорить о Betaflight, задать вопросы конфигурации или просто пообщаться с другими пилотами.

https://www.facebook.com/groups/betaflightgroup/

Этикет: Не просите спросить, и, пожалуйста, подождите достаточно долго для ответа - иногда люди летят, спят или на работе не могут немедленно ответить.

### Трекеры выпуска

Для проблем конфигуратора Betaflight поднимите их здесь

https://github.com/betaflight/betaflight-configurator/issues

Для проблем прошивки Betaflight поднимите их здесь

https://github.com/betaflight/betaflight/issues

## Разработчики

Мы принимаем чистые и разумные патчи, отправляем их!

## кредиты

CTN - Основной автор и поддерживающий конфигуратор BaseFlight, из которого был разднулся проект Cleanflight Configurator.

Hydra - автор и сопровождающий конфигуратора Cleanflight, из которого этот проект раздвоился.