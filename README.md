# STI Backend

**Modular backend API for an Intelligent Tutoring System (STI).**

STI Backend powers an academic platform designed to modernize educational management through personalized learning paths, academic resource management, intelligent tutoring workflows, and contextual AI-assisted academic support.

It provides the core business logic, authentication system, role-based access control, academic entities management, and communication with an external AI service.

## 📌 Description

This project serves as the backend infrastructure of the STI educational ecosystem.

It provides:

✔ Authentication and authorization management

✔ User lifecycle management

✔ Academic subjects administration

✔ Group management

✔ Academic sessions management

✔ Educational resources uploads

✔ Learning paths generation

✔ Learning style analysis

✔ AI-powered academic chatbot integration

✔ Initial system seeding

✔ Automatic administrator creation

The project follows a modular architecture based on domain separation and scalable service organization.

## 📚 Project Background

STI Backend is part of the evolution of a previously established academic tutoring system, redesigned and extended to support modern educational workflows, modular scalability, and AI-assisted academic interaction.

This implementation builds upon an earlier conceptual and technical foundation, adapting and expanding its architecture to support new academic requirements and intelligent tutoring strategies.

Original academic foundation and early system reference by:

**Isaías Elieser Osoria Tabares**

GitHub reference:

https://github.com/isaias-dev-7/

## ✨ Main Features

* 🔐 JWT authentication system

* 👥 Role-based access control (Admin, Professor, Student)

* 🌱 Automatic seed generation on first startup

* 👨‍💼 Automatic admin account generation

* 📚 Subject management

* 👥 Academic group management

* 🧩 Session management

* 📂 Educational resource upload system

* 🧠 Personalized learning path generation

* 📊 Learning style analytics

* 🤖 AI chatbot integration

* 🔒 Password encryption with bcrypt

* ⚡ Modular scalable architecture

* 🐳 Dockerized database environment

---

## 🚀 Installation & Usage

### 1. Clone the repository

```bash
git clone https://github.com/emanuelarevalomartinez/STI-My_Backend.git
```

Enter the project directory:

```bash
cd STI-My_Backend
```

---

### 2. Install dependencies

```bash
npm install
```

---

## ⚙️ Environment Configuration

Before running the project, create your `.env` file based on the template:

```bash
cp .env.template .env
```

Configure:

```env
PORT=3000

DB_HOST=localhost
DB_PORT=3306
DB_USER=sti_user
DB_PASS=sti_password
DB_NAME=sti_db

JWT_SECRET=your_super_secret_jwt_key_here

EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_email_app_password

EMAIL_ADMIN=admin@gmail.com
NAME_ADMIN=admin all system
PASS_ADMIN=admin123A+

MODE=dev
HOST_LOCAL=localhost
HOST_SERVER=
HOST_SERVER_DEV=

CHATBOT_URL=http://localhost:8000
```

### Important notes:

The admin account is automatically created during the first backend startup.

The `NAME_ADMIN` value **must contain exactly three words separated by spaces**.

Example:

```env
NAME_ADMIN=admin all system
```

Why?

The system generates the admin username automatically from the fullname structure.

Example generated username:

```bash
adminas
```

If the fullname has fewer than three words, startup will fail.

---

## 🐳 Docker Database Setup

The `docker-compose.yml` file is located inside the `docker/` directory.

Navigate first:

```bash
cd docker
```

Run Docker services:

```bash
docker compose up -d
```

Services:

| Service | Port | Purpose |
|---|---:|---|
| MySQL | 3306 | Main database |
| phpMyAdmin | 8080 | Database administration |

Access phpMyAdmin:

```bash
http://localhost:8080
```

Credentials:

```bash
User: root
Password: rootpassword
```

Return to project root:

```bash
cd ..
```

---

## 📂 Uploads Directory Setup

Before starting the backend, you must manually create the uploads structure in the root project directory.

Required structure:

```bash
uploads/
├── subjectImages/
└── resources/
    ├── aud/
    ├── documents/
    ├── images/
    └── video/
```

Create it with:

```bash
mkdir -p uploads/subjectImages
mkdir -p uploads/resources/aud
mkdir -p uploads/resources/documents
mkdir -p uploads/resources/images
mkdir -p uploads/resources/video
```

These directories are required for:

✔ Subject images

✔ Documents

✔ Audio resources

✔ Images

✔ Videos

Without these folders, file upload operations will fail.

---

## ▶ Running the project

Development mode:

```bash
npm run start:dev
```

Production mode:

```bash
npm run start:prod
```

Build:

```bash
npm run build
```

---

## 🌐 API Access

Once running:

API Base URL:

```bash
http://localhost:3000/api
```

Swagger Documentation:

```bash
http://localhost:3000/docs
```

---

## 🧩 Project Architecture

Project root structure:

| Directory | Purpose |
|---|---|
| src | Main source code |
| docker | Docker configuration |
| uploads | Uploaded files storage |
| db | MySQL persistent volume |
| dist | Production build output |
| dev | Development helpers |

---

## 🧠 Backend Modules

The backend is divided into modular domains:

| Module | Responsibility |
|---|---|
| auth | Authentication and authorization |
| chatbot | AI chatbot communication |
| common | Shared utilities and responses |
| group | Group management |
| http-service | External HTTP integrations |
| learning-path | Personalized routes |
| professor | Professor domain logic |
| resource | Educational resources |
| seed | Initial database data |
| session | Academic sessions |
| student | Student domain logic |
| subject | Subject management |
| user | User lifecycle |
| utils | Shared utilities |

---

## 🛠 Tech Stack

| Technology | Usage |
|---|---|
| NestJS | Backend framework |
| TypeScript | Main language |
| TypeORM | ORM |
| MySQL | Database |
| JWT | Authentication |
| bcryptjs | Password hashing |
| Multer | File uploads |
| Docker | Containers |
| Docker Compose | Service orchestration |
| Swagger | API docs |
| phpMyAdmin | Database management |
| Django | External AI service |

---

## 🤖 AI Integration

STI integrates with an external AI service for academic assistance.

Configuration:

```env
CHATBOT_URL=http://localhost:8000
```

NestJS acts as an intermediary between frontend and AI service.

This allows contextual academic conversations inside subjects and sessions.

---

## 🌱 Initial Startup Behavior

On first startup:

✔ Initial seed data is inserted

✔ Academic subjects are created

✔ Default administrator is generated

This ensures the platform is ready to use immediately.

---

## 🔒 Authentication Flow

STI uses JWT authentication.

Flow:

1. Login  
2. Token generation  
3. Protected routes validation  
4. Role verification  
5. Resource authorization  

Supported roles:

✔ Admin

✔ Professor

✔ Student

---

## 📝 License

UNLICENSED

---

## 🔗 Repository

Backend Repository:

[GitHub - STI Backend](https://github.com/emanuelarevalomartinez/STI-My_Backend)

Frontend Repository:

[GitHub - STI Frontend](https://github.com/emanuelarevalomartinez/STI-My_Frontend)