# Chess32bot

Chess32bot - это многопользовательский Telegram-бот для игры в шахматы на основе веб-приложения. Он позволяет пользователям играть в шахматы с случайными соперниками или друзьями. В будущем в планах развития проекта - добавление функционала подписки, отслеживание статистики (история игр, победы, поражения, рейтинг Elo) и анализ партий.

## Содержание
1. [Структура проекта](#структура-проекта)
2. [Требования](#требования)
3. [Установка](#установка)
4. [Использование](#использование)
5. [Лицензия](#лицензия)

### Структура проекта

Проект организован в следующие директории и файлы:

- `bootstrap.py`: Точка входа в проект.
- `build/`: Содержит HTML-файл веб-приложения.
- `config.py`: Файл конфигурации проекта.
- `config.yaml`: Файл конфигурации в формате YAML.
- `db_api/`: Каталог для модулей, связанных с базой данных.
- `engine/`: Содержит модули и классы для логики игры и сессий.
- `handlers/`: Обработчики бота Telegram.
- `websocket/`: Модули для поддержки WebSocket-соединений.
- `states/`: Модули управления состояниями бота.
- `utils.py`: Утилитарные функции.
- `main.py`: Основной скрипт для запуска бота Telegram.
- `requirements.txt`: Список зависимостей проекта.
- `router.py`: Регистрация обработчиков бота Telegram.
- `routes.py`: Маршруты для доступа к веб-приложению.
- `settings.py`: Настройки проекта.

### Требования

Для запуска проекта Chess32bot вам потребуется следующее:

- Python 3.10
- Система управления базами данных PostgreSQL
- Веб-сервер с поддержкой HTTPS (например, Apache)
- Git

### Установка

1. Установите Python 3.10, PostgreSQL и Git на вашем сервере.
2. Клонируйте репозиторий:
   ```git clone https://github.com/вашеимяпользователя/chess32bot.git```
3. Создайте виртуальное окружение:
   ```python -m venv venv```
4. Активируйте виртуальное окружение:
  ```source venv/bin/activate```
5. Установите зависимости проекта:
   ```pip install -r requirements.txt```
6. Настройте вашу базу данных PostgreSQL и обновите файл `config.yaml` с необходимыми учетными данными для базы данных.
7. Настройте ваш веб-сервер (например, Apache) для поддержки HTTPS. Вот пример конфигурации виртуального хоста Apache для HTTPS:
     ```
     <VirtualHost *:443>
        ServerName chess32.xyz
        ProxyPreserveHost On
        ProxyPass /wss/ ws://localhost:80/
        ProxyPassReverse /wss/ ws://localhost:80/
        ProxyPass /.well-known/acme-challenge !
        ProxyPass / http://localhost:8080/
        ProxyPassReverse / http://localhost:8080/
        SSLEngine on
        SSLCertificateFile /etc/ssl/chess32_xyz.crt
        SSLCertificateKeyFile /etc/ssl/rsa_key
        SSLCertificateChainFile /etc/ssl/chess32_xyz.ca-bundle
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/html
        ErrorLog ${APACHE_LOG_DIR}/error.log
       CustomLog ${APACHE_LOG_DIR}/access.log combined
   </VirtualHost>```
### Использование
### Лицензия
