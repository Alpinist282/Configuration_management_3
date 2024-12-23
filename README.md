# Configuration_management_3
Проект представляет собой инструмент для парсинга пользовательских конфигурационных файлов и преобразования их в формат TOML. Этот проект написан на Python и предоставляет ряд функциональных возможностей, таких как работа с многострочными комментариями, объявлением констант, выполнением арифметических операций в постфиксной записи и обработкой словарей.

## Описание проекта
Этот проект предназначен для упрощения работы с конфигурационными файлами, предоставляя возможность легко преобразовать пользовательский язык конфигурации в формат TOML. Основные возможности включают:

Удаление многострочных комментариев: Комментарии удаляются с использованием синтаксиса {{!-- комментарий --}}.
Создание и использование констант: Константы объявляются с помощью команды set имя = значение;.
Поддержка постфиксных выражений: Поддерживается выполнение арифметических операций (+, -, abs) над значениями в постфиксной нотации (@{константа операция}).
Работа со словарями: Словари определяются с помощью конструкции table([имя = значение, ...]) и затем преобразуются в формат TOML.
## Установка
Чтобы установить проект, необходимо выполнить следующие шаги:

## Склонировать репозиторий:
```
git clone https://github.com/yourusername/Configuration_Management_Practice_3.git
cd Configuration_Management_Practice_3
```
Создать и активировать виртуальное окружение:
Для Linux/Mac:
```
python -m venv .venv
source .venv/bin/activate
```
Для Windows:

```.venv\Scripts\activate```

## Использование
После установки проекта его можно запустить следующим образом:

```
cat web.txt | python script.py
```
где web.txt — это входной файл с конфигурацией.

## Пример
Рассмотрим пример входного файла web.txt:

```
{{!-- Конфигурация веб-сервера --}}
set port = 8080;
set timeout = @{port 20 +};

table([
    name = "WebServer",
    port = @{port},
    timeout = @{timeout}
])
```
При запуске команды:

```cat web.txt | python script.py```
ожидается следующий результат:

```
[table_0]
name = "WebServer"
port = 8080
timeout = 8100
```
## Тестирование
Для тестирования проекта используется модуль unittest. Запустить тесты можно следующей командой:

```python -m unittest unit_tests.py```
Тесты охватывают ключевые аспекты проекта, включая удаление комментариев, обработку констант, вычисление выражений и преобразование в TOML-формат. При успешном прохождении всех тестов будет выведен отчет о количестве выполненных тестов и времени выполнения.

## Заключение
Configuration Management Practice 3 является полезным инструментом для обработки конфигураций и их преобразования в удобный для чтения формат TOML. Он предлагает гибкий набор функций, позволяющий работать с различными элементами конфигурационных файлов, такими как комментарии, константы и выражения.








