# KickOff - Turf Booking Application

<div align="center">

### 🔗 Quick Access to Repositories

[![Frontend](https://img.shields.io/badge/Frontend-React_+_Vite-61DAFB?style=for-the-badge&logo=react&logoColor=white)](https://github.com/johnjoshua21/Kickoff-Frontend.git)
[![Backend](https://img.shields.io/badge/Backend-Spring_Boot-6DB33F?style=for-the-badge&logo=spring&logoColor=white)](https://github.com/johnjoshua21/KickOff-Backend.git)

**[📱 Frontend Repository](https://github.com/johnjoshua21/Kickoff-Frontend.git)** | **[⚙️ Backend Repository](https://github.com/johnjoshua21/KickOff-Backend.git)**

---

</div>

A comprehensive full-stack web application for booking sports turfs and managing turf facilities. Built with React (Frontend) and Spring Boot (Backend), KickOff provides a seamless experience for users to browse and book turfs, owners to manage their facilities, and admins to oversee the entire platform.

> **📚 Educational Project:** This project is developed for learning full-stack development concepts and best practices.

![KickOff Banner](https://github.com/user-attachments/assets/5578c1b8-ac14-410d-9b71-aec46c855f53)

## 🎯 Overview

KickOff is a modern turf booking platform that connects sports enthusiasts with turf facilities. The application streamlines the booking process, reduces scheduling conflicts, and provides powerful management tools for turf owners.

### Key Highlights

- **Real-time Availability**: Check turf availability instantly
- **Multi-sport Support**: Football, Cricket, Badminton, Tennis, Basketball, Volleyball, Hockey, and Futsal
- **Role-based Access Control**: Separate dashboards for Users, Turf Owners, and Admins
- **Slot Management**: Block unavailable slots and prevent double bookings
- **Image Gallery**: Upload and display multiple turf images
- **Responsive Design**: Works seamlessly on desktop and mobile devices

## ✨ Features

### For Users
- 🔍 **Browse Turfs**: Search and filter turfs by location, sport type, and price
- 📅 **Easy Booking**: Book time slots with real-time availability checking
- 💳 **Price Calculator**: Automatic price calculation based on duration
- 📱 **Booking Management**: View, track, and cancel bookings
- 👤 **Profile Management**: Update personal information and password

### For Turf Owners
- 🏟️ **Turf Management**: Add, edit, and delete turf listings with image galleries
- 📊 **Dashboard Analytics**: View booking statistics and revenue
- 🚫 **Slot Blocking**: Block time slots for maintenance or events
- 📋 **Booking Overview**: Track all bookings across all turfs
- 💰 **Revenue Tracking**: Monitor earnings and booking trends

### For Admins
- 👥 **User Management**: View and manage all users
- 🏢 **Platform Overview**: Complete system statistics
- 📈 **Analytics Dashboard**: Track bookings, revenue, and user activity
- 🗑️ **Content Moderation**: Delete users, turfs, or bookings if needed

## 🛠️ Tech Stack

### Frontend
- **Framework**: React 18 with Vite
- **Routing**: React Router v6
- **Styling**: Tailwind CSS
- **Icons**: Lucide React
- **HTTP Client**: Axios
- **Authentication**: JWT with Context API

### Backend
- **Framework**: Spring Boot 3.x
- **Language**: Java 17
- **Database**: MySQL 8
- **Security**: Spring Security with JWT
- **ORM**: Hibernate (JPA)
- **Build Tool**: Maven

### DevOps & Tools
- **Version Control**: Git & GitHub
- **API Testing**: Postman
- **File Storage**: Local file system
- **CORS**: Configured for cross-origin requests

## 🚀 Getting Started

### Prerequisites

- **Node.js** (v16 or higher)
- **Java** (JDK 17 or higher)
- **MySQL** (v8 or higher)
- **Maven** (v3.6 or higher)
- **Git**

### Quick Start

#### 1. Clone the Repositories
```bash
# Clone frontend
git clone https://github.com/johnjoshua21/Kickoff-Frontend.git

# Clone backend
git clone https://github.com/johnjoshua21/KickOff-Backend.git
```

#### 2. Setup Backend
```bash
cd KickOff-Backend

# Create MySQL database
mysql -u root -p
CREATE DATABASE turfBooking;
exit;

# Update application.properties with your MySQL credentials
# Edit src/main/resources/application.properties

# Build and run
mvn clean install
mvn spring-boot:run
```

Backend will run on `http://localhost:8080`

#### 3. Setup Frontend
```bash
cd Kickoff-Frontend

# Install dependencies
npm install

# Start development server
npm run dev
```

Frontend will run on `http://localhost:5173`

### Database Configuration

Update `application.properties` in the backend:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/turfBooking
spring.datasource.username=YOUR_USERNAME
spring.datasource.password=YOUR_PASSWORD
spring.jpa.hibernate.ddl-auto=update
```

### Environment Variables

Create `.env` file in frontend root (optional):
```env
VITE_API_URL=http://localhost:8080/api
```

## 📁 Project Structure

### Frontend Repository
**[Kickoff-Frontend](https://github.com/johnjoshua21/Kickoff-Frontend.git)**
```
kickoff-frontend/
├── src/
│   ├── assets/          # Images and static files
│   ├── components/      # Reusable React components
│   │   ├── BookingModal.jsx
│   │   ├── TurfCard.jsx
│   │   ├── TurfFormModal.jsx
│   │   ├── UserLayout.jsx
│   │   └── OwnerLayout.jsx
│   ├── context/         # React Context API
│   │   └── AuthContext.jsx
│   ├── pages/           # Page components
│   │   ├── admin/       # Admin pages
│   │   ├── owner/       # Owner pages
│   │   └── user/        # User pages
│   ├── services/        # API service layers
│   │   ├── authService.js
│   │   ├── bookingService.js
│   │   └── turfService.js
│   ├── App.jsx          # Main app component
│   └── main.jsx         # Entry point
├── public/              # Public assets
└── package.json         # Dependencies
```

### Backend Repository
**[KickOff-Backend](https://github.com/johnjoshua21/KickOff-Backend.git)**
```
kickoff-backend/
├── src/main/java/com/turfBooking/
│   ├── config/          # Spring configurations
│   │   ├── CorsConfig.java
│   │   └── WebSecurityConfig.java
│   ├── controller/      # REST controllers
│   │   ├── AuthController.java
│   │   ├── BookingController.java
│   │   ├── TurfController.java
│   │   ├── UserController.java
│   │   └── AdminController.java
│   ├── dto/             # Data Transfer Objects
│   ├── entity/          # JPA entities
│   │   ├── User.java
│   │   ├── Turf.java
│   │   ├── Booking.java
│   │   ├── BlockedSlot.java
│   │   └── TurfImage.java
│   ├── enums/           # Enumerations
│   ├── repository/      # JPA repositories
│   ├── security/        # Security & JWT
│   ├── service/         # Business logic
│   │   ├── implementation/
│   │   └── interfaces/
│   └── util/            # Utility classes
├── src/main/resources/
│   └── application.properties
└── pom.xml              # Maven dependencies
```

## 👥 User Roles

### 1. Regular User (USER)
- Browse and search available turfs
- Book time slots
- View and manage bookings
- Update profile

**Registration**: Select "Book Sports" during signup

### 2. Turf Owner (TURF_OWNER)
- Create and manage turf listings
- Upload turf images (multiple per turf)
- Block time slots for maintenance
- View booking analytics
- Track revenue

**Registration**: Select "Own a Turf" during signup

### 3. Administrator (ADMIN)
- Full platform oversight
- User management
- System-wide analytics
- Content moderation
- Delete any entity

**Registration**: Use `/api/auth/register-admin` endpoint (restricted)

## 📚 API Documentation

### Authentication Endpoints

#### Register User
```http
POST /api/auth/register
Content-Type: application/json

{
  "name": "John Doe",
  "phone": "1234567890",
  "password": "password123",
  "registrationType": "BOOK_SPORTS" // or "OWN_TURF"
}
```

#### Login
```http
POST /api/auth/login
Content-Type: application/json

{
  "phone": "1234567890",
  "password": "password123"
}
```

**Response:**
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "role": "USER",
  "userId": 1
}
```

### Turf Endpoints

#### Get All Turfs
```http
GET /api/turfs
```

#### Create Turf (Owner/Admin only)
```http
POST /api/turfs
Authorization: Bearer <token>
Content-Type: application/json

{
  "name": "Champions Arena",
  "phone": "9876543210",
  "location": "Coimbatore, Tamil Nadu",
  "type": "FOOTBALL",
  "pricePerSlot": 500,
  "description": "Premium football turf",
  "operatingStartTime": "06:00",
  "operatingEndTime": "22:00",
  "ownerId": 2,
  "imageUrls": ["/api/files/image1.jpg", "/api/files/image2.jpg"]
}
```

#### Search Turfs
```http
POST /api/turfs/search
Content-Type: application/json

{
  "location": "Coimbatore",
  "type": "FOOTBALL",
  "minPrice": 300,
  "maxPrice": 700
}
```

### Booking Endpoints

#### Create Booking
```http
POST /api/bookings
Authorization: Bearer <token>
Content-Type: application/json

{
  "userId": 1,
  "turfId": 3,
  "bookingDate": "2024-12-25",
  "slotStartTime": "18:00",
  "slotEndTime": "20:00",
  "status": "CONFIRMED"
}
```

#### Get My Bookings
```http
GET /api/bookings/user/{userId}
Authorization: Bearer <token>
```

#### Cancel Booking
```http
PUT /api/bookings/{bookingId}/cancel
Authorization: Bearer <token>
```

### Block Slot Endpoints (Owner/Admin)

#### Create Blocked Slot
```http
POST /api/blocked-slots
Authorization: Bearer <token>
Content-Type: application/json

{
  "turfId": 3,
  "blockedDate": "2024-12-24",
  "startTime": "10:00",
  "endTime": "14:00"
}
```

#### Get Blocked Slots by Owner
```http
GET /api/blocked-slots/owner/{ownerId}
Authorization: Bearer <token>
```

### File Upload Endpoints

#### Upload Single Image
```http
POST /api/files/upload
Authorization: Bearer <token>
Content-Type: multipart/form-data

file: <image-file>
```

#### Upload Multiple Images
```http
POST /api/files/upload-multiple
Authorization: Bearer <token>
Content-Type: multipart/form-data

files: <image-files>
```

#### Get Image
```http
GET /api/files/{filename}
```

### Admin Endpoints

#### Get All Users
```http
GET /api/admin/users
Authorization: Bearer <token>
```

#### Get All Bookings
```http
GET /api/admin/bookings
Authorization: Bearer <token>
```

#### Delete User
```http
DELETE /api/admin/users/{userId}
Authorization: Bearer <token>
```

## 🔐 Security Features

- **JWT Authentication**: Secure token-based authentication
- **Password Encryption**: BCrypt hashing for all passwords
- **Role-based Access Control**: Granular permissions for different user types
- **CORS Configuration**: Properly configured cross-origin requests
- **Input Validation**: Server-side validation for all inputs
- **SQL Injection Prevention**: Parameterized queries with JPA

---

## 👨‍💻 Author

**John Joshua**
- GitHub: [@johnjoshua21](https://github.com/johnjoshua21)
- Student Project - Learning Full Stack Development



---

## 🔗 Repository Links

<div align="center">

| Repository | Description | Link |
|------------|-------------|------|
| 🎨 **Frontend** | React + Vite + Tailwind CSS | [View Repository](https://github.com/johnjoshua21/Kickoff-Frontend.git) |
| ⚙️ **Backend** | Spring Boot + MySQL + JWT | [View Repository](https://github.com/johnjoshua21/KickOff-Backend.git) |
| 📦 **Parent** | Complete Project Overview | [View Repository](https://github.com/johnjoshua21/KickOff-TurfBookingApplication.git) |

</div>

---

<div align="center">

⭐ **Star this repository if you find it helpful for learning!**

**Disclaimer:** This project is created for educational purposes as part of learning full-stack development. It may not be production-ready and is intended for academic use only.

Made with ❤️ by a passionate student learning full-stack development

</div>
