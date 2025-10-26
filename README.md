# 🏥 MediQ - Sistema de Gestión Médica Integral

> **Demo en vivo:** [https://mediq-one.vercel.app](https://mediq-one.vercel.app)
> 
> **API Backend:** [https://mediq-backend-ba4f.onrender.com/api](https://mediq-backend-ba4f.onrender.com/api)

[![TypeScript](https://img.shields.io/badge/TypeScript-5.7-blue?logo=typescript)](https://www.typescriptlang.org/)
[![NestJS](https://img.shields.io/badge/NestJS-11.0-E0234E?logo=nestjs)](https://nestjs.com/)
[![Angular](https://img.shields.io/badge/Angular-19-DD0031?logo=angular)](https://angular.io/)
[![GraphQL](https://img.shields.io/badge/GraphQL-16-E10098?logo=graphql)](https://graphql.org/)
[![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?logo=docker)](https://www.docker.com/)

## 📋 Descripción

**MediQ** es un sistema completo de gestión médica desarrollado con tecnologías modernas, diseñado para clínicas multiespecialidad. Combina una arquitectura backend robusta con una interfaz de usuario intuitiva.

### ✨ Características Principales

- 🧑‍⚕️ **Gestión de Pacientes**: Fichas completas con historial médico, tratamientos y consentimientos
- 💊 **Tratamientos Personalizados**: Seguimiento de evoluciones, sesiones y facturación
- 📄 **Consentimientos Digitales**: Gestión de documentos firmados con validación y vencimiento
- 📊 **Dashboard Analítico**: Métricas en tiempo real sobre pacientes, tratamientos e ingresos
- 🔄 **API REST + GraphQL**: Doble interfaz de consulta de datos
- 🎨 **Multi-clínica**: Soporte para estética, fisioterapia, odontología y más
- 📧 **Sistema de Notificaciones**: Emails automáticos con plantillas personalizables
- ⚙️ **Configuración Flexible**: Campos de formulario y plantillas editables por clínica

---

## 🛠️ Stack Tecnológico

### Backend
- **Framework**: NestJS 11 (Node.js)
- **Lenguaje**: TypeScript 5.7
- **API**: REST + GraphQL (Apollo Server)
- **Base de Datos**: SQLite (desarrollo) / PostgreSQL (producción)
- **ORM**: TypeORM
- **Validación**: Class Validator + Class Transformer
- **Documentación**: Swagger/OpenAPI
- **Testing**: Jest

### Frontend
- **Framework**: Angular 19 (Standalone Components)
- **Lenguaje**: TypeScript 5.7
- **UI**: TailwindCSS 3
- **Estado**: Signals (Angular reactivity)
- **Desktop**: Electron (multiplataforma)
- **Validación**: Reactive Forms

### DevOps
- **Containerización**: Docker + Docker Compose
- **CI/CD**: GitHub Actions (preparado)
- **Deploy**: Railway (backend) + Vercel (frontend)
- **Volúmenes**: Persistencia de datos SQLite

---

## 🚀 Demo en Vivo

### 🌐 Aplicación Web
**URL**: [https://mediq-one.vercel.app](https://mediq-one.vercel.app)

**Modo Demo**: Navegación libre sin autenticación para evaluación rápida

### 📡 API REST
**Base URL**: `https://mediq-backend-ba4f.onrender.com/api`

**Documentación Swagger**: [https://mediq-backend-ba4f.onrender.com/api/docs](https://mediq-backend-ba4f.onrender.com/api/docs)

⚠️ **Nota**: Backend en tier gratuito de Render - primera carga puede tardar ~50 segundos

### 🎯 GraphQL Playground
**Endpoint**: `https://mediq-backend-ba4f.onrender.com/graphql`

Ejemplo de query:
```graphql
query {
  patients {
    id
    fullName
    dni
    email
    phone
  }
}
```

---

## 📸 Screenshots

### Dashboard Principal
![Dashboard](./screenshots/dashboard.png)
*Vista general con métricas de pacientes, tratamientos e ingresos*

### Gestión de Pacientes
![Pacientes](./screenshots/patients.png)
*Lista de pacientes con búsqueda y filtros avanzados*

### Detalle de Tratamiento
![Tratamiento](./screenshots/treatment-detail.png)
*Seguimiento completo de evoluciones y sesiones*

### GraphQL Playground
![GraphQL](./screenshots/graphql-playground.png)
*API GraphQL con schema interactivo*

---

## 🏗️ Arquitectura

```
┌─────────────────────────────────────────────────────────┐
│                    FRONTEND (Angular)                    │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐              │
│  │Components│  │ Services │  │  Signals │              │
│  └────┬─────┘  └────┬─────┘  └────┬─────┘              │
│       └─────────────┼─────────────┘                     │
└───────────────────┬─┴───────────────────────────────────┘
                    │ HTTP / WebSocket
┌───────────────────┴─┬───────────────────────────────────┐
│              BACKEND (NestJS)                            │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐              │
│  │REST API  │  │ GraphQL  │  │WebSocket │              │
│  └────┬─────┘  └────┬─────┘  └────┬─────┘              │
│       └─────────────┼─────────────┘                     │
│  ┌──────────────────┴──────────────────┐                │
│  │      Business Logic (Services)       │                │
│  └──────────────────┬──────────────────┘                │
│                     │                                    │
│  ┌──────────────────┴──────────────────┐                │
│  │        TypeORM (Repository)         │                │
│  └──────────────────┬──────────────────┘                │
└───────────────────┬─┴───────────────────────────────────┘
                    │
┌───────────────────┴─────────────────────────────────────┐
│             DATABASE (SQLite/PostgreSQL)                 │
│   Patients | Treatments | Consents | Billing            │
└─────────────────────────────────────────────────────────┘
```

---

## 🎯 Módulos Principales

### 1. Pacientes (`/api/patients`)
- CRUD completo de pacientes
- Búsqueda por DNI, nombre, email
- Historial médico detallado
- Relación con tratamientos y consentimientos

### 2. Tratamientos (`/api/treatments`)
- Gestión de tratamientos por especialidad
- Seguimiento de evoluciones y sesiones
- Estadísticas de progreso
- Facturación integrada

### 3. Consentimientos (`/api/consents`)
- Documentos digitales personalizables
- Firma electrónica con validación
- Control de vencimiento y renovación
- Templates por tipo de clínica

### 4. Dashboard (`/api/dashboard`)
- Métricas en tiempo real
- Gráficos de evolución temporal
- Indicadores clave de rendimiento (KPIs)

### 5. Configuración (`/api/clinic-config`)
- Personalización de campos de formulario
- Templates de documentos
- Configuración multi-clínica

---

## 🔧 Instalación Local

### Prerrequisitos
- Node.js 20+
- npm 10+
- Docker (opcional)

### Opción 1: Con Docker (Recomendado)

```bash
# Clonar repositorio
git clone https://github.com/Adravilag/MedIQ-Demo.git
cd MedIQ-Demo

# Levantar servicios
docker-compose up -d

# Acceder a:
# Frontend: http://localhost:4200
# Backend: http://localhost:3000/api
# GraphQL: http://localhost:3000/graphql
```

### Opción 2: Manual

#### Backend
```bash
cd MediQ-Backend
npm install
npm run start:dev

# Crear base de datos con datos de prueba
curl -X POST http://localhost:3000/api/seed
```

#### Frontend
```bash
cd MediQ-Frontend
npm install
npm start

# Abrir http://localhost:4200
```

---

## 📚 Documentación Técnica

### API REST
- **Swagger UI**: http://localhost:3000/api/docs
- **OpenAPI JSON**: http://localhost:3000/api/docs-json

### GraphQL
- **Playground**: http://localhost:3000/graphql
- **Schema SDL**: Generado automáticamente desde decoradores TypeScript

### Arquitectura
- **Patrón**: Modular + Repository Pattern
- **DTOs**: Validación automática con decoradores
- **Pipes**: Transformación y sanitización global
- **Guards**: Preparado para autenticación JWT (próximamente)

---

## 🧪 Testing

```bash
# Unit tests
npm test

# E2E tests
npm run test:e2e

# Coverage
npm run test:cov
```

---

## 🎓 Aprendizajes y Habilidades Demostradas

- ✅ **Arquitectura Full-Stack**: Integración completa backend-frontend
- ✅ **TypeScript Avanzado**: Decoradores, Generics, Types Guards
- ✅ **APIs Modernas**: REST + GraphQL en un mismo proyecto
- ✅ **Database Design**: Relaciones complejas con TypeORM
- ✅ **Validación Robusta**: Class Validator + Reactive Forms
- ✅ **Responsive Design**: TailwindCSS + Mobile First
- ✅ **Dockerización**: Containerización multi-stage
- ✅ **Clean Code**: SOLID, DRY, separación de responsabilidades
- ✅ **Git Flow**: Commits semánticos, branches organizadas

---

## 📞 Contacto

**Desarrollador**: Adrián Ávila García
- 📧 Email: adravilag@gmail.com
- 💼 LinkedIn: [linkedin.com/in/adravilag](https://linkedin.com/in/adravilag)
- 🐙 GitHub: [github.com/Adravilag](https://github.com/Adravilag)

---

## 📄 Licencia

Este proyecto es una demostración técnica open-source para propósitos educativos y de portfolio.

**Repositorios**:
- Frontend: [github.com/Adravilag/MedIQ-Frontend](https://github.com/Adravilag/MedIQ-Frontend)
- Backend: [github.com/Adravilag/MedIQ-Backend](https://github.com/Adravilag/MedIQ-Backend)

---

## ⚠️ Nota de Demo

Esta es una versión de demostración con datos ficticios generados mediante seeding. El backend se encuentra en tier gratuito de Render y puede tardar en despertar tras inactividad.

**Características de la Demo**:
- ✅ Backend completamente funcional en Render
- ✅ Frontend deployado en Vercel con auto-deploy
- ✅ Health monitoring automático del backend
- ✅ Indicadores visuales de estado del servidor
- ✅ Datos de prueba pre-cargados

**Última actualización**: Octubre 2025

