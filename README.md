# MCP Server

MCP сервер на Python, предоставляющий текущий курс доллара, прогноз погоды и новости за последнюю неделю.

## Установка

1. **Клонируйте репозиторий**:
   ```bash
   git clone https://github.com/Cavumnigrum/mcp_server_project.git
   cd mcp_server_project
   ```
2. **Создайте виртуальное окружение**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate     # Windows
   ```

3. **Установите зависимости**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Настройте API ключи**:
   - Зарегистрируйтесь на:
     - [exchangerate-api.com](https://www.exchangerate-api.com/) для курса доллара.
     - [openweathermap.org](https://openweathermap.org/) для погоды.
     - [newsapi.org](https://newsapi.org/) для новостей.
   - Скопируйте `.env.example` в `.env` и заполните своими ключами:
     ```bash
     cp .env.example .env
     ```
5. **Запустите сервер**:
   ```bash
   python mcp_server.py
   ```
   Сервер будет доступен по адресу `http://localhost:8000`.

## Тестирование

Запустите тесты с помощью `pytest`:
```bash
pytest test_mcp_server.py -v
```

## Подключение клиента

Самописный клиент:
```bash
python mcp_client.py
```
- При запуске клиента есть инструкция как им пользоваться

## Дополнительно
В репозитории есть docker-файлы для создания контейнеров.
Порядок работы с докер-файлами:
1. Убедиться, что установлены необходимые пакеты для docker и docker-compose
2. Перейти в папку с проектом
    ```bash
   cd path\to\project 
   ```
3. Запустить docker-compose файл в двух режимах для сервера и клиента
    ```bash
   docker-compose up -d server
   docker-compose run --rm client
   ```
4. После завершения работы можно уронить контейнеры с помощью
    ```bash
   docker-compose down server client 
   ```
