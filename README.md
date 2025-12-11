# MovieAPI - Full Stack Movie Application

A full-stack web application for browsing movies, reading and writing reviews, and watching trailers. Built with a React frontend and Spring Boot backend.

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Tech Stack](#tech-stack)
- [Features](#features)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Backend Setup](#backend-setup)
  - [Frontend Setup](#frontend-setup)
- [Environment Variables](#environment-variables)
- [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
- [Contributing](#contributing)
- [License](#license)

## 🎬 Project Overview

MovieAPI is a full-stack application that allows users to:
- Browse a collection of movies
- View detailed movie information
- Watch movie trailers
- Read and write movie reviews
- Interact with a user-friendly web interface

The application follows a modern architecture with a React frontend communicating with a Spring Boot REST API backend, all connected to a MongoDB database.

## 🛠️ Tech Stack

### Backend
- **Java 24** - Programming Language
- **Spring Boot 3.4.12** - Web Framework
- **Spring Data MongoDB** - Database ORM
- **Lombok** - Boilerplate Reduction
- **Maven** - Build Tool

### Frontend
- **React 18.3.1** - UI Library
- **React Router DOM 7.10.1** - Client-side Routing
- **Material-UI (MUI) 7.3.6** - UI Components
- **Axios 1.13.2** - HTTP Client
- **React Bootstrap 2.10.10** - Bootstrap Components
- **React Player 2.11.0** - Video Player
- **Font Awesome** - Icons

### Database
- **MongoDB** - NoSQL Database

## ✨ Features

- 🎬 **Movie Browsing** - Browse a comprehensive list of movies
- 🎞️ **Trailer Viewing** - Watch movie trailers directly in the app
- ⭐ **Reviews** - Read reviews from other users
- ✍️ **Review Submission** - Submit your own reviews and ratings
- 📱 **Responsive Design** - Works seamlessly on desktop and mobile devices
- 🎨 **Modern UI** - Clean and intuitive user interface with Material-UI
- 🔄 **Real-time Updates** - Instant updates when reviews are added

## 📁 Project Structure

```
MovieAPI/
├── movies/                          # Backend (Spring Boot)
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   └── dev/jon/movies/
│   │   │   │       ├── Movie.java
│   │   │   │       ├── MovieController.java
│   │   │   │       ├── MovieRepository.java
│   │   │   │       ├── MovieService.java
│   │   │   │       ├── Review.java
│   │   │   │       ├── ReviewController.java
│   │   │   │       ├── ReviewRepository.java
│   │   │   │       ├── ReviewService.java
│   │   │   │       └── MoviesApplication.java
│   │   │   └── resources/
│   │   │       └── application.properties
│   │   └── test/
│   ├── pom.xml
│   └── mvnw
│
└── movieClient/                     # Frontend (React)
    ├── src/
    │   ├── components/
    │   │   ├── Layout.js
    │   │   ├── header/
    │   │   │   └── Header.js
    │   │   ├── hero/
    │   │   │   ├── Hero.js
    │   │   │   └── Hero.css
    │   │   ├── home/
    │   │   │   └── Home.js
    │   │   ├── reviews/
    │   │   │   └── Reviews.js
    │   │   ├── reviewForm/
    │   │   │   └── ReviewForm.js
    │   │   └── trailer/
    │   │       ├── Trailer.js
    │   │       └── Trailer.css
    │   ├── api/
    │   │   └── axiosConfig.js
    │   ├── App.js
    │   ├── App.css
    │   ├── index.js
    │   └── index.css
    ├── public/
    ├── package.json
    └── README.md
```

## 🚀 Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:

- **Java 24** or later
- **Node.js 16+** and npm
- **Maven 3.6+**
- **MongoDB** (Local or MongoDB Atlas account)

### Backend Setup

1. **Navigate to the backend directory:**
   ```bash
   cd movies
   ```

2. **Install dependencies (Maven handles this automatically):**
   ```bash
   mvn clean install
   ```

3. **Configure MongoDB connection:**
   
   Update `src/main/resources/application.properties` with your MongoDB credentials:
   ```properties
   spring.application.name=movies
   spring.data.mongodb.database=YOUR_DATABASE_NAME
   spring.data.mongodb.uri=mongodb+srv://YOUR_USER:YOUR_PASSWORD@YOUR_CLUSTER
   ```

   Or set environment variables:
   ```bash
   MONGO_DATABASE=your_database_name
   MONGO_USER=your_username
   MONGO_PASSWORD=your_password
   MONGO_CLUSTER=your_cluster_url
   ```

### Frontend Setup

1. **Navigate to the frontend directory:**
   ```bash
   cd movieClient
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure API endpoint:**
   
   Update `src/api/axiosConfig.js` to point to your backend:
   ```javascript
   // Default is usually http://localhost:8080
   // Adjust as needed for your environment
   ```

## 🔧 Environment Variables

### Backend (MongoDB)

Create environment variables or update `application.properties`:

```properties
MONGO_DATABASE=movies_db
MONGO_USER=your_mongodb_username
MONGO_PASSWORD=your_mongodb_password
MONGO_CLUSTER=your_cluster.mongodb.net
```

### Frontend

The frontend communicates with the backend API. Ensure the backend is running at the configured endpoint (typically `http://localhost:8080`).

## ▶️ Running the Application

### Start the Backend

```bash
cd movies
mvn spring-boot:run
```

The backend will start on `http://localhost:8080`

### Start the Frontend

In a new terminal:

```bash
cd movieClient
npm start
```

The frontend will open at `http://localhost:3000`

## 📡 API Endpoints

### Movies

- `GET /api/v1/movies` - Get all movies
- `GET /api/v1/movies/{id}` - Get a specific movie
- `POST /api/v1/movies` - Create a new movie
- `PUT /api/v1/movies/{id}` - Update a movie
- `DELETE /api/v1/movies/{id}` - Delete a movie

### Reviews

- `GET /api/v1/reviews` - Get all reviews
- `GET /api/v1/reviews/{movieId}` - Get reviews for a specific movie
- `POST /api/v1/reviews` - Create a new review
- `PUT /api/v1/reviews/{id}` - Update a review
- `DELETE /api/v1/reviews/{id}` - Delete a review
