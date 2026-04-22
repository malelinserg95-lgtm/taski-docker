FROM node:18-alpine

# Рабочая директория внутри контейнера
WORKDIR /app

# Копируем только package.json и lock-файл
COPY package*.json ./

# Устанавливаем зависимости
RUN npm install

# Копируем остальной код
COPY . .

# Собираем проект (создаст /app/build)
RUN npm run build

# Устанавливаем простой сервер для статики
RUN npm install -g serve

# Открываем порт
EXPOSE 8000

# Запуск сервера
CMD ["serve", "-s", "build", "-l", "8000"]