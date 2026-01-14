# Task Manager API

A RESTful API for task management built with FastAPI, featuring JWT authentication and SQLAlchemy ORM.

## 📋 Overview

This Task Manager API provides a robust backend solution for managing tasks with user authentication. It's designed to be scalable, secure, and easy to integrate with frontend applications.

## ✨ Features

- **User Authentication**: Secure JWT-based authentication system
- **Task Management**: Create, read, update, and delete tasks
- **RESTful Design**: Clean and intuitive API endpoints
- **Database Integration**: SQLAlchemy ORM for efficient database operations
- **Fast Performance**: Built on FastAPI's high-performance framework
- **API Documentation**: Auto-generated interactive API docs with Swagger UI

## 🛠️ Technologies

- **[FastAPI](https://fastapi.tiangolo.com/)**: Modern, fast web framework for building APIs
- **[SQLAlchemy](https://www.sqlalchemy.org/)**: Python SQL toolkit and ORM
- **[JWT](https://jwt.io/)**: JSON Web Tokens for secure authentication
- **[Pydantic](https://pydantic-docs.helpmanual.io/)**: Data validation using Python type annotations
- **[Uvicorn](https://www.uvicorn.org/)**: ASGI server for running the application

## 📦 Prerequisites

Before running this project, make sure you have the following installed:

- Python 3.8 or higher
- pip (Python package manager)
- Virtual environment tool (venv or virtualenv)

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/kelvin-ads/task-manager-api-.git
   cd task-manager-api-
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   ```

3. **Activate the virtual environment**
   - On Windows:
     ```bash
     venv\Scripts\activate
     ```
   - On macOS/Linux:
     ```bash
     source venv/bin/activate
     ```

4. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

5. **Set up environment variables**
   
   Create a `.env` file in the root directory with the following variables:
   ```env
   DATABASE_URL=sqlite:///./task_manager.db
   SECRET_KEY=your-secret-key-here
   ALGORITHM=HS256
   ACCESS_TOKEN_EXPIRE_MINUTES=30
   ```

6. **Initialize the database**
   ```bash
   python -m app.database
   ```

## 🏃 Running the Application

Start the development server:

```bash
uvicorn app.main:app --reload
```

The API will be available at `http://localhost:8000`

## 📚 API Documentation

Once the application is running, you can access:

- **Swagger UI**: `http://localhost:8000/docs`
- **ReDoc**: `http://localhost:8000/redoc`

## 🔑 Authentication

The API uses JWT (JSON Web Tokens) for authentication. To access protected endpoints:

1. Register a new user or login with existing credentials
2. Obtain an access token from the response
3. Include the token in the Authorization header for subsequent requests:
   ```
   Authorization: Bearer <your-token-here>
   ```

## 🌐 API Endpoints

### Authentication
- `POST /auth/register` - Register a new user
- `POST /auth/login` - Login and receive JWT token

### Tasks
- `GET /tasks` - Get all tasks (authenticated)
- `GET /tasks/{id}` - Get a specific task (authenticated)
- `POST /tasks` - Create a new task (authenticated)
- `PUT /tasks/{id}` - Update a task (authenticated)
- `DELETE /tasks/{id}` - Delete a task (authenticated)

### Users
- `GET /users/me` - Get current user information (authenticated)

## 📁 Project Structure

```
task-manager-api-/
├── app/
│   ├── __init__.py
│   ├── main.py           # Application entry point
│   ├── database.py       # Database configuration
│   ├── models.py         # SQLAlchemy models
│   ├── schemas.py        # Pydantic schemas
│   ├── crud.py           # Database operations
│   ├── auth.py           # Authentication logic
│   └── routers/          # API route handlers
│       ├── __init__.py
│       ├── auth.py
│       ├── tasks.py
│       └── users.py
├── tests/                # Test files
├── requirements.txt      # Project dependencies
├── .env.example         # Environment variables template
├── .gitignore          # Git ignore rules
└── README.md           # This file
```

## 🧪 Testing

Run tests using pytest:

```bash
pytest
```

For coverage report:

```bash
pytest --cov=app tests/
```

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature-name`)
3. Make your changes
4. Commit your changes (`git commit -m 'Add some feature'`)
5. Push to the branch (`git push origin feature/your-feature-name`)
6. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Gilson Kelvin Arruda Sales**

- GitHub: [@kelvin-ads](https://github.com/kelvin-ads)

## 🙏 Acknowledgments

- FastAPI documentation and community
- SQLAlchemy team for the excellent ORM
- All contributors who help improve this project

---

⭐ If you find this project useful, please consider giving it a star on GitHub!
