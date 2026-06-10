# 🚀 FastShip Logistics API

FastShip is a high-performance logistics and shipment management API built with **FastAPI**, **PostgreSQL**, and **Redis**. Designed for modern e-commerce structures, it enables sellers to manage shipments, allows delivery partners to coordinate deliveries, tracks transit timelines, and sends automated email notifications on shipment updates.

[![Deploy to Render](https://render.com/images/deploy-to-render.button.svg)](https://render.com/deploy?repo=https://github.com/Akshayaraj-C/FastShip_API-)

---

## 🛠️ Tech Stack & Architecture

- **Backend Framework:** FastAPI (Asynchronous Python)
- **Database:** PostgreSQL (with SQLModel / SQLAlchemy Asyncio ORM)
- **Caching & Security Storage:** Redis (for session blacklisting and token invalidation)
- **Email Notifications:** FastAPI-Mail (SMTP notification system with HTML email templates)
- **Documentation:** Scalar API Reference Docs
- **Deployment:** Docker & Render Blueprint

---

## ✨ Key Features

1. **Dual Role Architecture:**
   - **Sellers:** Can register, create new shipments, track shipment status, and view delivery history.
   - **Delivery Partners:** Can register with specific serviceable ZIP codes, manage active shipments, and update shipment progress.

2. **Automated Notification Engine:**
   - Integrates background tasks with SMTP mail to automatically trigger responsive HTML emails to customers when a shipment status changes (e.g., *Placed, In Transit, Out for Delivery, Delivered, Cancelled*).

3. **Production Security:**
   - JWT-based authentication for both Sellers and Delivery Partners.
   - Token blacklisting stored in Redis on user logout for secure session invalidation.

4. **Dynamic Timelines:**
   - Fully trackable historical status events for each shipment.

---

## 🚀 One-Click Cloud Deployment

You can deploy this API along with its PostgreSQL database and Redis server to Render by clicking the button below:

[![Deploy to Render](https://render.com/images/deploy-to-render.button.svg)](https://render.com/deploy?repo=https://github.com/Akshayaraj-C/FastShip_API-)

---

## 💻 Local Development Setup

### Prerequisites
- Python 3.10+
- PostgreSQL
- Redis

### Installation Steps

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/Akshayaraj-C/FastShip_API-.git
   cd FastShip_API-
   ```

2. **Create and Activate Virtual Environment:**
   ```bash
   python -m venv .venv
   # On Windows:
   .venv\Scripts\activate
   # On macOS/Linux:
   source .venv/bin/activate
   ```

3. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure Environment Variables:**
   Create a `.env` file in the root directory and define the following variables:
   ```env
   # App Settings
   APP_NAME=FastShip
   APP_DOMAIN=localhost:8000

   # Database Settings
   POSTGRES_SERVER=localhost
   POSTGRES_PORT=5432
   POSTGRES_USER=your_postgres_user
   POSTGRES_PASSWORD=your_postgres_password
   POSTGRES_DB=fastship

   # Redis Settings
   REDIS_HOST=localhost
   REDIS_PORT=6379

   # Security Settings
   JWT_SECRET=your_super_secret_jwt_key
   JWT_ALGORITHM=HS256

   # Notification / SMTP Mail Settings (e.g. Mailtrap details)
   MAIL_USERNAME=your_smtp_username
   MAIL_PASSWORD=your_smtp_password
   MAIL_FROM=no-reply@fastship.com
   MAIL_PORT=2525
   MAIL_SERVER=sandbox.smtp.mailtrap.io
   ```

5. **Run the Application:**
   ```bash
   uvicorn main:app --reload
   ```

6. **Interactive Documentation:**
   Open [http://localhost:8000/scalar](http://localhost:8000/scalar) to test the endpoints interactively.
