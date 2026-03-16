# EcoBazaarX

EcoBazaarX is a full-stack e-commerce platform focused on eco-friendly products, carbon-aware shopping, and role-based administration.

## Tech Stack

- Frontend: React (CRA), React Router, Axios, Recharts
- Backend: Spring Boot, Spring Security (JWT), Spring Data JPA
- Database: MySQL
- Auth: JWT + OTP-based password reset via email (SMTP)

## Project Structure

```text
EcoBazaarX/
  Backend/
    SignupForm/
      SignupForm/        # Spring Boot backend
  Frontend/              # React frontend
```

## Core Features

- User signup/login with JWT authentication
- Forgot/reset password using OTP email flow
- Product catalog with search and product details
- Cart, checkout, and order APIs
- Carbon impact data model and eco insights
- Admin modules for users, products, and overview dashboards
- Role-based route/API protection (`USER`, `ADMIN`)

## Prerequisites

- Node.js 18+ and npm
- MySQL Workbench
- JDK 25 (recommended for current Maven compiler config)
- Maven Wrapper (already included as `mvnw.cmd`)

## Backend Setup (Spring Boot)

Working directory:

```bash
cd Backend\SignupForm\SignupForm
```

Update `src/main/resources/application.properties`:

- `spring.datasource.url` (default DB: `LoginDetails`)
- `spring.datasource.username`
- `spring.datasource.password`
- `spring.mail.username`
- `spring.mail.password`

Start backend:

```bash
mvnw.cmd spring-boot:run
```

Default backend URL: `http://localhost:8080`

## Frontend Setup (React)

Working directory:

```bash
cd Frontend
```

Install dependencies:

```bash
npm install
```

Run frontend:

```bash
npm start
```

Default frontend URL: `http://localhost:3000`

`src/config/api.js` currently points to:

```js
export const API_BASE_URL = "http://localhost:8080";
```

## Main API Areas

- Auth: `/api/auth/*` (`signup`, `login`, `forgot`, `reset`)
- Products: `/api/products`, `/api/product/{id}`, `/api/products/search`
- Cart: `/api/cart/*` (USER role)
- Orders: `/api/orders/*` (USER role)
- Recommendations: `/api/recommendations/*` (USER role)
- Admin: `/api/admin/*` (ADMIN role)


## Recommended SQL Commmands:

create database logindetails;
use logindetails;
#drop table products;
select * from users;
select * from products;
select * from orders;
select * from order_items;
#ALTER TABLE users ADD role VARCHAR(20) NOT NULL;
DELETE FROM orders WHERE id = 1;
DELETE FROM order_items WHERE id = 1;
DELETE FROM orders WHERE id = 6;
TRUNCATE TABLE orders;
select * from addresses;
select * from shipping;
select * from cart_items;
select * from carts;
select * from wishlist_items;
UPDATE users SET role = 'ADMIN' where id=3;


DELETE FROM users WHERE id = 2;

show databases;



## Notes

- CORS in backend allows localhost frontend origins (`3000`, `3001`, `5173`).
- Replace placeholder DB/mail credentials before running in your environment.
- Keep `node_modules` and build output out of version control.

## Recommended SQL Commands

CREATE DATABASE logindetails;
USE logindetails;

-- DROP TABLE products;

SELECT * FROM users;
SELECT * FROM products;
SELECT * FROM orders;
SELECT * FROM order_items;

-- ALTER TABLE users ADD role VARCHAR(20) NOT NULL;

DELETE FROM orders 
WHERE id = 1;

DELETE FROM order_items 
WHERE id = 1;

DELETE FROM orders 
WHERE id = 6;

TRUNCATE TABLE orders;

SELECT * FROM addresses;
SELECT * FROM shipping;
SELECT * FROM cart_items;
SELECT * FROM carts;
SELECT * FROM wishlist_items;

UPDATE users 
SET role = 'ADMIN' 
WHERE id = 3;

DELETE FROM users 
WHERE id = 2;

SHOW DATABASES;

