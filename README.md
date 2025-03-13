
# Healthcare Management System

A complete solution for managing patients, doctors, and healthcare services with secure authentication.

![Healthcare Management System](generated-icon.png)

## Features

- **User Authentication**: Secure login and registration system
- **Patient Management**: Add, view, update, and delete patient records
- **Doctor Management**: Manage doctor profiles with specialties and qualifications
- **Patient-Doctor Mapping**: Assign doctors to patients and track relationships
- **Responsive UI**: Clean, modern interface that works on all devices

## Tech Stack

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web framework
- **TypeScript** - Type-safe JavaScript
- **Drizzle ORM** - Database ORM for PostgreSQL
- **PostgreSQL** - Relational database
- **JWT Authentication** - Secure authentication

### Frontend
- **React** - UI library
- **TailwindCSS** - Utility-first CSS framework
- **Shadcn/UI** - Component library
- **React Hook Form** - Form validation
- **React Query** - Data fetching and state management
- **Wouter** - Simple routing

### Infrastructure
- **Railway** - PostgreSQL database hosting
- **Render** - Application deployment
- **Vite** - Build tool and development server

## Architecture

The application follows a client-server architecture:

```
├── client/            # React frontend application
│   ├── src/           # React components, pages & hooks
│   └── index.html     # HTML entry point
├── server/            # Express backend API
│   ├── routes.ts      # API route definitions
│   ├── storage.ts     # Data access layer
│   ├── auth.ts        # Authentication logic
│   ├── db.ts          # Database connection
│   └── index.ts       # Server entry point
├── shared/            # Shared code between client and server
│   └── schema.ts      # Database schema & validation
└── migrations/        # Database migrations
```

### Key Components:

1. **Express Server**: Handles API requests, authentication, and business logic
2. **React Frontend**: Provides the user interface and client-side logic
3. **Drizzle ORM**: Manages database interactions and schema
4. **JWT Authentication**: Secures API endpoints and user sessions

## Setup Instructions

### Prerequisites

- Node.js (v16 or higher)
- npm or yarn
- PostgreSQL database (Railway or local)

### Local Development

1. Clone the repository:
```bash
git clone <repository-url>
cd healthcare-management-system
```

2. Install dependencies:
```bash
npm install
```

3. Set up environment variables by creating a `.env` file in the root directory:
```
DATABASE_URL=postgresql://username:password@localhost:5432/healthcare_db
JWT_SECRET=your_jwt_secret_key
```

4. Run database migrations:
```bash
npm run db:push
```

5. Start the development server:
```bash
npm run dev
```

6. Access the application at http://localhost:5000

### Deployment

#### Database Setup (Railway)

1. Create a PostgreSQL database on [Railway](https://railway.app/)
2. Copy the connection string provided by Railway
3. Add the connection string to your environment variables as `DATABASE_URL`

#### Application Deployment (Render)

1. Create a new Web Service on [Render](https://render.com/)
2. Connect your repository
3. Set the following configuration:
   - **Build Command**: `npm install && npm run build`
   - **Start Command**: `npm run start`
   - **Environment Variables**: Add `DATABASE_URL` and `JWT_SECRET`
4. Deploy the application

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login and get JWT token

### Patients
- `GET /api/patients` - Get all patients
- `GET /api/patients/:id` - Get a specific patient
- `POST /api/patients` - Create a new patient
- `PUT /api/patients/:id` - Update a patient
- `DELETE /api/patients/:id` - Delete a patient

### Doctors
- `GET /api/doctors` - Get all doctors
- `GET /api/doctors/:id` - Get a specific doctor
- `POST /api/doctors` - Create a new doctor
- `PUT /api/doctors/:id` - Update a doctor
- `DELETE /api/doctors/:id` - Delete a doctor

### Patient-Doctor Mappings
- `GET /api/mappings` - Get all mappings
- `GET /api/mappings/:patientId` - Get mappings for a specific patient
- `POST /api/mappings` - Create a new mapping
- `DELETE /api/mappings/:id` - Delete a mapping

## License

MIT License

## Contributors

Add your name here
