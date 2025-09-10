#  Chattingo - Mini Hackathon Challenge

A full-stack real-time chat application built with React, Spring Boot, and WebSocket technology. **Your mission**: Containerize this application using Docker and deploy it to Hostinger VPS using Jenkins CI/CD pipeline.


##  Project Goal

Transform the base Chattingo app into a **production-ready deployment pipeline**:

-  Dockerized frontend (React) and backend (Spring Boot)
-  Multi-container orchestration via Docker Compose
-  Secure CI/CD pipeline using Jenkins
-  Live deployment on VPS with HTTPS support



##  Architecture Overview

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Frontend      │    │   Backend       │    │   Database      │
│   (React)       │◄──►│   (Spring Boot) │◄──►│   (MySQL)       │
│   Port: 80      │    │   Port: 8080    │    │   Port: 3306    │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │
         └────── WebSocket ──────┘
```

##  Technology Stack

### Frontend
- **React 18** - Modern UI framework
- **Redux Toolkit** - State management
- **Material-UI** - Component library
- **Tailwind CSS** - Utility-first CSS
- **WebSocket (SockJS + STOMP)** - Real-time messaging
- **React Router** - Client-side routing

### Backend
- **Spring Boot 3.3.1** - Java framework
- **Spring Security** - Authentication & authorization
- **Spring Data JPA** - Database operations
- **Spring WebSocket** - Real-time communication
- **JWT** - Token-based authentication
- **MySQL** - Database

### DevOps 
- **Docker** - Containerization (YOU BUILD)
- **Docker Compose** - Multi-container orchestration (YOU BUILD)
- **Jenkins** - CI/CD pipeline (YOU BUILD)
- **Nginx** - Web server & reverse proxy (YOU BUILD)

###  Prerequisites

- Docker + Docker Compose
- Java 17
- Node.js 18+
- Maven

### ▶Run Locally

```bash
git clone https://github.com/YOUR_USERNAME/chattingo.git
cd chattingo

# Build and run all services
docker-compose up --build



## 📱 Application Features

### Core Functionality
- ✅ User authentication (JWT)
- ✅ Real-time messaging (WebSocket)
- ✅ Group chat creation
- ✅ User profile management
- ✅ Message timestamps
- ✅ Responsive design

### API Endpoints
```
POST   /api/auth/register    - User registration
POST   /api/auth/login       - User login
GET    /api/users            - Get users
POST   /api/chats/create     - Create chat
GET    /api/chats            - Get user chats
POST   /api/messages/create  - Send message
GET    /api/messages/{chatId} - Get chat messages
WS     /ws                   - WebSocket endpoint
```

## 📊 Project Structure

```
chattingo/
├── backend/                       # Spring Boot application
│   ├── src/main/java/
│   │   └── com/chattingo/
│   │       ├── Controller/        # REST APIs
│   │       ├── Service/           # Business logic
│   │       ├── Model/             # JPA entities
│   │       └── config/            # Configuration
│   ├── src/main/resources/
│   │   └── application.properties
│   ├── .env                       # Environment variables
│   ├── pom.xml
│   └── Dockerfile                 # ✅ Backend Dockerfile (3-stage)
├── frontend/                      # React application
│   ├── src/
│   │   ├── Components/            # React components
│   │   ├── Redux/                 # State management
│   │   └── config/                # API configuration
│   ├── .env                       # Environment variables
│   ├── package.json
│   ├── Dockerfile                 # ✅ Frontend Dockerfile (3-stage)
│   └── nginx.conf                 # ✅ Nginx config for serving React
├── docker-compose.yml             # ✅ Root-level orchestration file
├── Jenkinsfile                    # ✅ Jenkins CI/CD pipeline file
├── CONTRIBUTING.md                # Setup & deployment instructions
└── README.md                      # Project overview, links, guides

```











