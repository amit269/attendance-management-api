# 🏢 Attendance Management API

A secure, production-ready REST API for employee attendance 
management built with Java Spring Boot and MySQL.

## 🛠 Tech Stack

- **Java** + **Spring Boot**
- **MySQL** — relational database
- **Spring Security** + **JWT** — dual filter authentication
- **Spring Data JPA** + **Hibernate** — ORM & query optimization
- **Maven** — build tool

## ✨ Features

- ✅ Employee registration & secure login with JWT
- ✅ Role-based access control (EMPLOYEE / ADMIN)
- ✅ Mark-In / Mark-Out attendance tracking with timestamps
- ✅ Automatic total working hours calculation per day
- ✅ Duplicate mark-in prevention (one record per employee per day)
- ✅ Employee profile management with profile picture upload
- ✅ Dashboard with attendance summary
- ✅ Secure logout functionality
- ✅ BCrypt password encryption

## 📁 Project Structure
```
src/
├── Controller/      # REST API endpoints
│   ├── AttendanceController
│   ├── EmployeeRegisterController
│   ├── DashboardController
│   ├── ProfileController
│   └── LogoutController
├── Service/         # Business logic layer
├── Repository/      # Database layer (JPA)
├── Entity/          # JPA entities (Employee, Attendance)
├── Config/          # Spring Security configuration
├── Filter/          # JWT authentication filters
└── Utils/           # JWT utility classes
```

## 🔗 API Endpoints

| Method | Endpoint | Access | Description |
|--------|----------|--------|-------------|
| POST | `/public/register` | Public | Register new employee |
| POST | `/public/login` | Public | Login & get JWT token |
| POST | `/Attendance/markIn` | Employee | Record mark-in time |
| POST | `/Attendance/markOut` | Employee | Record mark-out time |
| GET | `/Dashboard` | Employee | View attendance summary |
| GET | `/Profile` | Employee | View employee profile |
| PUT | `/Profile/update` | Employee | Update profile details |

## 🗄️ Database Schema
```
Employee Table
├── employee_id (PK)
├── name
├── email
├── password (BCrypt encrypted)
├── address
├── position
├── profile_picture
└── roles

Attendance Table
├── id (PK)
├── employee_id (FK → Employee)
├── mark_in_time
├── mark_out_time
├── record_date
└── total_working_hours
```

## ⚙️ How to Run Locally

**1. Clone the repo**
```bash
git clone https://github.com/amit269/attendance-management-api.git
cd attendance-management-api
```

**2. Create MySQL database**
```sql
CREATE DATABASE attendance_management;
```

**3. Update `application.properties`**
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/attendance_management
spring.datasource.username=YOUR_DB_USERNAME
spring.datasource.password=YOUR_DB_PASSWORD
upload.directory=YOUR_LOCAL_UPLOAD_PATH
```

**4. Run the app**
```bash
mvn spring-boot:run
```

**5. Test APIs using Postman at:**
```
http://localhost:8080
```

## 🔐 Security
- Passwords encrypted with BCrypt
- Dual JWT filter implementation for enhanced security
- Role-based endpoint protection via Spring Security

## 👨‍💻 Author
**Amit Chouhan**  
[LinkedIn](https://www.linkedin.com/in/amit-chouhan-b81529172/) | 
[GitHub](https://github.com/amit269)# attendance-application
