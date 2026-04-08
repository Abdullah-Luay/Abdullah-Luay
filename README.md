# 🚀 Scalable Django Backend System

> Production-ready backend built with Django & DRF, designed for high-performance APIs, secure integrations, and scalable architecture.

---

## 📌 Overview

This project is a **real-world backend system** built using modern engineering practices.  
It focuses on **scalability, maintainability, and clean architecture**, making it suitable for enterprise-level applications.

The system includes:

- API-first design using Django REST Framework
- Service-to-service secure communication (HMAC)
- Background processing with Celery
- Modular and extensible architecture
- Real business workflows (delegation, payments, integrations)

---

## 🧠 Key Features

- 🔐 Authentication & Authorization (JWT + HMAC)
- ⚡ High-performance REST APIs
- 🔄 Asynchronous task processing (Celery + Redis)
- 📦 Modular Django apps architecture
- 📊 Admin dashboard for data management
- 🌍 Internationalization (i18n support)
- 📁 File upload & media handling
- 📡 External API integrations
- 🧾 Flexible Payment system (GenericForeignKey design)
- 📨 WhatsApp messaging integration

---

## 🏗️ Architecture

```
Client
   ↓
API Layer (DRF Views)
   ↓
Service Layer (Business Logic)
   ↓
Domain Models (Django ORM)
   ↓
Database
```

### Design Principles

- Clean separation of concerns
- Reusable service layer
- Config-driven behavior
- Idempotent operations
- Scalable async processing
- Secure-by-default architecture

---

## 🛠️ Tech Stack

- **Backend:** Python, Django, Django REST Framework  
- **Async:** Celery, Redis  
- **Authentication:** JWT (SimpleJWT), HMAC service auth  
- **API Docs:** drf-spectacular (Swagger / OpenAPI)  
- **Database:** PostgreSQL (prod), SQLite (dev)  
- **Deployment:** Docker, Docker Swarm  
- **Server:** ASGI (Daphne / Gunicorn)  
- **Messaging:** UltraMsg (WhatsApp API)

---

## 🔐 Security

- HMAC-based service authentication
- JWT-based user authentication
- Rate limiting for APIs
- Strong input validation via serializers
- Environment-based secret management
- Protection against common API vulnerabilities

---

## ⚙️ Installation

```bash
git clone https://github.com/your-username/scalable-django-backend.git
cd scalable-django-backend

python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate

pip install -r requirements.txt
```

---

## 🔧 Configuration

Create environment variables:

```env
SECRET_KEY=your_secret_key
DEBUG=True

DATABASE_URL=your_db_url
REDIS_URL=redis://localhost:6379

JWT_SECRET=your_jwt_secret

SERVICE_KEY_ID=your_service_key
SERVICE_KEY_SECRET=your_service_secret
```

---

## 🚀 Running the Project

```bash
python manage.py migrate
python manage.py runserver
```

### Run Celery Worker

```bash
celery -A config worker -l info
```

---

## 🧪 Testing

```bash
python manage.py test
```

Optional load testing:

- Locust
- k6

---

## 📡 API Documentation

Swagger UI:

```
/swagger/
```

OpenAPI Schema:

```
/schema/
```

---

## 🔄 Service-to-Service Authentication Example

### Signature Generation

```python
message = f"{method}:{path}:{timestamp}"
signature = HMAC_SHA256(secret, message)
```

### Headers

```
Authorization: Bearer {key_id}:{signature}
X-Timestamp: {timestamp}
```

---

## 📦 Project Structure

```
apps/
 ├── users/
 ├── services/
 ├── payments/
 ├── facilities/
 ├── web_data/

config/
 ├── settings/
 ├── urls.py
```

---

## 🧩 Use Cases

- ERP systems
- Government platforms
- Booking & delegation systems
- Payment processing systems
- Multi-service backend architecture

---

## 📈 Performance Considerations

- Optimized queries using `select_related` & `prefetch_related`
- Background jobs for heavy operations
- Pagination & filtering
- Indexed database fields
- Scalable architecture ready for caching

---

## 🤝 Contribution

Contributions are welcome.

1. Fork the repository
2. Create a feature branch
3. Submit a pull request

---

## 📄 License

MIT License

---

## 👨‍💻 Author

**Abdullah Al-Ubaidy**  
Backend Developer | Django | Scalable Systems  

---

## ⭐ Why This Project Matters

This project demonstrates:

- Real-world backend engineering experience
- Scalable system design
- Secure API architecture
- Production-ready implementation practices

---

## 🔥 Notes

This repository is part of my professional portfolio and reflects my approach to building scalable backend systems.
