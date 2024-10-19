# Используем базовый образ Python
FROM python:3.8-slim

# Устанавливаем рабочую директорию
WORKDIR /app

# Копируем все файлы проекта в контейнер
COPY . /app

# Устанавливаем зависимости из requirements.txt
RUN pip install -r requirements.txt

# Открываем порт для приложения
EXPOSE 5000

# Команда для запуска приложения
CMD ["python", "manage.py", "runserver"]