# 🛒 TruSwap – Student Marketplace Platform

**First Place Winner – Truman State University ACM Codeathon 2025**

TruSwap is a full-stack marketplace platform designed specifically for university students to securely buy, sell, rent, and exchange items within their campus community. The platform provides authentication, listing management, group-based marketplaces, order tracking, and payment processing while maintaining a secure and scalable architecture.

## 🚀 Overview

College students frequently need a trusted platform to buy, sell, and rent textbooks, furniture, electronics, and other items without relying on public marketplaces.

TruSwap solves this problem by providing a university-focused marketplace with:

* Secure user authentication
* Campus-focused buying and selling
* Group-based marketplace communities
* Online payment processing
* Order tracking and purchase history
* Cloud-based deployment architecture

The platform was built using a modern full-stack architecture with a React frontend, Spring Boot backend, MongoDB database, Auth0 authentication, and PayPal integration.

---

# 🏗️ System Architecture

```text
React Frontend (Vite)
          │
          ▼
Spring Boot REST API
          │
          ▼
Service Layer
          │
          ▼
MongoDB Database
          │
 ┌────────┴────────┐
 ▼                 ▼
Auth0           PayPal
Authentication  Payments
```

### Frontend

Built using React and Vite with a component-based architecture.

Responsibilities:

* User interface
* Marketplace browsing
* Listing creation
* Group management
* Shopping workflows
* Authentication integration

### Backend

Built using Spring Boot and Java.

Responsibilities:

* Business logic
* API endpoints
* Authorization
* Payment workflows
* Database operations

### Database

MongoDB stores:

* Listings
* Users
* Orders
* Marketplace groups
* Transaction records

---

# ✨ Features

## Marketplace Listings

Students can:

* Create listings
* Buy items
* Sell items
* Rent items
* Browse listings by category
* View listing details

Each listing contains:

* Title
* Description
* Category
* Price
* Seller information
* Listing type (sell/rent)
* Images
* Posting date

---

## Secure Authentication

Authentication is handled through Auth0.

Features:

* User registration
* Login/logout
* JWT-based authentication
* Protected routes
* Secure API authorization

Protected actions include:

* Creating listings
* Viewing order history
* Managing personal listings
* Creating groups
* Processing payments

---

## Group-Based Marketplaces

One unique feature of TruSwap is support for marketplace groups.

Examples:

* Dorm communities
* Student organizations
* Academic departments
* Campus clubs

Users can:

* Create groups
* Join groups
* Browse group-specific listings
* Buy and sell within trusted communities

---

## Order Management

The platform tracks:

* Purchases
* Sales
* Transaction history
* Seller activity

Users can view:

* Purchased items
* Sold items
* Order status
* Transaction history

---

## PayPal Integration

Integrated PayPal checkout allows users to complete transactions securely.

Payment workflow:

```text
Buyer
   ↓
PayPal Checkout
   ↓
Payment Approval
   ↓
Backend Verification
   ↓
Order Creation
   ↓
Purchase Confirmation
```

---

# 🔄 Listing Creation Workflow

One of the core application workflows:

```text
User Creates Listing
        ↓
React Form Submission
        ↓
JWT Token Attached
        ↓
POST /api/createListing
        ↓
Spring Security Validates JWT
        ↓
ItemsController
        ↓
ItemService
        ↓
ItemRepository
        ↓
MongoDB
        ↓
Listing Saved
        ↓
Response Returned
        ↓
Marketplace Updated
```

Security is enforced by extracting the authenticated user ID from the JWT token rather than trusting client-provided user information.

---

# 🔐 Security Features

## Authentication & Authorization

Auth0 provides:

* JWT authentication
* Identity management
* Secure login flow
* Route protection

Backend authorization ensures only authenticated users can:

* Create listings
* Process purchases
* Manage groups
* View private user data

---

## API Security

Protected endpoints require:

```http
Authorization: Bearer <JWT_TOKEN>
```

Unauthorized requests are rejected before reaching business logic.

---

## Input Validation

The application validates:

* Listing data
* User input
* Payment requests
* Group creation requests

before persisting data to the database.

---

## CORS Protection

Spring Security is configured with controlled CORS policies allowing only approved frontend origins to access backend APIs.

---

# ☁️ Deployment Architecture

## Frontend

Platform: Vercel

Responsibilities:

* Static hosting
* Fast global delivery
* Frontend deployment pipeline

## Backend

Platform: Google Cloud Run

Responsibilities:

* Spring Boot API hosting
* Automatic scaling
* Containerized deployment

## Containerization

Docker is used to package backend services for consistent deployment across environments.

---

# 📊 Database Design

### Users

Stores:

* Auth0 user identifiers
* Profile information

### Listings

Stores:

* Product information
* Seller information
* Listing metadata

### Orders

Stores:

* Purchase records
* Buyer information
* Transaction history

### Groups

Stores:

* Marketplace communities
* Group membership information

---

# 💻 Tech Stack

## Frontend

* React
* Vite
* React Router
* Axios
* Tailwind CSS

## Backend

* Java 21
* Spring Boot
* Spring Security
* Spring Data MongoDB

## Authentication

* Auth0
* JWT Authentication

## Database

* MongoDB

## Payments

* PayPal REST API

## Cloud & DevOps

* Docker
* Google Cloud Run
* Vercel

---

# 🎯 Key Learning Outcomes

Through TruSwap, I gained experience with:

* Full-stack application development
* REST API design
* Spring Boot architecture
* JWT authentication and authorization
* Secure payment integration
* MongoDB data modeling
* Cloud deployment workflows
* Containerization with Docker
* React frontend development
* Marketplace system design
* Role-based access control
* Production deployment practices

---

# Future Improvements

* Real-time messaging between buyers and sellers
* Listing recommendation engine
* In-app notifications
* Advanced search and filtering
* Mobile application
* Rating and review system
* AI-powered fraud detection
* University email verification enforcement

---

Built as a secure, cloud-deployed marketplace platform to simplify buying, selling, and renting within university communities while providing hands-on experience with modern full-stack software engineering practices.
