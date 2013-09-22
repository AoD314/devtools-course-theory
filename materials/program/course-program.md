# Примерная программа курса

## Личное мастерство

  01. Текстовые форматы [Кирилл Корняков]
      - Текстовый и бинарный формат, сравнение
      - Популярные форматы на основе текстового: txt, xml, yaml, json
      - Текст как исходник: scripts, GraphVis, PlantUML, latex, doxygen
      - Легковесные языки разметки: Markdown, Textile, MediaWiki, ReST
      - Markdown: Wiki, книги, Slides, Web-publishing (Jekyll)

  01. Обработка текста / Текстовые редакторы [Кирилл Корняков]
      - Редакторы: vim, Emacs, Sublime
      - Манипуляции (навигация, сортировка, сниппеты и макросы)
      - Regular expressions
      - Утилиты командной строки (find, grep, sed, awk, head/tail/less)

  01. Автоматизация: командная строка и скриптовые языки
      - UNIX philosophy
      - Bash (cron, watch), other shells, настройка под себя, Tilda
      - Python (xml, excel, pdf, matplotlib)
      - Анонс: make, unit-testing, CI

  01. Рабочее место программиста
      - 4 кита: браузер, файл-менеджер, текстовый редактор, консоль, [IDE]
      - Браузер: облачные сервисы (почта, документы), StackOverflow, Google
      - Файл-менеджер: FTP, копирование путей, быстрая навигация
      - Cинхронизаторы директорий (Google Drive, BitTorrent Sync)
      - Искалки и запускалки
      - Other: файловые шары, виртуальные машины

  01. Системы контроля версий
      - Введение и история
      - Subversion, Mercurial
      - Git как DVCS и не только
      - Примеры хуков
      - Тренинг (книга Pro Git)

## Работа с кодом

  01. Написание кода, создание "проектов"
      - IDE с последними функциями (подсветка, автозавершение)
      - Автогенерация кода, метапрограммирование
      - Билд-системы
        - IDE
        - Makefiles
        - CMake
        - Other: Rake, scons, waf

  01. Построение исполняемых модулей
      - Обзор: компиляторы + линкеры, трансляторы, виртуальные машины
      - GNU toolchain, понятие кросс-компиляции
      - Компиляторы
        - MSVS
        - GCC, clang, LVVM

  01. Анализ бинарных модулей
      - Статическая и динамическая линковка
      - Зависимости
      - API, binary compatibility
      - Дизассемблирование

## Качество кода

  01. Качество кода
      - IDE + modern refactoring features
      - Системы для документирования кода (Sphinx, Doxygen)
      - Статический и динамический анализ кода
      - Отладка
        - Логирование (`printf`)
        - Отладчики

  01. Тестирование
      - Системы для написания Unit-тестов
        - GoogleTest
        - JUnit (XML format)
      - Системы непрерывной интеграции
        - BuildBot
        - Jenkins
        - GitHub (TravisCI)

  01. Профилирование и оптимизация производительности [Иосиф Мееров]
      - Замеры времени
      - Техники оптимизации
        - устранение проблемы или вызов библиотек
        - алгоритмическая
        - общие техники
        - векторизация
        - многопоточность (по данным, по задачам)
        - многопроцессность

## Коллективная разработка

  01. Коллективная разработка
      - Примеры Git workflow
      - Трекеры задач (Redmine, Trac, Bugzilla)
      - Инструменты для peer review (Gerrit)
      - GitHub (GitLab), Bitbucket, other (Code Google, SourceForge)

  01. Формирование сообщества
      - Листы рассылки
      - Форумы, Q&A
      - UserEcho
      - Социальные сети

# Практика

Разработка кросс-платформенной библиотеки на С++, с Sphinx документацией и CTest
и GoogleTest тестами, построением при помощи make и CMake, и автоматическими
прогонами тестов при помощи TravisCI.

Каждая новое задание дается через 2 недели. Итого, через 10-12 недель все должно
быть сдано.

  1. Клонировать проект на GitHub, создать README в формате Markdown. Там 
     должны присутствовать следующие секции: 
     - Тема лабораторной работы
     - Информация об авторе
     - Объяснение раскладки по подпапкам в виде списка
     - Перечисление возможностей проекта
  1. Проектирование
     - Разработать интерфейс класса (hpp-файл)
     - Задокументировать его в стиле Sphinx, см. заготовку:
       [исходник](https://raw.github.com/UNN-VMK-Software/devtools-course/master/code/kirill-kornyakov/docs/simplecalc.rst),
       [результат](https://devtools.readthedocs.org/ru/latest/)
     - Можно:
       - PlantUML попробовать прикрутить
       - Еще и Doxygen поднять
  1. Реализация
     - Реализовать класс, поместить его в библиотеку (статическую?).
     - Добавить тестирующее консольное приложение, которое проверяло бы класс на
       нескольких наборах данных, в том числе некорректных.
     - Организовать построение при помощи make.
     - Убедиться, что присланный пулл-реквест проходит построение на TravisCI.
  1. Интеграция
     - Добавить построение при помощи CMake
     - Добавить несколько тестов на CTest
     - Обеспечить запуск в рамках инфраструктуры TravisCI
     - Убедиться что пулл-реквест зеленый
  1. Тестирование (возможно стоит поменять с предыдущим пунктом)
     - Добавить unit-тесты с использованием фреймворка GoogleTest, обеспечить их
       запуск и выполнение в рамках общего тестирования TravisCI

Возможно:

  1. Можно парсить XML-вывод от GoogleTest
  1. Добавить генерацию Java и Python интерфейсов
  1. Задачка на обработку текстовой информации в консоли,
     можно просто взять что-то из awk и sed oneliners