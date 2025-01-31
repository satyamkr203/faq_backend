# FAQ Management System

Node.js/Express-based FAQ management system with multilingual support, rich text editing, and a REST API. The system provides automatic translation into Hindi and Bengali and features a modern admin interface for content management.

### **Features**
- ✅ **FAQ Creation & Management** with rich text editing.
- ✅ **Automatic Translation** to Hindi and Bengali using Google Translate.
- ✅ **REST API** for programmatic access to FAQ data.
- ✅ **Admin Interface** with translation preview and content management.
- ✅ **Real-Time Translation Status Indicators**.
- ✅ **Caching** with Redis for improved performance.
- ✅ **Comprehensive Test Coverage** to ensure reliability.
- ✅ **Dockerized Deployment** for easy setup and portability.

### **Tech Stack**
- **Django**: Backend framework for building the API and handling requests.
- **MongoDB**: NoSQL database to store FAQ data.
- **Redis**: Caching system to store translated FAQ data for fast access.
- **Google Translate API**: For automatic multilingual translation of FAQ content.
- **Mocha/Chai**: Testing framework for unit and integration testing.
- **Docker**: Containerization for easy deployment and setup.

---

## 📂 Project Structure
```plaintext
faq-backend/
├── config/
│   ├── db.js               # Database connection
│   ├── redis.js            # Redis configuration
├── controllers/
│   ├── faqController.js    # FAQ logic
├── models/
│   ├── faq.js              # FAQ schema
├── routes/
│   ├── faqRoutes.js        # API routes for FAQ
├── services/
│   ├── translationService.js # Google Translate integration
├── utils/
│   ├── cache.js            # Cache logic (Redis)
│   ├── errorHandler.js     # Error handling middleware
├── middlewares/
│   ├── authMiddleware.js   # Auth middleware (if applicable)
├── app.js                  # Express app configuration
├── tests/
│   ├── faq.test.js         # Unit tests for the FAQ API
├── .env                    # Environment variables
├── .gitignore              # Git ignore file
├── Dockerfile              # Dockerfile for containerization
├── docker-compose.yml      # Docker Compose config
├── package.json            # Dependencies and scripts
└── README.md               # Documentation
```

---

## 🛠️ Installation & Setup

Follow these steps to set up the project on your local machine.

### **Prerequisites**
Ensure you have the following installed:
- **Node.js & npm**: Download and install from [here](https://nodejs.org/)
- **Redis** (for caching): Install Redis from [here](https://redis.io/download)
- **Docker** (Optional for containerization): Install Docker from [here](https://www.docker.com/get-started)

### **Steps to Run Locally**

1. **Clone the repository**  
   First, clone the repository to your local machine:
   ```sh
   git clone https://github.com/your-repo/faq-backend.git
   cd faq-backend
   ```

2. **Install dependencies**  
   Install the required dependencies:
   ```sh
   npm install
   ```

3. **Set up environment variables**  
   Create a `.env` file in the root directory of the project.  
   Add necessary configurations such as database connection, Redis URL, and API keys. Example:
   ```env
   DB_URI=mongodb://localhost:27017/faqdb
   REDIS_URL=redis://localhost:6379
   ```

4. **Set up Redis**  
   Make sure Redis is installed and running. The app will connect to Redis for caching.  
   You can start Redis by running:
   ```sh
   redis-server
   ```

5. **Start the application**  
   After setting up the environment, you can start the application:
   ```sh
   npm start
   ```
   The app should now be running locally on `http://localhost:8000`.

6. **Run tests**  
   If you want to run the tests to ensure everything is working correctly, use:
   ```sh
   npm test
   ```

---

## 📡 API Endpoints
### **Base URL**
```
http://localhost:8000/api/faqs/
```

### **Endpoints**

#### **Fetch FAQs**
```sh
GET /api/faqs/           # Fetch FAQs in English (default)
GET /api/faqs/?lang=hi   # Fetch FAQs in Hindi
GET /api/faqs/?lang=bn   # Fetch FAQs in Bengali
```

#### **Create a FAQ**
```sh
POST /api/faqs/
Content-Type: application/json
{
    "question": "What is Node.js?",
    "answer": "Node.js is a JavaScript runtime.",
    "language": "en"
}
```

#### **Update a FAQ**
```sh
PUT /api/faqs/:id
Content-Type: application/json
{
    "answer": "Updated answer for Node.js."
}
```

#### **Delete a FAQ**
```sh
DELETE /api/faqs/:id
```

---

![Project Structure](assets/faq-dashboard.png)  <!-- Adding image -->

## 🧪 Docker Setup (Optional)

If you'd like to run the application using Docker, follow these steps:

1. **Build Docker image**  
   Build the Docker image using the `Dockerfile`:
   ```sh
   docker build -t faq-backend .
   ```

2. **Run the application with Docker**  
   Run the application with Docker Compose (this will also set up Redis for caching):
   ```sh
   docker-compose up
   ```

---
```

This `README.md` guides the user through setting up the project locally, including installation, environment configuration, and running the application. Let me know if you'd like to make any changes!
