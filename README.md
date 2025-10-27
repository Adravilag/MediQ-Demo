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
![Dashboard](./screenshots/dashboard.jpeg)
*Vista general con métricas de pacientes, tratamientos e ingresos en tiempo real*

### Gestión de Pacientes
![Pacientes - Lista](./screenshots/patients.jpeg)
*Lista de pacientes con búsqueda y filtros avanzados*

![Pacientes - Detalle](./screenshots/patients-details-info.jpeg)
*Ficha completa del paciente con información personal y contacto*

![Pacientes - Tratamientos](./screenshots/patients-details-treatment.jpeg)
*Historial de tratamientos asociados al paciente*

![Pacientes - Consentimientos](./screenshots/patients-details-consents.jpeg)
*Consentimientos firmados del paciente*

### Gestión de Tratamientos
![Tratamientos - Lista](./screenshots/treatments.jpeg)
*Panel de tratamientos activos y completados*

![Tratamientos - Detalle](./screenshots/treatments-details-historial.jpeg)
*Seguimiento detallado de evoluciones y sesiones*

![Tratamientos - Facturación](./screenshots/treatments-details-billing.jpeg)
*Control de facturación y pagos del tratamiento*

### Consentimientos Digitales
![Consentimientos - Lista](./screenshots/consents.jpeg)
*Gestión de consentimientos informados*

![Consentimientos - Detalle](./screenshots/consents-details.jpeg)
*Vista detallada del documento de consentimiento*

![Consentimientos - Firma](./screenshots/consent-details-signatured.jpeg)
*Consentimiento con firma digital y validación*

![Consentimientos - Auditoría](./screenshots/consents-details-audit.jpeg)
*Registro de auditoría y trazabilidad del documento*

### Sistema de Configuración
![Configuración - Sistema](./screenshots/config-system.jpeg)
*Configuración general de la clínica y especialidades*

![Configuración - Templates](./screenshots/config-templates.jpeg)
*Personalización de plantillas de documentos*

---

##  Aprendizajes y Habilidades Demostradas

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

