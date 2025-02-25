# Wardrobe Management System

A full-stack wardrobe management system built using Vue 3 (frontend) and Laravel 11 (backend). The system allows users to authenticate, add, edit, delete, categorize clothing items, and filter/search through them efficiently.

## Features
- User authentication (Login/Registration)
- Add, edit, and delete clothing items
- Categorize items (e.g., tops, bottoms, shoes)
- Filter and search functionality
- Responsive and user-friendly UI

---

## Setup Instructions

### Prerequisites
Ensure you have the following installed on your Ubuntu system:
- PHP 8.2+
- Composer
- MySQL
- Node.js 18+
- NPM
- Vue CLI

### Backend (Laravel 11)

#### 1. Clone the repository
```bash
git clone https://github.com/your-repo/wardrobe-management.git
cd wardrobe-management/backend
```

#### 2. Install dependencies
```bash
composer install
```

#### 3. Configure environment variables
Copy the example environment file and update your database credentials:
```bash
cp .env.example .env
```
Edit `.env` file to match your database setup:
```ini
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=wardrobe_db
DB_USERNAME=root
DB_PASSWORD=your_password
```

#### 4. Generate application key
```bash
php artisan key:generate
```

#### 5. Run migrations
```bash
php artisan migrate
```

#### 6. Start the Laravel server
```bash
php artisan serve
```
The backend will be available at `http://127.0.0.1:8000`

---

### Frontend (Vue 3)

#### 1. Move to the frontend directory
```bash
cd ../frontend
```

#### 2. Install dependencies
```bash
npm install
```

#### 3. Configure API base URL
Edit `src/api.js`:
```javascript
import axios from "axios";
const api = axios.create({
  baseURL: "http://127.0.0.1:8000/api",
  withCredentials: true,
});
export default api;
```

#### 4. Start the Vue development server
```bash
npm run dev
```
The frontend will be available at `http://localhost:5173`

---

## API Endpoints

### Authentication
- `POST /api/register` - Register new users
- `POST /api/login` - Login users

### Clothing Management
- `GET /api/clothing` - Fetch all clothing items
- `POST /api/clothing` - Add a new item
- `PUT /api/clothing/{id}` - Update an item
- `DELETE /api/clothing/{id}` - Delete an item

---

## Deployment
### Backend (Laravel)
- Use Laravel Forge, DigitalOcean, or a VPS
- Configure `.env` with production database credentials
- Run migrations: `php artisan migrate --force`
- Set up a queue worker for background tasks

### Frontend (Vue 3)
- Deploy on Vercel, Netlify, or a static server
- Set API base URL to the deployed backend

---

## License
MIT License

---

## Author
Developed by [Your Name]

