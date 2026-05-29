# Property Management Tool with M-Pesa STK PUSH Integration

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Node.js](https://img.shields.io/badge/Node.js-18+-green.svg)](https://nodejs.org/)
[![React](https://img.shields.io/badge/React-18+-blue.svg)](https://reactjs.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-12+-336791.svg)](https://www.postgresql.org/)

## 🏢 Overview

A comprehensive property management system designed for Kenyan businesses with integrated M-Pesa STK PUSH payment collection. Manage properties, tenants, rent payments, and maintenance requests all in one platform.

## ✨ Features

### 💼 Property Management
- Add, edit, and delete properties
- Manage multiple units per property
- Track occupancy status
- Set and manage rental rates
- Property documentation and details

### 👥 Tenant Management
- Add and manage tenant information
- Track lease agreements
- Document storage (IDs, contracts, etc.)
- Emergency contact management
- Payment history per tenant

### 💰 Payment Collection
- **M-Pesa STK PUSH Integration**
- Automatic payment initiation
- Real-time payment status tracking
- Payment confirmation and receipts
- Payment history and reports
- Transaction reconciliation

### 📊 Dashboard & Reporting
- Revenue overview and analytics
- Outstanding payments tracking
- Property occupancy metrics
- Recent transaction history
- Comprehensive reporting
- System alerts and notifications

### 🔧 Maintenance Management
- Create maintenance requests
- Track maintenance status
- Assign maintenance tasks
- Cost tracking

### 🔐 Security
- User authentication (JWT)
- Role-based access control
- Secure M-Pesa integration
- Data encryption
- Input validation and sanitization

## 🚀 Tech Stack

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **PostgreSQL** - Database
- **JWT** - Authentication
- **Axios** - HTTP client
- **Joi** - Data validation

### Frontend
- **React 18** - UI library
- **React Router** - Navigation
- **Axios** - API calls
- **TailwindCSS** - Styling
- **React Hook Form** - Form management
- **Zustand** - State management
- **Recharts** - Data visualization

## 📋 Prerequisites

- Node.js v16 or higher
- npm or yarn
- PostgreSQL 12 or higher
- Git
- M-Pesa Daraja API credentials (Consumer Key, Consumer Secret, Business Shortcode, Passkey)

## 🛠️ Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/jeremiahjohn52-design/Property--management-Hub.git
cd Property--management-Hub
```

### 2. Backend Setup

```bash
cd backend
npm install

# Create .env file
cp .env.example .env

# Edit .env with your credentials
nano .env

# Start the server
npm run dev
```

**Backend runs on**: http://localhost:5000

### 3. Frontend Setup

```bash
cd frontend
npm install

# Create .env file
cp .env.example .env

# Start the development server
npm start
```

**Frontend runs on**: http://localhost:3000

## 📝 Environment Variables

### Backend (.env)
```env
# Server
NODE_ENV=development
PORT=5000

# Database
DATABASE_URL=postgresql://user:password@localhost:5432/property_mgmt

# JWT
JWT_SECRET=your_secret_key_here
JWT_EXPIRE=7d

# M-Pesa Daraja API
MPESA_CONSUMER_KEY=your_consumer_key
MPESA_CONSUMER_SECRET=your_consumer_secret
MPESA_BUSINESS_SHORTCODE=your_shortcode
MPESA_PASSKEY=your_passkey
MPESA_ENVIRONMENT=sandbox
MPESA_CALLBACK_URL=https://your-domain.com/api/payments/mpesa-callback

# Email (Optional)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your_email@gmail.com
SMTP_PASS=your_app_password
```

### Frontend (.env)
```env
REACT_APP_API_URL=http://localhost:5000/api
REACT_APP_ENV=development
```

## 📚 API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout
- `POST /api/auth/refresh-token` - Refresh JWT token

### Properties
- `GET /api/properties` - List all properties
- `POST /api/properties` - Create new property
- `GET /api/properties/:id` - Get property details
- `PUT /api/properties/:id` - Update property
- `DELETE /api/properties/:id` - Delete property

### Tenants
- `GET /api/tenants` - List all tenants
- `POST /api/tenants` - Add new tenant
- `GET /api/tenants/:id` - Get tenant details
- `PUT /api/tenants/:id` - Update tenant
- `DELETE /api/tenants/:id` - Delete tenant

### Payments
- `POST /api/payments/initiate-stk` - Initiate M-Pesa STK PUSH
- `POST /api/payments/mpesa-callback` - M-Pesa payment callback
- `GET /api/payments/status/:checkoutRequestId` - Check payment status
- `GET /api/payments/history` - Get payment history
- `GET /api/payments/tenant/:tenantId` - Get tenant payment history

### Maintenance
- `GET /api/maintenance` - List maintenance requests
- `POST /api/maintenance` - Create maintenance request
- `PUT /api/maintenance/:id` - Update maintenance request
- `DELETE /api/maintenance/:id` - Delete maintenance request

## 🔑 Getting M-Pesa Credentials

1. Visit [Safaricom Daraja Portal](https://developer.safaricom.co.ke/)
2. Sign up or log in
3. Create a new application
4. Generate credentials:
   - Consumer Key
   - Consumer Secret
   - Business Shortcode
   - Passkey
5. Set callback URL in your application settings

## 🧪 Testing

### API Testing with Postman
1. Import the Postman collection from `docs/postman-collection.json`
2. Set up environment variables
3. Test endpoints

### Testing M-Pesa Integration
- Use Sandbox environment first
- Test with valid Safaricom test phone numbers
- Verify callback handling

## 📦 Database Setup

### Create Database
```bash
creatdb property_mgmt
```

### Run Migrations
```bash
cd backend
npm run migrate
```

### Seed Database (Optional)
```bash
npm run seed
```

## 🚀 Deployment

### Backend Deployment (Render/Heroku)
```bash
# Set environment variables in your hosting platform
# Push to production
git push heroku main
```

### Frontend Deployment (Vercel/Netlify)
```bash
# Using Vercel
vercel

# Using Netlify
netlify deploy
```

## 📄 Project Structure

```
property-management-mpesa/
├── backend/
│   ├── src/
│   │   ├── config/
│   │   ├── controllers/
│   │   ├── middleware/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── services/
│   │   ├── utils/
│   │   ├── database/
│   │   └── app.js
│   ├── .env.example
│   ├── package.json
│   └── server.js
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── hooks/
│   │   ├── context/
│   │   ├── styles/
│   │   └── App.jsx
│   ├── .env.example
│   ├── package.json
│   └── public/
├── docs/
├── .gitignore
└── README.md
```

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📋 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🆘 Support

For support, email support@example.com or open an issue in the repository.

## 🎯 Roadmap

- [ ] Mobile app (React Native)
- [ ] Expense tracking
- [ ] Automated payment reminders
- [ ] Document management system
- [ ] Integration with other payment providers
- [ ] Multi-currency support
- [ ] Advanced analytics and reporting
- [ ] WhatsApp integration for notifications

## 👨‍💻 Author

**Jeremiah John**
- GitHub: [@jeremiahjohn52-design](https://github.com/jeremiahjohn52-design)

---

**Made with ❤️ for Kenyan property managers**
