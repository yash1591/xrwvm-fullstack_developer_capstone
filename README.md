🚗 Dealerships Website – Microservices Based Full Stack Application
📌 Project Overview

The Dealerships Website is a full-stack microservices-based web application built using Django, React, Node.js, MongoDB, Docker, and Kubernetes.

The system allows users to:

View car makes and models

View all dealerships

Filter dealerships by state

View dealer details

View reviews of a dealer

Add reviews with sentiment analysis

The project integrates multiple technologies including a Django backend, Node.js microservices, MongoDB database, IBM Cloud Code Engine, and containerized deployment using Docker and Kubernetes.

🏗 Solution Architecture
🔹 Components
1️⃣ Dealerships Website (Django + React)

Handles frontend rendering and templates

Provides proxy APIs

Manages user authentication

Stores car makes & models (SQLite)

2️⃣ Dealership & Reviews Service (Node.js + Express + MongoDB)

Manages dealer data

Manages review data

Runs inside Docker container

3️⃣ Sentiment Analyzer Service (IBM Cloud Code Engine)

Analyzes review text

Returns:

Positive

Negative

Neutral

🧰 Technology Stack
Layer	Technology
Frontend	React, Django Templates
Backend	Django
Microservice	Node.js, Express
Database (Cars)	SQLite
Database (Dealers/Reviews)	MongoDB
Containerization	Docker
Deployment	Kubernetes
Cloud Service	IBM Cloud Code Engine
CI/CD	GitHub Actions
🔌 Microservices & APIs
📍 Django Microservices
Endpoint	Description
/get_cars/	Get list of cars
/get_dealers/	Get all dealers
/get_dealers/:state	Get dealers by state
/dealer/:id	Get dealer by ID
/review/dealer/:id	Get reviews for dealer
/add_review/	Add new review
📍 Dealership & Reviews Service (Node.js)
Endpoint	Description
/fetchDealers	Fetch all dealers
/fetchDealer/:id	Fetch dealer by ID
/fetchReviews	Fetch all reviews
/fetchReview/dealer/:id	Fetch reviews by dealer ID
/insertReview	Insert a new review
📍 Sentiment Analyzer Service
Endpoint	Description
/analyze/:text	Returns sentiment of text
🔐 User Management

User authentication is implemented using Django’s built-in authentication system.

Features:

User Registration

Login

Logout

Authenticated users can add reviews

Anonymous users can only view dealers and reviews

🗂 Project Structure
dealerships-website/
│
├── django_app/
│   ├── models.py
│   ├── views.py
│   ├── proxy_services.py
│   └── templates/
│
├── react_frontend/
│
├── node_dealers_service/
│   ├── server.js
│   ├── routes/
│   └── Dockerfile
│
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
│
└── README.md
🚀 Setup Instructions
🔹 1. Fork & Clone Repository
git clone <your-forked-repo-url>
cd dealerships-website
🔹 2. Run Django Application
cd django_app
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver

Application runs at:

http://localhost:8000
🔹 3. Run Node.js Service
cd node_dealers_service
npm install
docker build -t dealers-service .
docker run -p 5000:5000 dealers-service
🔹 4. Configure MongoDB

Make sure MongoDB is running locally or via Docker:

docker run -d -p 27017:27017 mongo
🔹 5. Deploy to Kubernetes
kubectl apply -f k8s/
🔄 CI/CD Pipeline

CI/CD is configured using GitHub Actions.

Pipeline includes:

Code linting

Build validation

Docker image build

Kubernetes deployment

📄 Features Implemented

✅ Static pages for user stories
✅ Django authentication system
✅ React frontend
✅ MongoDB integration
✅ Dockerized Node.js microservice
✅ Sentiment analysis integration
✅ Proxy service in Django
✅ Dynamic Django templates
✅ Dealer listing page
✅ Dealer reviews page
✅ Add review page
✅ CI/CD pipeline
✅ Kubernetes deployment

📊 Database Design
SQLite (Django)

CarMake

CarModel

MongoDB

Dealers Collection

Reviews Collection

🌍 Deployment Flow

Node service containerized using Docker

Deployed on Kubernetes cluster

Sentiment analyzer deployed on IBM Code Engine

Django app communicates via proxy services

End user accesses via browser

🧠 Key Learning Outcomes

Microservices architecture

REST API integration

Proxy services

Full stack development

Docker & container orchestration

Kubernetes deployment

Cloud deployment

CI/CD pipelines

Authentication systems

Sentiment analysis integration

📌 Future Improvements

JWT-based authentication

Caching with Redis

Role-based access control

Advanced sentiment analytics

Production-grade monitoring

👨‍💻 Author

Yash Deshmukh
Computer Engineering Student
