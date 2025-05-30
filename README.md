# PWA Backend

## Project Description
This project is the backend for a Progressive Web Application (PWA) developed with NestJS. It provides a robust RESTful API with support for offline/online operations, JWT authentication, and data persistence using PostgreSQL.

## Prerequisites
- Node.js (v18.x or higher)
- PostgreSQL (v14.x or higher)
- npm (v9.x or higher)

## Installation

1. Clone the repository:
bash
git clone https://github.com/jefer15/pwa-backend.git
cd pwa-backend

2. Install dependencies:
npm install

## Running the Project

### Development
npm run start:dev

### Production
npm run build
npm run start:prod

### Debug
npm run start:debug

## Technologies Used

### Framework and Core
- *NestJS (v11.0.1)*: Progressive Node.js framework for building scalable and efficient server-side applications.
- *TypeScript*: Provides static typing and modern JavaScript features.

### Database and ORM
- *TypeORM (v0.3.24)*: ORM that facilitates interaction with the PostgreSQL database.
- *PostgreSQL (v8.16.0)*: Robust and reliable relational database management system.

### Authentication and Security
- *Passport.js*: Authentication middleware for Node.js.
- *JWT (JSON Web Tokens)*: Token implementation for stateless authentication.
- *bcrypt*: For secure password hashing.

### Validation and Transformation
- *class-validator*: For DTO validation.
- *class-transformer*: For object transformation.

## Project Structure

src/
├── auth/ # Authentication module
├── users/ # User module
├── task/ # Task module
├── config/ # Application configuration
└── main.ts # Application entry point