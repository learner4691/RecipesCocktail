# Coctails App

## Описание

Полнофункциональное MERN-приложение для публикации, просмотра, оценки и управления рецептами коктейлей.

---

## Функционал

### Пользователи:
- Регистрация с email, username и ролью (`user`, `admin`)
- Вход с валидацией
- Отображение уведомлений (Snackbar)
- Разделение доступа: только админы — опубликовывать/удалять коктейли

### Коктейли:
- Просмотр списка всех опубликованных коктейлей
- Просмотр деталей с рецептом, ингредиентами
- Голосование за рецепт (1–5 звёзд)
- Добавление, удаление, публикация (в зависимости от роли)
- Страница "Мои коктейли" — отображает только рецепты текущего пользователя

---

## Стек технологий

### Frontend:
- **React** + **Redux**
- **Material UI**
- **React Router v6**
- **Axios**
- **JWT авторизация**
- **ProtectedRoute** для защиты маршрутов
- **Рейтинг и сортировка**
- **Snackbar-уведомления**

**Структура компонентов:**
  - `App` — корневой компонент с роутами и layout'ом
  - `Register`, `Login` — формы регистрации и авторизации
  - `Coctails`, `MyCoctails`, `CoctailDetails`, `NewCoctail` — основная бизнес-логика
  - `UserForm`, `Loader`, `Rating`, `HasAccess`, `AppToolbar` — вспомогательные UI-компоненты

### Backend:
- **Node.js** + **Express**
- **MongoDB** (mongoose)
- **JWT**
- **Multer** (загрузка изображений)

- Поддержка CRUD операций для коктейлей и пользователей
- Хранение изображений и маршруты API:
  - `POST /users` — регистрация
  - `POST /users/sessions` — логин
  - `POST /coctails`, `GET /coctails`, `GET /coctails/:id`, `DELETE /coctails/:id`, `PATCH /coctails/:id/publish`, `POST /coctails/:id/rate`

### 🛡 Роли
- `user` (по умолчанию)
- `admin` (password: "admin") может опубликовывать и удалять любые коктейли.
---

### 🌐 Порты
- **Frontend**: [http://localhost:3000](http://localhost:3000) (по умолчанию для Create React App)
- **Backend**: [http://localhost:8000](http://localhost:8000) (для API)

## 📁 Структура проекта

```bash
├── backend/                  # Серверная часть (Express + MongoDB)
│   ├── models/               # Mongoose-модели
│   ├── routes/               # Маршруты Express
│   ├── middleware/           # Middleware-функции (авторизация и др.)
│   ├── public/uploads/       # Загруженные изображения
│   ├── server.js             # Точка входа сервера (Express + MongoDB)
│   ├── fixtures.js           # Генерация начальных данных
│   ├── utils/                # Вспомогательные утилиты

├── frontend/                 # Клиентская часть (React)
│   ├── public/
│   │   └── images/           # Изображения для фронтенда
│   ├── src/
│   │   ├── components/       # Компоненты 
│   │   ├── containers/       # Основные страницы
│   │   ├── store/            # Redux store, экшн и редюсеры
│   │   ├── utils/            # Вспомогательные функции
│   │   ├── App.js            # Главный компонент приложения
│   │   ├── axiosCoctail.js   # Настройка axios для API
│   │   ├── constants.js      # Константы проекта
│   │   ├── index.css         # Глобальные стили приложения
│   │   └── index.js          # Точка входа React-приложения, подключение Redux и маршрутизации
│   └── README.md
```

## Установка и запуск

```bash
# Клонирование репозитория
git clone https://github.com/learner4691/RecipesCocktail.git

# Корневая директория проекта
cd RecipesCocktail

# Инициализация сабмодулей (frontend и server)
git submodule update --init --recursive

# Установка зависимостей и запуск Backend
cd "COCTAIL(server)"
npm install
npm start

# Новое окно в bash
# Корневая директория проекта
cd RecipesCocktail

# Установка зависимостей и запуск Frontend
cd "COCTAIL(frontend)"
npm install
npm start

📄 Лицензия 
Этот проект распространяется без лицензии и предназначен для свободного использования в учебных целях.
