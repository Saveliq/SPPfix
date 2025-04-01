# SPP Installer Script

Этот скрипт предназначен для распаковки ISO-файлов SPP, импорта сертификатов и запуска утилиты `launch_sum.bat`.

## Функционал
- Автоматическая распаковка ISO-файла (или работа с уже распакованной папкой)
- Импорт GPG-ключей для проверки пакетов RPM
- Запуск `clean_cache.bat` (по выбору пользователя)
- Запуск `launch_sum.bat` с параметром `/open_firewall` (по выбору пользователя)
- Логирование всех действий

## Установка и настройка

### 1. Установка Python и зависимостей

Если Python не установлен, скачайте и установите его с [официального сайта](https://www.python.org/downloads/).

Создайте виртуальное окружение и установите зависимости:

```sh
python -m venv venv
source venv/bin/activate  # для Linux/macOS
venv\Scripts\activate  # для Windows
pip install -r requirements.txt
### 2. Запуск скрипта python
```sh
run_spp.py

## Сборка .exe

Для создания исполняемого файла (`.exe`) используйте `pyinstaller`:
```sh
pip install pyinstaller
pyinstaller --onefile --noconsole run_spp.py

Готовый `.exe` файл появится в папке `dist`.

## Возможные ошибки

1. **Ошибка "pyinstaller: command not found"**  
   Убедитесь, что `pyinstaller` установлен в виртуальном окружении:
```sh
pip install pyinstaller

2. **Ошибка "Файл не найден" при распаковке ISO**  
Проверьте, содержит ли путь к файлу пробелы. Если да, попробуйте указать путь в кавычках.

3. **Ошибка сертификатов GPG**  
Проверьте, были ли ключи успешно импортированы и не повреждены ли файлы ключей.

## Лицензия

Этот проект распространяется под лицензией MIT.
