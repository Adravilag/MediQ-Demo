# 🏥 MediQ - Sistema de Gestión Médica Integral

> **Demo en vivo:** [https://mediq-one.vercel.app](https://mediq-one.vercel.app)
> 
> **API Backend:** [https://mediq-backend-ba4f.onrender.com/api](https://mediq-backend-ba4f.onrender.com/api)
> 
> **Documentación Swagger:** [https://mediq-backend-ba4f.onrender.com/api/docs](https://mediq-backend-ba4f.onrender.com/api/docs)

[![TypeScript](https://img.shields.io/badge/TypeScript-5.7-blue?logo=typescript)](https://www.typescriptlang.org/)
[![NestJS](https://img.shields.io/badge/NestJS-11.0-E0234E?logo=nestjs)](https://nestjs.com/)
[![Angular](https://img.shields.io/badge/Angular-19-DD0031?logo=angular)](https://angular.io/)
[![GraphQL](https://img.shields.io/badge/GraphQL-16-E10098?logo=graphql)](https://graphql.org/)
[![TailwindCSS](https://img.shields.io/badge/Tailwind-3.4-38B2AC?logo=tailwind-css)](https://tailwindcss.com/)

---

## 📋 Descripción

**MediQ** es un sistema completo de gestión médica desarrollado con las últimas tecnologías web, diseñado para clínicas multiespecialidad (estética, fisioterapia, odontología). Combina una arquitectura backend robusta basada en NestJS con una interfaz moderna en Angular 19.

### 🎯 Demo Rápida

**¡Pruébalo ahora!** → [https://mediq-one.vercel.app](https://mediq-one.vercel.app)

⚠️ **Nota**: El backend está en tier gratuito de Render. La primera carga puede tardar ~50 segundos mientras el servidor despierta. El frontend incluye un **indicador de estado** que te avisa cuando el backend está listo.

---

### ✨ Características Principales

- 🧑‍⚕️ **Gestión de Pacientes**: Fichas completas con historial médico, información de contacto y documentación
- 💊 **Tratamientos Personalizados**: Control de evoluciones, sesiones y facturación integrada
- 📄 **Consentimientos Digitales**: Firma electrónica, validación y trazabilidad completa
- 📊 **Dashboard Analítico**: Métricas en tiempo real (pacientes, ingresos, tratamientos activos)
- 🔄 **API REST + GraphQL**: Doble interfaz de consulta de datos con documentación Swagger
- 🎨 **Multi-especialidad**: Configurable para estética, fisioterapia, odontología, medicina general
- 🔍 **Búsqueda Avanzada**: Filtros dinámicos por estado, fecha, tipo de tratamiento
- ⚙️ **Sistema Configurable**: Campos de formulario y plantillas personalizables por clínica
- 📱 **Responsive Design Completo**: Sistema responsive con **ResponsiveService**, directivas custom y tabla híbrida que alterna entre vista de tabla (desktop) y cards (móvil). 5 breakpoints configurados con **Angular CDK BreakpointObserver**
- 🔔 **Backend Health Monitoring**: Indicador visual del estado del servidor en tiempo real

---

## 🛠️ Stack Tecnológico

### Backend
- **Framework**: NestJS 11 (Node.js con TypeScript)
- **API**: REST + GraphQL (Apollo Server)
- **Base de Datos**: TypeORM + SQLite/PostgreSQL
- **Validación**: Class Validator + DTOs
- **Documentación**: Swagger/OpenAPI automático
- **Deploy**: Render (tier gratuito)

### Frontend
- **Framework**: Angular 19 con Standalone Components
- **UI**: TailwindCSS 3 + DaisyUI
- **Estado**: Signals (nueva API de reactividad de Angular)
- **Formularios**: Reactive Forms con validación
- **Deploy**: Vercel con auto-deploy desde GitHub
- **Desktop**: Electron (versión desktop disponible Diciembre 2025)

### Features Técnicos
- 🔒 **CORS configurado** para Vercel + subdominios
- ⚡ **Lazy Loading** de módulos para mejor performance
- 🎨 **Componentes SVG optimizados** con carga síncrona
- 🔄 **Health Check** automático cada 30s
- 📦 **Modular Architecture** con separación de responsabilidades
- ✅ **DTO Validation** en todas las peticiones
- 🌍 **Environment Management** (dev/prod)
- 📱 **Sistema Responsive Completo** con ResponsiveService + Angular CDK
- 🎯 **Directivas Custom Responsive**: `*appResponsive`, `[appResponsiveClass]`, `appResponsiveGrid`
- 📊 **Tabla Híbrida**: Alterna automáticamente entre tabla (desktop) y cards (móvil)

---

## 🚀 Demo en Vivo

### 🌐 Aplicación Web
**URL**: [https://mediq-one.vercel.app](https://mediq-one.vercel.app)

**Modo Demo**: Navegación libre sin autenticación. Datos de prueba pre-cargados mediante seeding.

**Características destacadas para probar**:
- ✅ Dashboard con métricas en tiempo real
- ✅ Búsqueda y filtros avanzados de pacientes
- ✅ Creación y edición de tratamientos
- ✅ Sistema de consentimientos con auditoría
- ✅ Configuración multi-especialidad
- ✅ Indicador de estado del backend (arriba a la derecha)

### 📡 API REST + Swagger
**Base URL**: `https://mediq-backend-ba4f.onrender.com/api`

**Documentación Interactiva**: [https://mediq-backend-ba4f.onrender.com/api/docs](https://mediq-backend-ba4f.onrender.com/api/docs)

Endpoints principales:
- `GET /api/patients` - Listar pacientes
- `GET /api/treatments` - Listar tratamientos
- `GET /api/consents` - Listar consentimientos
- `GET /api/dashboard/metrics` - Métricas del dashboard
- `GET /api/health` - Health check del servidor

⚠️ **Nota**: Backend en tier gratuito de Render - primera carga puede tardar ~50 segundos en despertar

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
    treatments {
      id
      name
      status
    }
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

## 🎓 Habilidades Técnicas Demostradas

- ✅ **Full-Stack Development**: Integración completa backend NestJS + frontend Angular
- ✅ **TypeScript Avanzado**: Decoradores, Generics, Type Guards, DTOs tipados
- ✅ **APIs Modernas**: REST + GraphQL en un mismo proyecto con documentación automática
- ✅ **Database Design**: Relaciones complejas (One-to-Many, Many-to-One) con TypeORM
- ✅ **Validación Robusta**: Class Validator (backend) + Reactive Forms (frontend)
- ✅ **Arquitectura Modular**: Separación de responsabilidades, Repository Pattern
- ✅ **UI/UX Moderno**: TailwindCSS, componentes reutilizables, diseño responsive
- ✅ **State Management**: Angular Signals para reactividad eficiente
- ✅ **Responsive Design Avanzado**: ResponsiveService con Angular CDK, directivas custom, tabla híbrida
- ✅ **DevOps**: Deploy automatizado en Vercel + Render, CORS, environment management
- ✅ **Clean Code**: SOLID principles, código documentado, commits semánticos
- ✅ **Error Handling**: Manejo de errores, validaciones, mensajes de usuario
- ✅ **Performance**: Lazy loading, optimización de bundles, health monitoring, debouncing

---

## 📞 Contacto y Enlaces

**Desarrollador**: Adrián Ávila García

📧 **Email**: adravilag@gmail.com  
💼 **LinkedIn**: [linkedin.com/in/adravilag](https://linkedin.com/in/adravilag)  
🐙 **GitHub**: [github.com/Adravilag](https://github.com/Adravilag)

**Repositorios del Proyecto**:
- 🎨 **Frontend**: [github.com/Adravilag/MedIQ-Frontend](https://github.com/Adravilag/MedIQ-Frontend)
- ⚙️ **Backend**: [github.com/Adravilag/MedIQ-Backend](https://github.com/Adravilag/MedIQ-Backend)
- 📚 **Demo & Docs**: [github.com/Adravilag/MedIQ-Demo](https://github.com/Adravilag/MedIQ-Demo)

---

## 📄 Licencia

Este proyecto es una demostración técnica **open-source** para propósitos educativos y de portfolio.

MIT License - Ver repositorios individuales para más detalles.

---

## ⚠️ Nota de Demo

**Características de la Demo en Producción**:
- ✅ Backend desplegado en **Render** (tier gratuito)
- ✅ Frontend desplegado en **Vercel** con auto-deploy desde GitHub
- ✅ **Health monitoring** automático con indicador visual
- ✅ Menú deshabilitado cuando backend está offline (UX mejorada)
- ✅ Datos de prueba pre-cargados mediante seeding
- ✅ Documentación Swagger completamente funcional
- 🚧 **Versión Desktop (Electron)**: Disponible Diciembre 2025

**Limitaciones del Tier Gratuito**:
- ⏱️ Backend puede tardar ~50 segundos en despertar tras inactividad
- 💾 Base de datos SQLite en memoria (datos se resetean periódicamente)
- 🔄 Sin persistencia permanente de cambios

**Para Evaluadores/Reclutadores**: El código fuente completo está disponible públicamente en los repositorios de GitHub enlazados arriba. No dudes en contactar para cualquier consulta técnica.

---

**Última actualización**: Octubre 2025  
**Versión**: 1.0.0

