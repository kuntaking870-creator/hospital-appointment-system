# Hospital Appointment Attendance & Analytics System

## Overview

A production-ready enterprise-grade web application designed to monitor appointment attendance, provide real-time operational dashboards, and generate comprehensive statistics for hospital management. This system integrates seamlessly with an existing Hospital Management System (HMS) through automated synchronization.

## Key Features

### 1. Automated HMS Integration
- **Read-only synchronization** with existing HMS through REST API or database connection
- **Automatic appointment import** with no manual data entry required
- **Real-time status updates** as patients move through the clinic workflow
- **No duplicate records** - intelligent synchronization service

### 2. Appointment Status Management
- **Booked**: When appointment is created in HMS
- **Attended**: When patient is added to doctor's queue
- **Completed**: When healthcare provider closes the patient's visit
- **No Show**: When patient was booked but never entered queue before clinic day ends

### 3. Real-Time Dashboard
- Total appointments booked for the day
- Number of patients attended
- Completed visits count
- No-show count
- Overall attendance percentage
- Visual charts for trends (daily, weekly, monthly, yearly)
- Clinic performance metrics
- Doctor performance metrics
- No-show trend analysis

### 4. Advanced Search Module
- Search by patient name, hospital number, NID, phone number
- Search by appointment date, clinic, doctor, or status
- View future appointments for any patient
- Check attendance history
- Track completed visits
- Identify missed appointments
- Display all appointments for a specific date
- Filter by attendance status

### 5. Comprehensive Reporting
- Daily, weekly, monthly, yearly attendance statistics
- No-show reports
- Clinic performance reports
- Doctor performance reports
- Attendance percentage analysis
- Appointment trend reports
- Export to PDF, Excel, CSV formats

### 6. Role-Based Access Control
- **Administrator**: Full system access and configuration
- **Receptionist**: View appointments and basic search
- **Clinic Manager**: Dashboard, reports, and clinic-specific data
- **Department Head**: Department and doctor performance metrics
- **Report Viewer**: Read-only report access

### 7. Security & Audit
- Microsoft Active Directory / LDAP integration
- Secure login and session management
- Complete audit logging of all activities
- User activity tracking
- Secure password management

## Technology Stack

### Backend
- **Framework**: ASP.NET Core 8 Web API
- **ORM**: Entity Framework Core
- **Database**: SQL Server
- **Architecture**: Clean Architecture
- **Patterns**: Repository Pattern, Dependency Injection
- **Logging**: Serilog
- **Validation**: FluentValidation

### Frontend
- **Framework**: React 18+
- **Language**: TypeScript
- **UI Library**: Material UI (MUI)
- **State Management**: Redux Toolkit
- **HTTP Client**: Axios
- **Charts**: Chart.js / Recharts
- **Responsive Design**: Mobile-first approach

### Infrastructure
- **Containerization**: Docker & Docker Compose
- **Database**: SQL Server
- **Message Queue**: RabbitMQ (optional, for background jobs)
- **Logging**: Serilog with ELK Stack support

## Project Structure

```
hospital-appointment-system/
├── backend/
│   ├── src/
│   │   ├── Hospital.Appointment.Domain/
│   │   ├── Hospital.Appointment.Application/
│   │   ├── Hospital.Appointment.Infrastructure/
│   │   ├── Hospital.Appointment.Presentation/
│   │   └── Hospital.Appointment.API/
│   ├── tests/
│   ├── Hospital.Appointment.sln
│   └── Dockerfile
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── store/
│   │   ├── hooks/
│   │   ├── types/
│   │   └── utils/
│   ├── public/
│   ├── package.json
│   ├── tsconfig.json
│   └── Dockerfile
├── database/
│   ├── scripts/
│   │   ├── 01_initial_schema.sql
│   │   ├── 02_seed_data.sql
│   │   └── migrations/
│   └── backups/
├── docs/
│   ├── API_DOCUMENTATION.md
│   ├── HMS_INTEGRATION_GUIDE.md
│   ├── INSTALLATION_GUIDE.md
│   ├── DEPLOYMENT_GUIDE.md
│   ├── ARCHITECTURE.md
│   └── USER_GUIDE.md
├── docker-compose.yml
├── .env.example
└── README.md
```

## Quick Start

### Prerequisites
- .NET 8 SDK
- Node.js 18+
- SQL Server 2019+
- Docker & Docker Compose (optional)

### Backend Setup
```bash
cd backend
dotnet restore
dotnet ef database update
dotnet run
```

### Frontend Setup
```bash
cd frontend
npm install
npm start
```

### Docker Setup
```bash
docker-compose up -d
```

## Database Schema

### Core Tables
- **Appointments**: Appointment records synced from HMS
- **Patients**: Patient information from HMS
- **Clinics**: Clinic/Department information
- **Doctors**: Healthcare provider information
- **AppointmentStatusHistory**: Status change tracking
- **Users**: System users and role assignments
- **AuditLogs**: Complete audit trail

## API Endpoints

### Appointments
- `GET /api/appointments` - List appointments with filtering
- `GET /api/appointments/{id}` - Get appointment details
- `GET /api/appointments/by-patient/{patientId}` - Patient appointments
- `GET /api/appointments/by-date/{date}` - Appointments by date
- `GET /api/appointments/statistics` - Appointment statistics

### Dashboard
- `GET /api/dashboard/summary` - Daily summary metrics
- `GET /api/dashboard/trends/{period}` - Trend data
- `GET /api/dashboard/clinic-performance` - Clinic metrics
- `GET /api/dashboard/doctor-performance` - Doctor metrics

### Reports
- `GET /api/reports/attendance/{period}` - Attendance report
- `GET /api/reports/no-shows/{period}` - No-show report
- `GET /api/reports/export/{format}` - Export report

### Authentication
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout
- `GET /api/auth/me` - Current user info

## Configuration

See `.env.example` for required environment variables:
- Database connection string
- HMS API endpoints
- LDAP/AD configuration
- JWT settings
- Logging configuration

## Deployment

See `docs/DEPLOYMENT_GUIDE.md` for:
- Production server setup
- SSL/TLS configuration
- Database backup and recovery
- Monitoring and logging
- Performance tuning
- Scaling considerations

## Security

- HTTPS only in production
- RBAC with claim-based authorization
- SQL injection prevention through parameterized queries
- CSRF protection
- Input validation and sanitization
- Secure password hashing (bcrypt)
- Audit logging of all user actions
- Rate limiting on API endpoints

## Support & Documentation

- **API Documentation**: `docs/API_DOCUMENTATION.md`
- **HMS Integration**: `docs/HMS_INTEGRATION_GUIDE.md`
- **Installation**: `docs/INSTALLATION_GUIDE.md`
- **Deployment**: `docs/DEPLOYMENT_GUIDE.md`
- **Architecture**: `docs/ARCHITECTURE.md`
- **User Guide**: `docs/USER_GUIDE.md`

## License

[Your Hospital] - All Rights Reserved

## Contact

For technical support and inquiries, please contact the development team.

---

**Version**: 1.0.0  
**Last Updated**: 2026-07-10  
**Status**: In Development
