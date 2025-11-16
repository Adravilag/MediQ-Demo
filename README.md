#  MediQ - Sistema de Gestión Médica Integral

> **Demo en vivo:** [https://mediq-frontend-kj92.onrender.com](https://mediq-frontend-kj92.onrender.com)
>  
> **Documentación Swagger:** [https://mediq-backend-f6ud.onrender.com/api/docs](https://mediq-backend-f6ud.onrender.com/api/docs)

[![TypeScript](https://img.shields.io/badge/TypeScript-5.7-blue?logo=typescript)](https://www.typescriptlang.org/)
[![NestJS](https://img.shields.io/badge/NestJS-11.0-E0234E?logo=nestjs)](https://nestjs.com/)
[![Angular](https://img.shields.io/badge/Angular-19-DD0031?logo=angular)](https://angular.io/)
[![GraphQL](https://img.shields.io/badge/GraphQL-16-E10098?logo=graphql)](https://graphql.org/)
[![TailwindCSS](https://img.shields.io/badge/Tailwind-3.4-38B2AC?logo=tailwind-css)](https://tailwindcss.com/)

---

##  Descripción

**MediQ** es un sistema completo de gestión médica desarrollado con las últimas tecnologías web, diseñado para clínicas multiespecialidad (estética, fisioterapia, odontología). Combina una arquitectura backend robusta basada en NestJS con una interfaz moderna en Angular 19.

###  Demo Rápida

**¡Pruébalo ahora!** → [https://mediq-frontend-kj92.onrender.com](https://mediq-frontend-kj92.onrender.com)

 **Nota**: El backend está en tier gratuito de Render. La primera carga puede tardar ~50 segundos mientras el servidor despierta. El frontend incluye un **indicador de estado** que te avisa cuando el backend está listo.

---

###  Características Principales

-  **Gestión de Pacientes**: Fichas completas con historial médico, información de contacto y documentación
-  **Tratamientos Personalizados**: Control de evoluciones, sesiones y facturación integrada
-  **Consentimientos Digitales**: Firma electrónica, validación y trazabilidad completa
-  **Dashboard Analítico**: Métricas en tiempo real (pacientes, ingresos, tratamientos activos)
-  **API REST + GraphQL**: Doble interfaz de consulta de datos con documentación Swagger
-  **Multi-especialidad**: Configurable para estética, fisioterapia, odontología, medicina general
-  **Búsqueda Avanzada**: Filtros dinámicos por estado, fecha, tipo de tratamiento
-  **Sistema Configurable**: Campos de formulario y plantillas personalizables por clínica
-  **Responsive Design Completo**: Sistema responsive con **ResponsiveService**, directivas custom y tabla híbrida que alterna entre vista de tabla (desktop) y cards (móvil). 5 breakpoints configurados con **Angular CDK BreakpointObserver**
-  **Backend Health Monitoring**: Indicador visual del estado del servidor en tiempo real

---

##  Stack Tecnológico

### Backend
- **Framework**: NestJS 11 (Node.js con TypeScript)
- **API**: REST + GraphQL (Apollo Server)
- **Base de Datos**: TypeORM + SQLite/PostgreSQL
- **Validación**: Class Validator + DTOs
- **Documentación**: Swagger/OpenAPI automático
- **Deploy**: Render (tier gratuito)

### Frontend
- **Framework**: Angular 20 con Standalone Components
- **UI**: TailwindCSS 4.1 + DaisyUI + Custom Components
- **Estado**: Signals (API de reactividad de Angular)
- **Formularios**: Reactive Forms con validación avanzada
- **Deploy**: Vercel con auto-deploy desde GitHub
- **Desktop**: Electron 38.4 (aplicación de escritorio disponible)

### Features Técnicos
-  **CORS configurado** para Vercel + subdominios
-  **Lazy Loading Completo** - 38+ chunks lazy cargados bajo demanda
-  **Bundle Optimizado** - 1.72 MB inicial (↓35% vs versión anterior)
-  **Code Splitting Automático** - Dashboard (270 KB), Settings (110 KB) lazy
-  **Sistema de Iconos SVG** - 140+ iconos Material Design optimizados con sprites.svg
-  **Health Check** automático cada 30s con indicador visual
-  **Modular Architecture** con separación de responsabilidades
-  **DTO Validation** en todas las peticiones
-  **Environment Management** (dev/prod)
-  **Sistema Responsive Completo** con ResponsiveService + Angular CDK BreakpointObserver
-  **Directivas Custom Responsive**: `*appResponsive`, `[appResponsiveClass]`, `appResponsiveGrid`
-  **Tabla Híbrida**: Alterna automáticamente entre tabla (desktop) y cards (móvil)
-  **Dashboard v2.4**: Alertas inteligentes, Quick Actions FAB, Timeline de actividad
-  **KPIs Interactivos**: Métricas clicables con navegación a vistas detalladas
-  **Iconos de Tendencia**: Ascendente (verde), Descendente (rojo), Estable (azul)
-  **Performance Optimizada**: Transfer size 411 KB (reducción del 75%)
-  **Badges con Iconos**: Tratamientos, consentimientos, estados con iconos visuales
-  **Acciones Consistentes**: Iconos uniformes en todos los botones CRUD
-  **77 Tests Unitarios**: 100% cobertura CRUD en backend

---

##  Demo en Vivo

###  Aplicación Web
**URL**: [https://mediq-one.vercel.app](https://mediq-one.vercel.app)

**Modo Demo**: Navegación libre sin autenticación. Datos de prueba pre-cargados mediante seeding.

**Características destacadas para probar**:
-  **Dashboard v2.4** con alertas inteligentes y métricas interactivas
-  **Quick Actions FAB** (botón flotante) para crear rápidamente
-  **Timeline de Actividad Reciente** con últimas acciones
-  **Filtro de Periodo** (hoy, semana, mes, trimestre, año, personalizado)
-  **KPIs Clicables** - Click en métricas para navegar a vistas filtradas
-  **Objetivos Visibles** - Badges de meta en consentimientos (90%)
-  **Pendiente de Cobro Destacado** - Visualización prioritaria
-  **Sistema de Iconos Completo** - 140+ iconos SVG Material Design en badges, acciones y filtros
-  **Badges Visuales** - Iconos en tratamientos, consentimientos, estados de sesión
-  **Botones de Acción** - Iconos consistentes en todas las acciones CRUD
-  Búsqueda y filtros avanzados de pacientes
-  Creación y edición de tratamientos
-  Sistema de consentimientos con auditoría
-  Configuración multi-especialidad
-  Indicador de estado del backend (arriba a la derecha)
-  **70+ Iconos Material Design** integrados

###  API REST + Swagger
**Base URL**: `https://mediq-backend-ba4f.onrender.com/api`

**Documentación Interactiva**: [https://mediq-backend-ba4f.onrender.com/api/docs](https://mediq-backend-ba4f.onrender.com/api/docs)

Endpoints principales:
- `GET /api/patients` - Listar pacientes
- `GET /api/treatments` - Listar tratamientos
- `GET /api/consents` - Listar consentimientos
- `GET /api/dashboard/metrics` - Métricas del dashboard
- `GET /api/health` - Health check del servidor

 **Nota**: Backend en tier gratuito de Render - primera carga puede tardar ~50 segundos en despertar

###  GraphQL Playground
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

##  Screenshots

### Dashboard Principal
![Dashboard](./screenshots/dashboard.jpeg)
*Dashboard v2.4 con alertas inteligentes, Quick Actions FAB, timeline de actividad y métricas interactivas en tiempo real*

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

##  Habilidades Técnicas Demostradas

-  **Full-Stack Development**: Integración completa backend NestJS + frontend Angular
-  **TypeScript Avanzado**: Decoradores, Generics, Type Guards, DTOs tipados
-  **APIs Modernas**: REST + GraphQL en un mismo proyecto con documentación automática
-  **Database Design**: Relaciones complejas (One-to-Many, Many-to-One) con TypeORM
-  **Validación Robusta**: Class Validator (backend) + Reactive Forms (frontend)
-  **Arquitectura Modular**: Separación de responsabilidades, Repository Pattern
-  **UI/UX Moderno**: TailwindCSS, componentes reutilizables, diseño responsive
-  **State Management**: Angular Signals para reactividad eficiente
-  **Responsive Design Avanzado**: ResponsiveService con Angular CDK, directivas custom, tabla híbrida
-  **Dashboard Moderno v2.4**: Alertas inteligentes, FAB, timeline, filtros de periodo
-  **Sistema de Iconos SVG**: 140+ iconos Material Design optimizados
-  **Performance Optimization**: Bundle inicial 1.72 MB (↓35%), 38+ lazy chunks, code splitting
-  **DevOps**: Deploy automatizado en Vercel + Render, CORS, environment management
-  **Clean Code**: SOLID principles, código documentado, commits semánticos
-  **Error Handling**: Manejo de errores, validaciones, mensajes de usuario
-  **Lazy Loading Avanzado**: Todos los módulos principales cargados bajo demanda

---

##  Contacto y Enlaces

**Desarrollador**: Adrián Dávila Guerra

**Email**: adrian.davilaguerra@gmail.com

**LinkedIn**: [linkedin.com/in/adravilag](https://www.linkedin.com/in/adri%C3%A1n-d%C3%A1vila-guerra-97a15496/)

**GitHub**: [github.com/Adravilag](https://github.com/Adravilag)

---

##  Licencia

Este proyecto es una demostración técnica **open-source** para propósitos educativos y de portfolio.

MIT License - Ver repositorios individuales para más detalles.

---

## 🗺️ Roadmap

Para conocer las próximas mejoras planificadas, consulta nuestro [ROADMAP completo](./ROADMAP.md).

### Próximas Mejoras Planificadas

#### 🔥 Prioridad Alta
- **Tour Interactivo con Driver.js** - Onboarding guiado para nuevos usuarios ([Ver implementación](./DRIVER-JS-IMPLEMENTATION.md))
- **Sistema de Notificaciones en Tiempo Real** - WebSockets para sincronización multi-usuario
- **Creación de Facturas desde Sesiones** - Flujo optimizado con preview
- **Gestión de Tipos de Consentimiento** - CRUD completo con plantillas HTML

#### ⚡ Completado Recientemente
- ✅ **Refactorización Treatment-Form** - 6 componentes modulares, -70.8% HTML, 0 errores compilación (13 Nov 2025)
- ✅ **TypeScript Strict Mode Backend** - Type safety completo con FindOptionsWhere, type guards y null handling (13 Nov 2025)
- ✅ **Handlers Genéricos de Entidades** - Sistema reutilizable DRY para CRUD/Navegación/Filtros (Nov 2025)
- ✅ **Pipes Compartidos** - 10 pipes reutilizables con documentación completa (Nov 2025)
- ✅ **Treatment-List Handlers v2.0** - Arquitectura modular consistente con otros listados (Nov 2025)

---

##  Nota de Demo

**Características de la Demo en Producción**:
-  Backend desplegado en **Render** (tier gratuito)
-  Frontend desplegado en **Vercel** con auto-deploy desde GitHub
-  **Bundle optimizado**: 1.72 MB inicial, 411 KB transferidos (↓75%)
-  **38+ chunks lazy**: Code splitting automático por rutas
-  **Health monitoring** automático con indicador visual
-  Menú deshabilitado cuando backend está offline (UX mejorada)
-  Datos de prueba pre-cargados mediante seeding
-  Documentación Swagger completamente funcional
-  **77 Tests Unitarios** pasando al 100% (backend)
-  **Versión Desktop (Electron)**: Aplicación de escritorio disponible
-  **Sistema Responsive Completo**: Tabla híbrida + directivas custom
-  **Dashboard v2.4**: Alertas, FAB, timeline, KPIs interactivos
-  **Performance optimizada**: Lighthouse Score 85+, Time to Interactive <3s

**Limitaciones del Tier Gratuito**:
-  Backend puede tardar ~50 segundos en despertar tras inactividad
-  Base de datos SQLite en memoria (datos se resetean periódicamente)
-  Sin persistencia permanente de cambios

**Para Evaluadores/Reclutadores**: El código fuente completo está disponible públicamente en los repositorios de GitHub enlazados arriba. No dudes en contactar para cualquier consulta técnica.

---

---

##  Sistema de Pagos Online

MediQ integra **pagos online con Bizum y tarjeta** mediante Redsys TPV Virtual.

### Características de Pagos en la Demo
-  **Facturación Automática**: Crea facturas desde sesiones con un click
-  **Múltiples Métodos**: Efectivo (inmediato), Bizum (online), Transferencia, Tarjeta
-  **Pago con Bizum**: Botón integrado en formularios de factura
-  **Confirmación Automática**: Webhook actualiza estado sin intervención manual
-  **Estados Inteligentes**: 
  -  Efectivo → `paid` (inmediato)
  -  Bizum → `processing` → `paid` (webhook)
  -  Transferencia → `pending` → `paid` (manual)
-  **Polling en Tiempo Real**: UI se actualiza automáticamente al confirmar pago

### Flujo de Pago en la Demo

```
1. Crear Sesión
   └─→ Seleccionar " Bizum (pago online)"
   └─→ Marcar " Crear factura automáticamente"
   
2. Guardar Sesión
   └─→ Factura generada con status: 'processing'
   └─→ Redirige a formulario de factura
   
3. Pagar con Bizum
   └─→ Click en botón " Pagar con Bizum"
   └─→ Se abre ventana de Redsys
   └─→ Usuario paga desde app bancaria
   
4. Confirmación Automática
   └─→ Webhook actualiza factura: status='paid'
   └─→ UI detecta cambio (polling cada 3s)
   └─→ Muestra " Pago confirmado exitosamente"
```

### Endpoints de API

```http
# Iniciar pago (genera firma y parámetros)
POST https://mediq-backend-ba4f.onrender.com/api/payments/initiate
Body: { invoiceId, amount, description }

# Consultar estado de pago (para polling)
GET https://mediq-backend-ba4f.onrender.com/api/payments/status/:invoiceId

# Webhook de confirmación (llamado por Redsys)
POST https://mediq-backend-ba4f.onrender.com/api/payments/webhook/redsys
```

### Probarlo en la Demo

 **Nota**: El sistema de pagos está completamente implementado en el código, pero la demo pública usa credenciales de sandbox de Redsys. Para pruebas reales:

1. Accede a [https://mediq-one.vercel.app](https://mediq-one.vercel.app)
2. Crea un paciente con email válido
3. Crea un tratamiento para ese paciente
4. Crea una sesión y selecciona "Bizum"
5. Marca "Crear factura automáticamente"
6. Guarda y sigue el flujo de pago

**Modo de prueba**: Usa tarjetas de prueba de Redsys o el simulador de Bizum para testing.

** Documentación Técnica**:
- [Sistema de Pagos Completo](../MediQ-Backend/docs/PAYMENT-SYSTEM.md)
- [Guía Rápida de Integración](../MediQ-Backend/PAYMENT-QUICKSTART.md)
- [Implementación Frontend](../FACTURACION-BIZUM-IMPLEMENTADO.md)

---

##  Mejoras Visuales Recientes

### Dashboard v2.4
- **Alertas Inteligentes**: Sistema de notificaciones contextuales
- **Quick Actions FAB**: Botón flotante con 4 acciones rápidas
- **Timeline de Actividad**: Últimas 5 acciones del sistema
- **Filtro de Periodo**: 6 opciones temporales
- **KPIs Interactivos**: Click para navegar a vistas filtradas
- **140+ Iconos Material Design**: sprites.svg optimizado con sistema completo

### Sistema de Iconos SVG
- **SvgIconComponent**: Componente reutilizable standalone
- **140+ iconos Material Design**: Diseño consistente y profesional
- **Badges Visuales**: Iconos en tratamientos, consentimientos, estados
- **Botones de Acción**: Iconos en CRUD (view, edit, archive, delete, restore)
- **Filtros Mejorados**: Iconos SVG en lugar de emojis
- **Demo Interactivo**: `/svg-demo` con catálogo completo

### Sistema Responsive Completo
- **ResponsiveService** con Angular CDK BreakpointObserver
- **5 Breakpoints**: XSmall, Small, Medium, Large, XLarge
- **Directivas Custom**: `*appResponsive`, `[appResponsiveClass]`, `appResponsiveGrid`
- **Tabla Híbrida**: Alterna entre tabla (desktop) y cards (móvil)

### Facturación Mejorada
- **UI con Emojis**: Métodos de pago visuales y claros
- **Lógica Condicional**: Checkbox inteligente según método
- **Mensajes Contextuales**: Información en tiempo real
- **Estados Visuales**: Badges de color según estado de pago

---

## 📝 Changelog Reciente

### Última Actualización (13 Noviembre 2025)

**🏗️ Frontend - Arquitectura y Refactorización**
- **Treatment-Form Refactorizado**: Arquitectura modular con 6 section components
  - ✅ Reducción de HTML: 332 → 97 líneas (-70.8%)
  - ✅ Similitud arquitectónica: 75% → 95% (+20 puntos)
  - ✅ Componentes creados: header, alerts, basic-info, medical-history, factors, consent-checkbox
  - ✅ Type safety completo con wrappers para null-safety
  - ✅ Build exitoso: 0 errores de compilación
  - 📄 [Documentación completa](../docs/TREATMENT-FORM-REFACTORING-COMPLETE.md)

- **Treatment-List Handlers v2.0**: Migración a arquitectura modular consistente
  - ✅ 10 archivos de handlers (data, column-config, action-config, filter-config, etc.)
  - ✅ Computed signals para filtrado, ordenamiento y paginación
  - ✅ Context menu handlers con validaciones de estado
  - ✅ Inicialización con query params desde URL
  - ✅ README completo con 330+ líneas de documentación

**📦 Handlers Genéricos Reutilizables**
- **EntityCRUDHandlers**: CRUD operations para cualquier entidad
- **EntityNavigationHandlers**: Navegación consistente (view/edit/new/archived)
- **EntityPaginationHandlers**: Paginación con cálculo de totalPages
- **EntityFilterHandlers**: Filtros dinámicos con reset y load saved
- **EntityExportHandlers**: Exportación JSON/CSV con mappers personalizados
- **EntityActionHandlers**: Orquestador de acciones (view/edit/archive/delete)
- **EntityComputedHandlers**: Utilidades para filtrado, sort y paginación
- 📄 [Documentación de handlers genéricos](../MediQ-Frontend/src/app/shared/handlers/README.md)

**🎨 Pipes Compartidos**
- ✅ 10 pipes reutilizables documentados:
  - `CurrencyEsPipe`: Formato de moneda española (1.234,56 €)
  - `StatusBadgePipe`: Configuración de badges para todos los estados
  - `SafeHtmlPipe`: Sanitización de HTML segura
  - `HighlightPipe`: Resaltado de términos de búsqueda
  - `FileSizePipe`: Conversión de bytes a formato legible
  - `InitialsPipe`: Extracción de iniciales para avatares
  - `DurationPipe`: Formato de duración (1h 30min)
  - `PluralPipe`: Pluralización automática en español
  - `TimeAgoPipe`: Tiempo relativo (Hace 2 horas)
  - `TruncatePipe`: Truncado de texto con ellipsis
- 📄 [Guía completa de pipes](../MediQ-Frontend/src/app/shared/pipes/README.md)

**🔧 Backend - Mejoras de Code Quality**
- ✅ TypeScript strict mode compliance
  - Uso de `FindOptionsWhere<T>` en lugar de `any`
  - Type guards con `error instanceof Error`
  - Proper null handling con optional chaining
  - Type-safe enum comparisons
- ✅ ESLint fixes: 0 warnings en patient.service.ts y consent.service.ts
- ✅ Interfaces para respuestas enriquecidas (EnrichedConsent con patient data)
- ✅ Métodos privados con type-safe implementations

### 30 Octubre 2025

**⚡ Optimización de Bundle y Performance**
- Lazy Loading Completo en todas las rutas principales
- Reducción de bundle inicial: 2.65 MB → 1.72 MB (**↓35%**)
- 38+ chunks lazy generados por code splitting automático
- Transfer size optimizado: 411 KB comprimido (↓75%)
- Presupuestos de bundle configurados y cumplidos

**🎨 Sistema de Iconos SVG Mejorado**
- Expansión de 70+ a **140+ iconos Material Design**
- Sistema completo con `SvgIconComponent` reutilizable
- Iconos en badges, botones de acción y filtros
- Demo interactivo en `/svg-demo`

**🗂️ Gestión de Archivados**
- Nuevos componentes para pacientes, tratamientos, sesiones y consentimientos archivados
- Restauración masiva y eliminación permanente
- Trazabilidad completa de documentos archivados

**✨ Mejoras de Experiencia**
- Pre-validación de pacientes duplicados
- Datos de prueba para formularios de tratamientos
- Carga dinámica de tipos de tratamiento
- Workflow mejorado tras firmar consentimientos

**🔧 Mejoras Técnicas**
- Refactorización de componentes del dashboard
- Actualización de modelos con compatibilidad retroactiva
- Limpieza de código y formateo consistente
- Notificaciones uniformes en toda la aplicación

### v2.5.0 (Octubre 2025)
- Dashboard v2.4 con alertas inteligentes
- Sistema responsive completo
- Integración de pagos Bizum/Redsys

---

**Última actualización**: 13 Noviembre 2025  
**Mejoras principales**: Treatment-Form Refactorizado + TypeScript Strict Mode Backend + 140+ Iconos SVG �️✨ 

