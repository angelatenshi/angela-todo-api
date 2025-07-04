# Laravel Todo API
Hello, this is Angela! Here is my simple and clean Laravel-based Todo API. I've built this as part of my technical assessment for Adaca. It supports basic CRUD functionality and an added ONE bonus feature: search by title.

No frontend, no frills — just a solid backend API that does what it’s supposed to from the PDF requirement.

## Setup Instructions
1. My project is Laravel 12 and it requires:
   ```
   PHP 8.2 or higher. Mine is PHP 8.4.
   You can check your php version by running php -v
   ```
2. Clone this repository:
   ```
   git clone https://github.com/your-username/angela-todo-api.git
   cd angela-todo-api
   ```
3. Install dependencies (Important):
   ```
   composer install
   ```
4. Create a `.env` file (Important):
   ```
   cp .env.example .env
   ```
5. Generate your app key (Important):
   ```
   php artisan key:generate
   ```
6. Set up the database (Important):
   - In your `.env`, configure SQLite:
     ```
     DB_CONNECTION=sqlite
     DB_DATABASE="absolute/path/to/database.sqlite"
     ```
     Replace the path with your actual full path to the SQLite file (use forward slashes).
     Mine was "DB_DATABASE="C:/Users/Angela Mae Villamar/angela-todo-api/database/database.sqlite".

   - Create the SQLite file:
     ```
     touch database/database.sqlite   # or create it manually on Windows
     ```
7. Run migrations:
   ```
   php artisan migrate
   ```
8. Serve the app:
   ```
   php artisan serve
   ```
If the installation doesn't work on your end, kindly contact me through my personal email. I will galdly help.


## How to Run the Project
Once the server is running, the base URL will typically be:
http://127.0.0.1:8000

```
Your API routes will be available under:
http://127.0.0.1:8000/api

```

## API Endpoints
I tested these by running php artisan route:list, 
try it on your end to make sure the API routes are working. 

| Method | Endpoint             | Description             |
|--------|----------------------|-------------------------|
| GET    | /api/todos           | List all todos          |
| POST   | /api/todos           | Create a new todo       |
| PUT    | /api/todos/{id}      | Update completed status |
| DELETE | /api/todos/{id}      | Delete a todo           |


## Bonus Feature
I added ONE optional function — **search by title**. 

Example:
```
GET /api/todos?search=buy
```
This will return all todos with "buy" in the title.


## How to Test with Postman
### Headers (for all requests):
```
Content-Type: application/json
Accept: application/json
```
### 1. Create a Todo
- Method: `POST`
- URL: `http://127.0.0.1:8000/api/todos`
- Body:
```json
{
  "title": "Buy myself a necklace"
}
```
### 2. List All Todos
- Method: `GET`
- URL: `http://127.0.0.1:8000/api/todos`

### 3. Search Todos by Title
- Method: `GET`
- URL: `http://127.0.0.1:8000/api/todos?search=buy`

### 4. Update Todo Completion
- Method: `PUT`
- URL: `http://127.0.0.1:8000/api/todos/1`
- Body:
```json
{
  "completed": true
}
```
### 5. Delete a Todo
- Method: `DELETE`
- URL: `http://127.0.0.1:8000/api/todos/1`

---

That's all for me. I hope you guys like my work. Happy testing!
