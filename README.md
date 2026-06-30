# 🧁 BakeCharm — Smart Bakery Management & Ordering System

BakeCharm is a full-stack web application for managing and ordering from a bakery online — built as a Web Engineering project. It pairs a React frontend with an ASP.NET Core Web API and a MongoDB database, and covers the full flow from product browsing to checkout to admin management.

<!--
  📸 ADD SCREENSHOTS HERE before publishing.
  Suggested shots: home/catalogue page, product detail, custom cake builder,
  cart & checkout, admin dashboard. See "Screenshots" section below.
-->

## ✨ Features

- **Customer accounts** — registration with email verification and secure password hashing on the API
- **Product catalogue** — categories, filters, ratings, pricing, recommendations, and reviews
- **Custom cake builder** — real-time price calculation via API, with client-side fallback
- **Cart & checkout** — delivery-slot capacity validation
- **Order lifecycle** — order creation, inventory deduction, loyalty points, and status tracking
- **Admin dashboard** — products, inventory, delivery slots, promotions, orders, and analytics
- **Offline-friendly frontend** — gracefully falls back to local demo JSON if the API is unreachable

## 🛠️ Tech Stack

| Layer    | Technology |
|----------|------------|
| Frontend | React 19, Vite, Bootstrap 5, Axios, lucide-react |
| Backend  | ASP.NET Core Web API (.NET 10), C# |
| Database | MongoDB |

## 📂 Project Structure

```text
BakeCharm/
├── frontend/        React + Bootstrap client (Vite)
├── backend/         ASP.NET Core Web API + MongoDB models/services
├── database/        MongoDB export notes, JSON exports, dump/restore scripts
└── server/          Setup notes and handoff guide
```

## 🚀 Getting Started

### Prerequisites

- [Node.js 20 LTS+](https://nodejs.org/) (includes npm)
- [.NET SDK 10](https://dotnet.microsoft.com/download)
- [MongoDB Community Server](https://www.mongodb.com/try/download/community), running locally
- (Optional) [MongoDB Compass](https://www.mongodb.com/products/compass) to inspect the database

### 1. Start MongoDB

Make sure MongoDB is running locally at:

```text
mongodb://localhost:27017
```

The backend will automatically create and seed the `BakeCharmDb` database on first run if it's empty — no manual setup required. To transfer an existing database from another machine, see [`database/README-DATABASE.md`](database/README-DATABASE.md).

### 2. Run the backend

```bash
cd backend
dotnet restore
dotnet run
```

The API will be available at `http://localhost:5118`.

### 3. Run the frontend

```bash
cd frontend
npm install
npm run dev
```

Open the URL Vite prints in the terminal (usually `http://localhost:5173`).

## 🔑 Demo Accounts

| Role     | Email                      | Password         |
|----------|-----------------------------|-------------------|
| Admin    | `admin@bakecharm.test`      | `Admin@12345`     |
| Customer | `maya@bakecharm.test`       | `Customer@12345`  |

> Email delivery is simulated in the API response/logs, so the project can be demonstrated fully without SMTP configuration.


## 🗺️ Roadmap / Possible Improvements

- [ ] Real SMTP integration for email verification and order confirmations
- [ ] Payment gateway integration
- [ ] Automated tests (unit + integration)
- [ ] CI/CD pipeline (GitHub Actions)

## 📄 License

This project is licensed under the [MIT License](LICENSE).
