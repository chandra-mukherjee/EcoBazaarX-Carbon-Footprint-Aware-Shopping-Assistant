EcoBazaarX

EcoBazaarX is a complete full-stack e-commerce application designed for selling environmentally friendly products. The platform also includes carbon impact awareness features and an administration system with different user roles.

Technology Stack

Frontend: React (Create React App), React Router, Axios, Recharts

Backend: Spring Boot, Spring Security with JWT authentication, Spring Data JPA

Database: MySQL

Authentication: JWT along with OTP-based password recovery through email (SMTP)

Project Directory Layout
EcoBazaarX/
  Backend/
    SignupForm/
      SignupForm/        # Backend built with Spring Boot
  Frontend/              # Frontend built with React
Key Features

Secure user registration and login using JWT authentication

Password recovery and reset through OTP sent via email

Product listing with search functionality and detailed product pages

Shopping cart system, checkout process, and order management APIs

Carbon footprint tracking and eco-related insights

Admin panel for managing users, products, and viewing system statistics

Role-based access control for both routes and APIs (USER, ADMIN)

Requirements

Make sure the following are installed before running the project:

Node.js (version 18 or higher) and npm

MySQL version 8 or later

JDK 25 (recommended for compatibility with the Maven configuration)

Maven Wrapper (included in the project as mvnw.cmd)

Backend Setup (Spring Boot)

Navigate to the backend folder:

cd Backend\SignupForm\SignupForm

Modify the file src/main/resources/application.properties with your configuration:

spring.datasource.url (default database: LoginDetails)

spring.datasource.username

spring.datasource.password

spring.mail.username

spring.mail.password

Start the backend server:

mvnw.cmd spring-boot:run

Backend will run at:

http://localhost:8080
Frontend Setup (React)

Go to the frontend directory:

cd Frontend

Install the required packages:

npm install

Start the React application:

npm start

Frontend will run at:

http://localhost:3000

The API base URL is configured in:

src/config/api.js
export const API_BASE_URL = "http://localhost:8080";
Important API Endpoints

Authentication: /api/auth/*

signup

login

forgot password

reset password

Products:
/api/products
/api/product/{id}
/api/products/search

Cart: /api/cart/* (USER role required)

Orders: /api/orders/* (USER role required)

Recommendations: /api/recommendations/* (USER role required)

Admin APIs: /api/admin/* (ADMIN role required)

Running Tests

Backend tests:

cd Backend\SignupForm\SignupForm
mvnw.cmd test

Frontend tests:

cd Frontend
npm test
Additional Information

The backend CORS configuration allows frontend requests from localhost ports 3000, 3001, and 5173.

Replace the database and email credentials with your own before running the application.

Avoid committing node_modules and compiled build files to version control.
