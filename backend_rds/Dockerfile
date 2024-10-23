# Используем базовый образ Python
FROM python:3.9

# Устанавливаем рабочую директорию
WORKDIR /app

# Копируем все файлы проекта в контейнер
COPY . /app

# Устанавливаем зависимости для PostgreSQL
# RUN apt-get update && apt-get install -y libpq-dev gcc

# Устанавливаем зависимости из requirements.txt
RUN pip install -r requirements.txt

# Открываем порт для приложения
EXPOSE 8001

# Команда для запуска приложения
CMD ["python", "manage.py", "runserver", "0.0.0.0:8001"]
