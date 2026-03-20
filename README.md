# 🛍️ L'Oréal Vue Storefront

A full-stack product catalog application built with **Vue 3** on the frontend and **Node.js + Express** on the backend, developed as part of the L'Oréal-sponsored software development program at Universidad de la Costa.

## 🧰 Tech Stack

| Layer     | Technology              |
|-----------|-------------------------|
| Frontend  | Vue 3 (Composition API) |
| Backend   | Node.js + Express       |
| Styling   | CSS nativo              |
| HTTP      | Fetch API               |
| Dev tools | Vite, Nodemon           |

---

## 📁 Project Structure

```
loreal-vue-storefront/
├── backend-api/
│   ├── index.js
│   ├── package.json
│   ├── src/
│   │   ├── app.js
│   │   └── routes/
│   │       └── productos.routes.js
│   └── public/
│       └── imagenes/
│           └── productos/        ← static product images
└── frontend-vue/
    └── src/
        └── App.vue
```

---

## 🚀 Getting Started

### Prerequisites

- Node.js v18 or higher
- npm v9 or higher

---

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/loreal-vue-storefront.git
cd loreal-vue-storefront
```

---

### 2. Run the Backend

```bash
cd backend-api
npm install
npm run dev
```

The API will be available at: `http://localhost:3000`

| Endpoint                          | Description              |
|-----------------------------------|--------------------------|
| `GET /api/productos`              | Returns all products     |
| `GET /imagenes/productos/:file`   | Serves a product image   |

---

### 3. Run the Frontend

Open a new terminal:

```bash
cd frontend-vue
npm install
npm run dev
```

The app will be available at: `http://localhost:5173`

---

## ✨ Features

- REST API built with Express serving product data as JSON
- Vue 3 frontend consuming the API with `fetch`
- Static image serving from the Express backend
- Smart URL builder — works with both local and public APIs
- Basic error handling for failed requests

---

## 👨‍💻 Author

**Jonathan** — Systems Engineering Student· L'Oréal Sponsored Program  

---

## 📄 License

This project was developed for educational purposes as part of a sponsored full-stack development workshop.