# Product Management System

A full-stack, minimalistic Product Management System built with Node.js, Express, MongoDB, and modern Tailwind CSS. Rendered server-side with EJS templates, this application features a sleek **Dark Glassmorphism** user interface, role-based access control (RBAC), and robust data validation.

## ✨ Features

- **Storefront (Customer Portal):** Browse products via a glass-themed, responsive grid. View specific product details and dynamically filter by category or search term.
- **Admin Dashboard:** A secured management panel providing CRUD operations for both Products and Categories, paired alongside overarching store metrics.
- **Role-Based Access Control (RBAC):** Distinct roles for `customer` and `admin`. Admin access is strictly protected by JWT-based authentication and custom middleware.
- **Sleek UI/UX Engine:** The entire frontend utilizes **Tailwind CSS v4** to render a beautiful, dark glassmorphism aesthetic (`backdrop-blur`, custom mesh gradients, nested translucent cards).
- **Security & Reliability:** Features robust `Joi` validation schemas for all incoming data and securely hashed passwords utilizing `bcryptjs`.
- **Automated Seeding:** On launch, the database guarantees the existence of a default Admin user, simplifying the deployment process.

## 🛠️ Tech Stack

- **Backend Environment:** Node.js, Express.js
- **Database Architecture:** MongoDB, Mongoose ODM
- **Frontend Views:** EJS (Embedded JavaScript Templates)
- **Styling Engine:** Tailwind CSS v4 (via PostCSS/CLI)
- **Authentication:** JSON Web Tokens (JWT), Cookie-Parser
- **File Uploads:** Multer (Local disk storage)

## 🚀 Getting Started

### Prerequisites
Make sure you have the following installed on your machine:
- Node.js (v18+)
- MongoDB (Running locally or an Atlas URI)

### 1. Clone the repository
```bash
git clone <your-repository-url>
cd product-management-system
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Environment Variables
Create a `.env` file in the root directory and configure the following:
```env
PORT=3000
MONGODB_URI=mongodb://127.0.0.1:27017/product_management
SESSION_SECRET=your_super_secret_session_key
JWT_SECRET=your_super_secret_jwt_key
ADMIN_PASSWORD=Admin1234
```

### 4. Build the Stylesheet
Before starting the application, ensure Tailwind generates the required CSS classes used by your EJS templates:
```bash
npm run build:css
```

### 5. Running the Application
Start the development server using nodemon:
```bash
npm run dev
```

The application will be accessible at: `http://localhost:3000`

## 🔑 Default Credentials

Upon starting the server, an admin account is automatically seeded into the database (if one doesn't already exist).
Access the Admin Dashboard automatically with:

- **Admin Login Route:** `/auth/admin/login`
- **Email:** `admin@gmail.com`
- **Password:** `Admin1234` *(or whatever you configure in `ADMIN_PASSWORD`)*

## 📂 Project Structure

```
├── app/
│   ├── controller/      # Business logic (auth, admin, customer)
│   ├── middleware/      # Admin guard, Auth verification
│   ├── models/          # Mongoose Schemas (User, Product, Category)
│   ├── routes/          # Express Routers
│   └── utils/           # Joi validation schemas
├── public/              
│   └── css/             # Tailwind input/output stylesheets
├── views/               
│   ├── admin/           # Dashboard, Product/Category CRUD forms
│   ├── auth/            # Login, Registration pages
│   ├── customer/        # Storefront interfaces
│   └── partials/        # Global headers, sidebars, footers
├── .env                 # Environment config
├── app.js               # Express entrypoint & Database connection
└── package.json         # Scripts and Project dependencies
```

