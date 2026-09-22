# Care System

A centralized **care and follow-up management system** designed to organize families, individuals, servants, and continuous visitation records within the service.

The system helps servants and service administrators maintain structured records, track follow-ups, distribute responsibilities, and ensure that no individual or family is overlooked.

---

## ✨ Features

- 👥 **User Management**
  - Different roles for service members
  - Secure authentication
  - Role-based access control

- 🏠 **Family Management**
  - Organize individuals into families (`Osra`)
  - Assign families to specific service groups
  - Track family information and relationships

- 🎓 **Batch Management**
  - Organize service members into batches (`Dof3a`)
  - Connect families and servants to their corresponding batch

- 📍 **Region Management**
  - Organize service activities by region
  - Currently supported regions include:
    - Janaklees
    - Victoria
    - Sidi Bishr

- 🤝 **Continuous Care & Follow-up**
  - Record visits and follow-ups
  - Track the responsible servant
  - Maintain a history of care activities
  - Monitor the status of follow-ups

- 📊 **Service Administration**
  - Manage servants and responsibilities
  - Monitor service activity
  - Keep service data organized in one system

---

## 👤 User Roles

The system currently supports the following roles:

| Role          | Description                                                   |
| ------------- | ------------------------------------------------------------- |
| `Khadem`      | Servant responsible for assigned individuals/families         |
| `Amin_Khedma` | Service secretary responsible for managing service activities |
| `Amin_dof3a`  | Batch secretary responsible for a specific batch              |
| `Admin`       | System administrator with full access                         |

---

## 🗂️ Main Entities

The database is organized around the following core entities:

### User

Stores system users and their roles.

```text
User
├── id
├── name
├── username
├── password_hash
├── role
├── phone_number
└── created_at
```

### Dof3a

Represents a service batch/group.

### Osra

Represents a family/group of individuals.

### Region

Represents the geographical/service area associated with the family or service activity.

### Care / Follow-up

Stores continuous care activities and visitation records, allowing the service to maintain a history of interactions and follow-ups.

---

## 🏗️ System Architecture

The project is divided into two main applications:

```text
care-system/
│
├── frontend/
│   └── Web Application
│
├── backend/
│   └── REST API
│
├── database/
│   └── Database schema / migrations
│
└── README.md
```

### Frontend

The frontend provides the user interface for:

- Authentication
- Dashboard
- Family management
- Batch management
- Care/follow-up records
- User management
- Service administration

### Backend

The backend is responsible for:

- Authentication & authorization
- Business logic
- User management
- Family and batch management
- Care records
- Database communication
- API endpoints

### Database

A relational database is used to maintain structured relationships between:

```text
Users
  ↓
Batches
  ↓
Families
  ↓
Individuals
  ↓
Care / Follow-ups
  ↓
Visits & Notes
```

---

## 🔐 Authentication & Authorization

The system uses authenticated user accounts and role-based authorization.

Passwords are stored as **hashed values** rather than plain text.

Access to system functionality depends on the user's role.

For example:

```text
Admin
 ├── Manage users
 ├── Manage service structure
 └── Access all records

Amin_Khedma
 ├── Manage service-related records
 └── Monitor servants and follow-ups

Amin_dof3a
 ├── Manage assigned batch
 └── Follow up with its families

Khadem
 └── Manage assigned care activities
```

---

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed:

- Node.js
- npm
- Git
- PostgreSQL
- A package manager such as npm

---

## 📥 Installation

Clone the repository:

```bash
git clone https://github.com/mirollawa2l/CARE
```

### Backend

```bash
cd backend
npm install
```

Create your environment file:

```bash
cp .env.example .env
```

Configure the required environment variables:

```env
DATABASE_URL=your_database_url
JWT_SECRET=your_jwt_secret
PORT=5000
```

Start the backend:

```bash
npm run dev
```

---

### Frontend

Open another terminal:

```bash
cd frontend
npm install
```

Create the frontend environment file if required:

```bash
cp .env.example .env
```

Configure the API URL:

```env
VITE_API_URL=http://localhost:5000
```

Start the frontend:

```bash
npm run dev
```

---

## 🌳 Project Structure

```text
care-system/
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── hooks/
│   │   └── ...
│   ├── public/
│   └── package.json
│
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   ├── routes/
│   │   ├── services/
│   │   ├── middleware/
│   │   ├── models/
│   │   └── ...
│   ├── prisma/
│   └── package.json
│
├── .gitignore
└── README.md
```

---

## 🔄 Care Workflow

The general workflow is:

```text
Admin / Service Secretary
          │
          ▼
     Create Users
          │
          ▼
     Create Batches
          │
          ▼
      Create Families
          │
          ▼
    Assign Servants
          │
          ▼
   Continuous Follow-up
          │
          ▼
    Record Visits
          │
          ▼
   Review & Monitoring
```

Each follow-up can become part of the family's history, allowing servants to understand previous interactions instead of starting from zero every time.

---

## 🔒 Security

The system follows common security practices including:

- Password hashing
- Authentication tokens
- Role-based authorization
- Environment variables for secrets
- Input validation
- Protected API routes
- No sensitive credentials committed to Git

Never commit your `.env` files.

---

## 🧪 Testing

Run backend tests with:

```bash
npm test
```

Run frontend tests with:

```bash
npm test
```

For production builds:

```bash
npm run build
```

---

## 🛠️ Technologies

The exact technologies may evolve during development, but the system is structured around:

- **Frontend:** React / TypeScript
- **Backend:** Node.js / TypeScript
- **Database:** PostgreSQL
- **Authentication:** JWT
- **API:** REST
- **Version Control:** Git / GitHub

---

## 📌 Future Improvements

Possible future additions include:

- 📱 Mobile-friendly interface
- 🔔 Follow-up reminders
- 📅 Scheduled visits
- 📊 Service statistics and dashboards
- 🗺️ Region-based visualization
- 📈 Follow-up analytics
- 🔍 Advanced search and filtering
- 📋 Exportable reports
- 🔐 More granular permissions
- 📝 Detailed visit notes and history
- 🔔 Notifications for overdue follow-ups

---

## 🤝 Contributing

Contributions are welcome.

1. Fork the repository
2. Create a feature branch

```bash
git checkout -b feature/your-feature
```

3. Commit your changes

```bash
git commit -m "Add your feature"
```

4. Push the branch

```bash
git push origin feature/your-feature
```

5. Open a Pull Request

---

## 📄 License

This project is intended for service management and organizational purposes.

Add the project's chosen license here if the repository will be distributed publicly.
