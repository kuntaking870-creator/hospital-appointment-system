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
- **Charts**: Recharts
- **Responsive Design**: Mobile-first approach

### Infrastructure
- **Containerization**: Docker & Docker Compose
- **Database**: SQL Server
- **Logging**: Serilog with ELK Stack support

## Quick Start

### Prerequisites
- .NET 8 SDK
- Node.js 18+
- SQL Server 2019+
- Docker & Docker Compose (optional)

## Documentation

- **API Documentation**: `docs/API_DOCUMENTATION.md`
- **HMS Integration**: `docs/HMS_INTEGRATION_GUIDE.md`
- **Installation**: `docs/INSTALLATION_GUIDE.md`
- **Deployment**: `docs/DEPLOYMENT_GUIDE.md`
- **Architecture**: `docs/ARCHITECTURE.md`
- **User Guide**: `docs/USER_GUIDE.md`

## License

All Rights Reserved

---

**Version**: 1.0.0  
**Last Updated**: 2026-07-10  
**Status**: In Development