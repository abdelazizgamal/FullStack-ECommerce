# 🛒 E-Commerce Platform

A full-stack e-commerce web application built with **Angular** and **ASP.NET Core Web API**, following clean layered architecture and REST principles. The system covers the complete shopping lifecycle — from product browsing and cart management to order processing — with role-based access for customers and admins.

---

## 📦 Repositories

| Layer | Repository |
|-------|-----------|
| Frontend | [angular-ecommerce-frontend](https://github.com/abdelazizgamal/frontend-repo) |
| Backend | [aspnet-ecommerce-api](https://github.com/abdelazizgamal/Ecommerce.API) |

---

## 🏗️ Architecture Overview

```
┌─────────────────────────┐         ┌──────────────────────────────┐
│     Angular Frontend    │  REST   │    ASP.NET Core Web API      │
│                         │ ──────► │                              │
│  Components / Services  │  JWT    │  Controllers / BLL / DAL     │
│  Routing / Guards       │ ◄────── │  Entity Framework Core       │
└─────────────────────────┘         └──────────────┬───────────────┘
                                                   │
                                                   ▼
                                        ┌─────────────────┐
                                        │   SQL Server    │
                                        └─────────────────┘
```

---

## ✨ Features

### Customer
- Browse and search products by name and category
- View full product details
- Add to cart, update quantities, remove items
- Checkout and place orders
- View order history

### Admin
- Full product and category management (CRUD)
- Monitor and manage orders
- Role-protected admin dashboard

### System
- JWT-based authentication and authorization
- Route guards for customer and admin pages
- Reactive forms with full validation
- Cart total and order total calculations
- Price snapshot preserved at order time

---

## 🔌 API Endpoints

### Authentication
```http
POST /api/auth/register
POST /api/auth/login
```

### Products
```http
GET    /api/products
GET    /api/products/{id}
POST   /api/products
PUT    /api/products/{id}
DELETE /api/products/{id}
```

### Categories
```http
GET    /api/categories
POST   /api/categories
PUT    /api/categories/{id}
DELETE /api/categories/{id}
```

### Cart & Orders
```http
GET    /api/cart
POST   /api/cart
PUT    /api/cart/{id}
DELETE /api/cart/{id}
POST   /api/orders
GET    /api/orders
```

---

## 🗄️ Database Design

Key entities and relationships:

```
Users ──────────── Orders
  │                  │
  └── Cart Items     └── Order Items ── Products
                                           │
                                        Categories
```

| Entity | Key Fields |
|--------|-----------|
| Users | Id, Name, Email, Role |
| Products | Id, Name, Price, Stock, CategoryId |
| Categories | Id, Name |
| Cart | UserId, ProductId, Quantity |
| Orders | Id, UserId, Total, Status |
| OrderItems | OrderId, ProductId, Quantity, PriceAtPurchase |

---

## 🛠️ Tech Stack

### Frontend
| Technology | Purpose |
|-----------|---------|
| Angular | SPA Framework |
| TypeScript | Language |
| Angular Router | Client-side routing & guards |
| Angular Reactive Forms | Form handling & validation |
| HTTP Client | API communication |

### Backend
| Technology | Purpose |
|-----------|---------|
| ASP.NET Core | Web API framework |
| C# | Language |
| Entity Framework Core | ORM & migrations |
| SQL Server | Database |
| JWT | Authentication |

---

## 🚀 Getting Started

### Prerequisites
- Node.js & Angular CLI
- .NET 9 SDK
- SQL Server

### Backend Setup
```bash
git clone https://github.com/abdelazizgamal/backend-repo
cd backend-repo
```
Update the connection string in `appsettings.json`:
```json
"ConnectionStrings": {
  "DefaultConnection": "Server=.;Database=ECommerceDB;Trusted_Connection=True;"
}
```
```bash
dotnet ef database update
dotnet run
```

### Frontend Setup
```bash
git clone https://github.com/abdelazizgamal/frontend-repo
cd frontend-repo
npm install
ng serve
```
App runs at `http://localhost:4200`

---

## 👤 Author

**Abdelaziz Gamal**
[linkedin.com/in/abdelaziz-gamal](https://www.linkedin.com/in/abdelaziz-gamal) · [github.com/abdelazizgamal](https://github.com/abdelazizgamal)
