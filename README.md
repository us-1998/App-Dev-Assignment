Python API's Assignment

 Welcome to the Python API’s Assignment! This project demonstrates an Android application built with Kotlin for user authentication, including features such as user signup, login, and a "Forgot Password" feature. It integrates with a Django REST API for backend operations, ensuring seamless user management and password recovery via email.

Features
User Authentication
User Signup:


Users can create a new account by providing an email, username, and password.
User Login:


Existing users can log in using their credentials (email and password).
Forgot Password
Password Recovery via Email:
Users can retrieve their forgotten password by entering their email. A password reset link is sent to their email via Outlook SMTP integration.
Django REST API Integration
The backend, developed using Django, handles user authentication, email functionality, and password management.
API endpoints facilitate user registration, login, and password recovery.

How It Works
User Signup:


The user enters their details (email, username, password) to register for a new account.
User Login:


After registration, users can log in using their email and password.
Forgot Password:


If the user forgets their password, they can request a password reset. The backend sends a password reset link via email.
Backend API:


The app interacts with the Django backend to perform user-related operations, including authentication and sending email notifications.

Visual Highlights
Signup Screen:


A simple and intuitive screen for user registration where users input their email, username, and password.
Login Screen:


Users log in by entering their registered email and password.
Forgot Password Screen:


Users can reset their password by entering their email to receive a password recovery link.
Backend API Integration:


Retrofit is used to handle API requests for signup, login, and password recovery.

Tech Stack
Frontend (Android App):


Language: Kotlin
UI Framework: XML-based layouts
Libraries: Retrofit for HTTP requests, OkHttp for network logging
Authentication: Firebase Auth for handling user login and registration
Backend (Django API):


Framework: Django (Python)
Database: SQLite (can be replaced with other relational databases)
Email Backend: Outlook SMTP (via Django Email settings)
API Libraries: Django Rest Framework (DRF)

Prerequisites
Backend Requirements:
Python 3.8+
Django 3.0+
Install dependencies using pip install -r requirements.txt.
SMTP Settings for Email Functionality:
Configure the email backend for sending password recovery emails. Example settings for Outlook in settings.py:
EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
EMAIL_HOST = 'smtp.office365.com'
EMAIL_PORT = 587
EMAIL_USE_TLS = True
EMAIL_HOST_USER = '<your_outlook_email>'
EMAIL_HOST_PASSWORD = '<your_password>'
DEFAULT_FROM_EMAIL = '<your_outlook_email>'


Setup Instructions
Backend Setup
Clone the repository:

 git clone https://github.com/us-1998/App-Dev-Assignment.git
cd <backend_directory>


Run migrations:

 python manage.py makemigrations
python manage.py migrate


Start the server:

 python manage.py runserver


Ensure the backend API is reachable at:

 http://192.168.100.102:8000/api/


Frontend Setup
Open the project in Android Studio.


Update the base URL in the RetrofitInstance.kt:

 const val BASE_URL = "http://192.168.100.102:8000/api/"


Build and run the app on an emulator or physical device.



API Endpoints
Signup:


Endpoint: POST /api/users/signup/
Request Body:
 { "email": "example@example.com", "username": "user", "password": "password123" }


Login:


Endpoint: POST /api/users/login/
Request Body:
 { "email": "example@example.com", "password": "password123" }


Forgot Password (Retrieve Password):


Endpoint: POST /api/users/forgot/
Request Body:
 { "email": "example@example.com" }



Key Files
Backend
views.py: Handles API logic, including sending emails.
models.py: Defines the user schema.
urls.py: Defines API routes.
settings.py: Configures email backend and database.
Frontend
ForgotPasswordActivity.kt: Implements the "Forgot Password" feature.
LoginActivity.kt and SignupActivity.kt: Handle login and signup processes.
RetrofitInstance.kt: Configures Retrofit for API calls.

Notes
Ensure that the backend server runs on the same network as the Android device or emulator.
For production, use HTTPS instead of HTTP for secure communication.
Update SMTP credentials to match your email provider (e.g., Gmail, Outlook, etc.).

License
This project is licensed under the MIT License. Feel free to use and modify as needed.

Submitted By:

SWEN221101044
USMAN SHAMS
