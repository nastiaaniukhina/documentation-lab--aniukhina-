# API Overview

Демонстраційний REST API для застосунку "Task Manager".

## Base URL
https://api.demo-taskmanager.com

---

## Endpoints

### 1. Отримати список завдань (GET)

**Endpoint:**  
GET /tasks

ruby

**Приклад запиту:**
```http
GET https://api.demo-taskmanager.com/tasks
Приклад відповіді (JSON):

json
[
  {
    "id": 1,
    "title": "Закінчити звіт",
    "completed": false
  },
  {
    "id": 2,
    "title": "Презентація для клієнта",
    "completed": true
  }
]
Коди відповіді:

200 — успішно

404 — завдання не знайдено

500 — внутрішня помилка сервера

2. Створити нове завдання (POST)
Endpoint:

bash
POST /tasks
Приклад запиту (JSON):

json
{
  "title": "Підготувати звіт по API",
  "completed": false
}
Приклад відповіді (JSON):

json
{
  "id": 3,
  "title": "Підготувати звіт по API",
  "completed": false,
  "created_at": "2025-11-15T12:00:00Z"
}
Коди відповіді:

201 — створено успішно

400 — некоректні дані запиту

500 — внутрішня помилка сервера

3. Отримати деталі конкретного завдання (GET)
Endpoint:

bash
GET /tasks/{id}
Приклад запиту:

http
GET https://api.demo-taskmanager.com/tasks/3
Приклад відповіді (JSON):

json
{
  "id": 3,
  "title": "Підготувати звіт по API",
  "completed": false,
  "created_at": "2025-11-15T12:00:00Z"
}
Коди відповіді:

200 — успішно

404 — завдання з таким ID не знайдено

500 — внутрішня помилка сервера
