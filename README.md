# Django + React Full-Stack Application

A full-stack web application combining Django backend with React frontend, featuring user authentication and a hybrid rendering approach.

## 🚀 Tech Stack

**Backend:**
- Django 5.2.8
- Python 3.11
- Django REST Framework (for API endpoints)

**Frontend:**
- React 18+
- React Router
- Modern JavaScript (ES6+)

## ✨ Features

- User authentication (login/register)
- Hybrid rendering: Django templates for static pages, React for dynamic components
- RESTful API endpoints
- Session-based authentication
- Responsive design

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- Python 3.11 or higher
- Node.js 16+ and npm
- Git

## 🛠️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/jk-austin/BestCars
cd BestCars
```

### 2. Backend Setup (Django)

#### Create and activate a virtual environment:

**On macOS/Linux:**
```bash
python3 -m venv djangoenv
source djangoenv/bin/activate
```

**On Windows:**
```bash
python -m venv djangoenv
djangoenv\Scripts\activate
```

#### Install Python dependencies:

```bash
pip install -r requirements.txt
```

#### Set up the database:

```bash
python manage.py migrate
```

#### Create a superuser (optional, for admin access):

```bash
python manage.py createsuperuser
```

### 3. Frontend Setup (React)

#### Navigate to the frontend directory:

```bash
cd frontend
```

#### Install Node dependencies:

```bash
npm install
```

#### Build the React app:

```bash
npm run build
```

This creates optimized production files in the `frontend/build/` directory.

#### Return to the project root:

```bash
cd ..
```

## 🚀 Running the Application

### Development Mode

#### Start the Django development server:

From the project root directory (with your virtual environment activated):

```bash
python manage.py runserver
```

The application will be available at `http://localhost:8000`

### Available Routes

- `http://localhost:8000/` - Homepage
- `http://localhost:8000/about/` - About page
- `http://localhost:8000/contact/` - Contact page
- `http://localhost:8000/login/` - Login (React component)
- `http://localhost:8000/register/` - Register (React component)
- `http://localhost:8000/admin/` - Django admin panel

## 📁 Project Structure

```
project-root/
├── frontend/
│   ├── public/
│   │   └── index.html          # React app entry point
│   ├── src/
│   │   ├── App.js              # Main React component with routing
│   │   ├── components/
│   │   │   ├── Login.jsx       # Login component
│   │   │   └── Register.jsx    # Register component
│   │   └── index.js
│   ├── package.json
│   └── build/                  # Generated after npm run build
├── templates/
│   ├── Home.html
│   ├── about.html
│   └── contact.html
├── djangoapp/                  # Django app with API endpoints
│   ├── views.py
│   ├── urls.py
│   └── models.py
├── manage.py
├── settings.py
├── urls.py
└── requirements.txt
```

## 🔧 Configuration

### Template Directories

The Django `TEMPLATES` setting includes:
```python
'DIRS': [
    os.path.join(BASE_DIR, 'frontend/static'),
    os.path.join(BASE_DIR, 'frontend/public'),
    os.path.join(BASE_DIR, 'frontend/build'),
    os.path.join(BASE_DIR, 'frontend/build/static'),
],
```

### Static Files

Static files are served from `frontend/build/static/` after running `npm run build`.

## 🧪 Development Workflow

### Making Frontend Changes

1. Navigate to the frontend directory: `cd frontend`
2. Make your changes to React components
3. Rebuild the app: `npm run build`
4. Return to root: `cd ..`
5. Refresh your browser to see changes

### Making Backend Changes

1. Make your changes to Django views, models, or URLs
2. Run migrations if models changed: `python manage.py makemigrations && python manage.py migrate`
3. The Django development server will auto-reload

## 📝 API Endpoints

  - `POST /djangoapp/login/` - User authentication
  - Request body: `{"userName": "string", "password": "string"}`
  - Response: `{"status": "Authenticated", "userName": "string"}`

## 🐛 Troubleshooting

### "TemplateDoesNotExist" Error
- Ensure you've run `npm run build` in the frontend directory
- Check that `TEMPLATES['DIRS']` in settings.py includes the correct paths

### Static Files Not Loading
- Run `python manage.py collectstatic` if in production
- Verify `STATIC_URL` and `STATIC_ROOT` settings

### React App Shows Blank Page
- Check browser console for errors
- Ensure React build completed successfully
- Verify React Router configuration matches Django URL patterns

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👤 Author

Jesse Korff - https://github.com/jk-austin

## 🙏 Acknowledgments

- Django documentation
- React documentation
- Create React App

---

**Note:** This is a demonstration project for portfolio purposes.
