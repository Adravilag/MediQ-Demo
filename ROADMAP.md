# 🗺️ MediQ - Roadmap de Desarrollo

> **Última actualización**: 30 de Octubre de 2025  
> **Estado del proyecto**: v2.6.0 - En desarrollo activo

---

## 📋 Tabla de Contenidos

- [🔥 Prioridad Alta](#-prioridad-alta)
- [⚡ Prioridad Media](#-prioridad-media)
- [💡 Prioridad Baja / Futuro](#-prioridad-baja--futuro)
- [✅ Completado Recientemente](#-completado-recientemente)
- [📊 Estado General](#-estado-general)

---

## 🔥 Prioridad Alta

### 🔔 Sistema de Notificaciones en Tiempo Real
**Estado**: 🔴 Pendiente  
**Complejidad**: Alta  
**Estimación**: 2-3 semanas

**Problemas a corregir**:
- ❌ Contadores de pacientes no se actualizan automáticamente
- ❌ Contadores de tratamientos desincronizados
- ❌ Contadores de sesiones sin actualización en tiempo real
- ❌ Contadores de consentimientos incorrectos
- ❌ No se reflejan elementos vinculados (paciente → tratamientos → sesiones)
- ❌ Archivado en cascada no actualiza contadores
- ❌ Restauración no actualiza dashboard

**Implementación planificada**:
- [ ] Implementar **WebSockets** (Socket.io) para notificaciones en tiempo real
- [ ] Crear servicio `NotificationHub` centralizado
- [ ] Eventos del backend:
  - `patient:created`, `patient:updated`, `patient:archived`, `patient:restored`
  - `treatment:created`, `treatment:updated`, `treatment:archived`, `treatment:restored`
  - `session:created`, `session:updated`, `session:archived`, `session:restored`
  - `consent:created`, `consent:updated`, `consent:archived`, `consent:restored`
  - `invoice:created`, `invoice:paid`, `invoice:cancelled`
- [ ] Actualización automática de contadores en dashboard
- [ ] Sincronización de listas activas al recibir eventos
- [ ] Sistema de caché con invalidación inteligente
- [ ] Notificaciones toast para cambios importantes
- [ ] Indicador visual de "Actualizando..." durante sincronización

**Beneficios**:
- ✅ Dashboard siempre actualizado sin recargar
- ✅ Múltiples usuarios ven cambios en tiempo real
- ✅ Mejor experiencia de usuario (UX)
- ✅ Reducción de llamadas API innecesarias

---

### 🔍 Corrección de Filtros de Búsqueda
**Estado**: 🟠 En progreso  
**Complejidad**: Media  
**Estimación**: 1 semana

**Problemas identificados**:
- ❌ Filtro por fecha no funciona correctamente en tratamientos
- ❌ Búsqueda por DNI no encuentra resultados parciales
- ❌ Filtros combinados (ciudad + estado) no se aplican bien
- ❌ Rango de fechas en sesiones arroja resultados incorrectos
- ❌ Búsqueda en consentimientos por tipo no filtra correctamente
- ❌ Filtros no se persisten al navegar entre páginas
- ❌ Reset de filtros no limpia todos los campos

**Mejoras planificadas**:
- [ ] Refactorizar servicio de filtros con RxJS operators
- [ ] Implementar debouncing (500ms) en campos de texto
- [ ] Validación de rangos de fechas (inicio < fin)
- [ ] Búsqueda parcial mejorada (LIKE con wildcards)
- [ ] Persistencia de filtros en localStorage
- [ ] Query params en URL para compartir filtros
- [ ] Indicadores visuales de filtros activos (chips)
- [ ] Botón "Limpiar todo" con confirmación
- [ ] Tests unitarios para cada tipo de filtro

**Casos de uso cubiertos**:
- ✅ Búsqueda de pacientes por nombre parcial
- ✅ Filtrado de tratamientos por rango de fechas
- ✅ Combinación de múltiples filtros (AND logic)
- ✅ Búsqueda avanzada con operadores (=, >, <, BETWEEN)

---

### 💳 Creación de Facturas desde Sesiones
**Estado**: 🟡 Parcialmente implementado  
**Complejidad**: Media  
**Estimación**: 1 semana

**Funcionalidad actual**:
- ✅ Checkbox "Crear factura automáticamente" en formulario de sesión
- ✅ Generación básica de factura al guardar sesión
- ⚠️ Falta validación de datos obligatorios
- ⚠️ No permite edición de factura antes de crear
- ⚠️ Duplicación de facturas en algunos casos

**Mejoras planificadas**:
- [ ] **Flujo mejorado en 2 pasos**:
  1. Sesión guardada → Mostrar preview de factura
  2. Usuario revisa/edita → Confirma creación
- [ ] Validación de campos obligatorios (paciente, monto, método pago)
- [ ] Prevención de facturas duplicadas (chequeo en backend)
- [ ] Plantillas de factura configurables por clínica
- [ ] Numeración automática correlativa de facturas
- [ ] Generación de PDF de factura con logo de clínica
- [ ] Envío automático por email (opcional)
- [ ] Registro de auditoría (quién creó, cuándo, desde dónde)
- [ ] Descuentos y recargos aplicables
- [ ] Multi-sesión: crear 1 factura para varias sesiones

**Casos de uso**:
- ✅ Sesión → Factura automática (efectivo)
- ✅ Sesión → Factura pendiente (Bizum/transferencia)
- 🔜 Múltiples sesiones → 1 factura mensual
- 🔜 Sesión → Factura con descuento del 10%
- 🔜 Sesión → Factura con IVA configurable

---

## ⚡ Prioridad Media

### 📄 Gestión de Tipos de Consentimiento
**Estado**: 🔴 Pendiente  
**Complejidad**: Media  
**Estimación**: 1 semana

**Descripción**:
Actualmente los tipos de consentimiento están hardcodeados. Se necesita un CRUD completo para gestionarlos dinámicamente.

**Funcionalidades planificadas**:
- [ ] Módulo `ConsentTypes` con CRUD completo
- [ ] Campos del modelo:
  - `id`, `name`, `description`, `category` (tratamiento, intervención, fotografía, datos)
  - `template` (HTML con placeholders: `{{patientName}}`, `{{date}}`)
  - `requiredFields` (array de campos obligatorios)
  - `expirationMonths` (meses de validez, null = permanente)
  - `requiresSignature` (boolean)
  - `requiresWitness` (boolean)
  - `active` (boolean)
  - `clinicType` (estética, fisioterapia, odontología, general)
- [ ] Interfaz de gestión:
  - Lista de tipos con filtro por categoría
  - Formulario de creación/edición
  - Editor de plantilla con preview en tiempo real
  - Drag & drop para reordenar
  - Activar/desactivar tipos sin eliminar
- [ ] Validaciones:
  - Nombre único por clínica
  - Template debe contener placeholders válidos
  - ExpirationMonths debe ser positivo
- [ ] Permisos:
  - Solo administradores pueden crear/editar tipos
  - Usuarios normales solo leen tipos activos

**Plantillas predefinidas incluidas**:
- ✅ Consentimiento informado general
- ✅ Consentimiento fotografía clínica
- ✅ Consentimiento tratamiento láser
- ✅ Consentimiento infiltraciones
- ✅ Consentimiento protección de datos (RGPD)

---

### 📝 Sistema de Plantillas Personalizables
**Estado**: 🔴 Pendiente  
**Complejidad**: Alta  
**Estimación**: 2 semanas

**Descripción**:
Sistema flexible para crear y gestionar plantillas de documentos (informes, consentimientos, recetas, certificados).

**Funcionalidades planificadas**:
- [ ] Módulo `Templates` con CRUD completo
- [ ] Campos del modelo:
  - `id`, `name`, `type` (consent, report, prescription, certificate)
  - `htmlContent` (HTML con Handlebars)
  - `cssStyles` (CSS custom para la plantilla)
  - `variables` (array de variables disponibles)
  - `category`, `version`, `active`
- [ ] **Editor WYSIWYG avanzado**:
  - Editor visual tipo Notion/Google Docs
  - Inserción de placeholders con autocompletado
  - Vista previa en tiempo real
  - Estilos de texto (negrita, cursiva, listas)
  - Inserción de imágenes/logos
  - Tablas y columnas
  - Firma digital
  - Código QR
- [ ] **Variables dinámicas disponibles**:
  - Paciente: `{{patient.fullName}}`, `{{patient.dni}}`, `{{patient.birthDate}}`
  - Tratamiento: `{{treatment.name}}`, `{{treatment.type}}`
  - Sesión: `{{session.date}}`, `{{session.duration}}`
  - Clínica: `{{clinic.name}}`, `{{clinic.address}}`, `{{clinic.phone}}`
  - Profesional: `{{doctor.name}}`, `{{doctor.license}}`
  - Fecha actual: `{{currentDate}}`, `{{currentTime}}`
- [ ] **Versionado de plantillas**:
  - Historial de cambios
  - Rollback a versiones anteriores
  - Comparación visual de versiones
- [ ] **Generación de documentos**:
  - Vista previa antes de generar
  - Exportación a PDF
  - Firma digital integrada
  - Envío por email automático
  - Almacenamiento en historial del paciente

**Tipos de plantillas**:
- 📄 Consentimientos informados
- 📋 Informes médicos
- 💊 Recetas y prescripciones
- 📜 Certificados médicos
- 📊 Reportes de evolución
- 🧾 Presupuestos

---

### 💾 Sistema de Backup y Restauración
**Estado**: 🔴 Pendiente  
**Complejidad**: Alta  
**Estimación**: 2 semanas

**Descripción**:
Sistema automatizado de respaldo de datos con restauración punto-en-tiempo.

**Funcionalidades planificadas**:

#### Backend (Exportación)
- [ ] Endpoint `/api/backup/full` - Backup completo de BD
- [ ] Endpoint `/api/backup/incremental` - Backup incremental (cambios desde último)
- [ ] Formatos de exportación:
  - JSON (datos raw)
  - SQL dump (compatible con PostgreSQL/MySQL)
  - CSV por tabla (para análisis)
  - Excel (.xlsx) con múltiples hojas
- [ ] **Backups automáticos programados**:
  - Diario (3 AM) - Incremental
  - Semanal (Domingo 3 AM) - Completo
  - Mensual (Día 1 a las 3 AM) - Completo
- [ ] Encriptación AES-256 de backups
- [ ] Compresión gzip para reducir tamaño
- [ ] Almacenamiento en:
  - Sistema de archivos local
  - AWS S3 / Google Cloud Storage
  - Azure Blob Storage
  - Dropbox / Google Drive (opcional)
- [ ] Retención configurable:
  - Diarios: 7 días
  - Semanales: 4 semanas
  - Mensuales: 12 meses
  - Anuales: 5 años
- [ ] Limpieza automática de backups antiguos

#### Frontend (Interfaz)
- [ ] Panel de administración de backups:
  - Lista de backups disponibles (fecha, tamaño, tipo)
  - Estado de último backup (exitoso/fallido)
  - Botón "Crear backup ahora"
  - Calendario de programación
- [ ] **Restauración controlada**:
  - Selección de backup por fecha
  - Vista previa de datos a restaurar
  - Opciones de restauración:
    - Completa (sobreescribe todo)
    - Parcial (solo tablas seleccionadas)
    - Merge (combina con datos existentes)
  - Confirmación con contraseña de administrador
  - Creación de backup pre-restauración automático
- [ ] **Monitoreo**:
  - Notificaciones de backup exitoso/fallido
  - Dashboard con métricas:
    - Espacio usado por backups
    - Fecha del último backup
    - Historial de restauraciones
  - Alertas si no hay backup en 48h
- [ ] **Descargar backup**:
  - Descarga manual de backup en local
  - Subida de backup externo para restaurar

#### Seguridad y Auditoría
- [ ] Log detallado de operaciones:
  - Quién creó el backup
  - Quién restauró datos
  - Timestamp de cada operación
  - IP de origen
- [ ] Permisos granulares:
  - Solo administradores pueden crear/restaurar
  - Confirmación de 2 usuarios para restauración
- [ ] Verificación de integridad (checksums)
- [ ] Tests de restauración automáticos mensualmente

**Casos de uso**:
- ✅ Recuperación ante fallo de servidor
- ✅ Migración a nuevo servidor
- ✅ Auditoría de datos históricos
- ✅ Cumplimiento normativo (RGPD - conservación de datos)
- ✅ Rollback tras error humano

---

## 💡 Prioridad Baja / Futuro

### 🔐 Sistema de Autenticación y Autorización
**Estado**: 🔴 Pendiente  
**Complejidad**: Alta  
**Estimación**: 3 semanas

- [ ] Implementar JWT con refresh tokens
- [ ] Sistema de roles y permisos granulares:
  - Administrador (acceso total)
  - Médico (gestión de pacientes y tratamientos)
  - Recepcionista (solo lectura + citas)
  - Facturación (solo facturación y cobros)
- [ ] Login con 2FA (autenticación de dos factores)
- [ ] SSO con Google/Microsoft (opcional)
- [ ] Logs de auditoría de accesos
- [ ] Sesiones concurrentes limitadas
- [ ] Bloqueo de cuenta tras intentos fallidos
- [ ] Política de contraseñas robustas

---

### 📅 Sistema de Citas y Calendario
**Estado**: 🔴 Pendiente  
**Complejidad**: Alta  
**Estimación**: 3-4 semanas

- [ ] Calendario visual con vista semanal/mensual
- [ ] Creación de citas con duración configurable
- [ ] Asignación de citas a profesionales
- [ ] Recordatorios automáticos por email/SMS
- [ ] Gestión de disponibilidad de médicos
- [ ] Lista de espera automatizada
- [ ] Confirmación de citas por paciente
- [ ] Integración con Google Calendar
- [ ] Notificaciones push 24h antes de cita
- [ ] Estadísticas de asistencia/ausencias

---

### 💬 Sistema de Mensajería Interna
**Estado**: 🔴 Pendiente  
**Complejidad**: Media  
**Estimación**: 2 semanas

- [ ] Chat entre profesionales
- [ ] Notificaciones de mensajes no leídos
- [ ] Archivos adjuntos en mensajes
- [ ] Mensajes grupales por departamento
- [ ] Historial de conversaciones
- [ ] Búsqueda en mensajes
- [ ] Estado "Leyendo..." en tiempo real
- [ ] Mensajes destacados/importantes

---

### 📊 Reportes y Analíticas Avanzadas
**Estado**: 🟡 Básico implementado  
**Complejidad**: Media  
**Estimación**: 2 semanas

**Actual**:
- ✅ Dashboard con métricas básicas
- ✅ Contadores de pacientes, tratamientos, sesiones

**Mejoras planificadas**:
- [ ] Reportes personalizables con filtros avanzados
- [ ] Gráficos interactivos (Chart.js → D3.js)
- [ ] Exportación de reportes a PDF/Excel
- [ ] Comparativas mes a mes / año a año
- [ ] Análisis de rentabilidad por tratamiento
- [ ] Predicciones con Machine Learning (IA)
- [ ] Heatmaps de actividad
- [ ] Embudo de conversión (consulta → tratamiento)
- [ ] KPIs configurables por usuario
- [ ] Reportes programados por email

---

### 🌍 Internacionalización (i18n)
**Estado**: 🔴 Pendiente  
**Complejidad**: Media  
**Estimación**: 1-2 semanas

- [ ] Soporte multi-idioma (español, inglés, francés)
- [ ] Traducción de interfaz con Angular i18n
- [ ] Formatos de fecha/moneda localizados
- [ ] Selector de idioma en configuración
- [ ] Documentos/plantillas multi-idioma
- [ ] Detección automática de idioma del navegador

---

### 📱 Aplicación Móvil Nativa
**Estado**: 🔴 Pendiente  
**Complejidad**: Muy Alta  
**Estimación**: 3-6 meses

- [ ] Desarrollo con React Native / Flutter
- [ ] Versión para iOS y Android
- [ ] Funcionalidades offline (sync posterior)
- [ ] Notificaciones push nativas
- [ ] Cámara para captura de documentos
- [ ] Firma digital táctil
- [ ] Geolocalización para servicios a domicilio
- [ ] Integración con biometría (Face ID, huella)

---

### 🤖 Asistente con Inteligencia Artificial
**Estado**: 🔴 Pendiente  
**Complejidad**: Muy Alta  
**Estimación**: 4-6 meses

- [ ] Chatbot para consultas frecuentes
- [ ] Sugerencias de diagnóstico (asistente, no reemplazo)
- [ ] Autocompletado inteligente en formularios
- [ ] Detección de anomalías en datos
- [ ] Predicción de no-shows en citas
- [ ] Recomendaciones de tratamientos basadas en historial
- [ ] Análisis de sentimiento en notas clínicas
- [ ] Generación automática de resúmenes de sesiones

---

### 🔗 Integraciones con Sistemas Externos
**Estado**: 🔴 Pendiente  
**Complejidad**: Variable  
**Estimación**: Variable por integración

- [ ] **Sistemas de pago**:
  - ✅ Bizum/Redsys (implementado)
  - 🔜 PayPal, Stripe
  - 🔜 TPV físico
- [ ] **Email marketing**:
  - Mailchimp
  - SendGrid
- [ ] **SMS**:
  - Twilio
  - Vonage
- [ ] **Contabilidad**:
  - A3 Software
  - Sage
  - Contasimple
- [ ] **Laboratorios médicos**:
  - API para solicitud de análisis
  - Recepción automática de resultados
- [ ] **Farmacias**:
  - Envío de recetas electrónicas
- [ ] **Seguros médicos**:
  - Validación de pólizas
  - Facturación directa a aseguradoras

---

## ✅ Completado Recientemente

### v2.6.0 (30 Octubre 2025)

#### ⚡ Optimización de Bundle y Performance
- ✅ Lazy Loading Completo en todas las rutas
- ✅ Reducción de bundle inicial: 2.65 MB → 1.72 MB (↓35%)
- ✅ 38+ chunks lazy generados por code splitting
- ✅ Transfer size optimizado: 411 KB (↓75%)
- ✅ Presupuestos de bundle configurados (1.75 MB máx.)

#### 🎨 Sistema de Iconos SVG
- ✅ Expansión de 70+ a 140+ iconos Material Design
- ✅ SvgIconComponent reutilizable
- ✅ Integración en badges, botones y filtros
- ✅ Demo interactivo en `/svg-demo`

#### 🗂️ Componentes de Archivado
- ✅ ArchivedPatientsComponent
- ✅ ArchivedTreatmentsComponent
- ✅ ArchivedSessionsComponent
- ✅ ArchivedConsentsComponent
- ✅ Acciones masivas (restaurar/eliminar)

#### ✨ Mejoras de UX
- ✅ PatientPreValidationComponent (detección de duplicados)
- ✅ TreatmentTestDataService (datos de prueba)
- ✅ Carga dinámica de tipos de tratamiento
- ✅ Workflow mejorado tras firmar consentimientos

### v2.5.0 (Octubre 2025)
- ✅ Dashboard v2.4 con alertas inteligentes
- ✅ Quick Actions FAB
- ✅ Sistema responsive completo
- ✅ Integración de pagos Bizum/Redsys

---

## 📊 Estado General

### Progreso por Categoría

| Categoría | Completado | En Progreso | Pendiente | Total |
|-----------|------------|-------------|-----------|-------|
| **Performance** | 4 | 0 | 0 | 4 |
| **Sistema de Iconos** | 4 | 0 | 0 | 4 |
| **Archivado** | 4 | 0 | 0 | 4 |
| **UX/Validación** | 4 | 0 | 0 | 4 |
| **Notificaciones** | 0 | 0 | 1 | 1 |
| **Filtros** | 0 | 1 | 0 | 1 |
| **Facturación** | 2 | 1 | 3 | 6 |
| **Consentimientos** | 1 | 0 | 1 | 2 |
| **Plantillas** | 0 | 0 | 1 | 1 |
| **Backup** | 0 | 0 | 1 | 1 |
| **Autenticación** | 0 | 0 | 1 | 1 |
| **Citas** | 0 | 0 | 1 | 1 |
| **Reportes** | 1 | 0 | 1 | 2 |
| **Mobile** | 0 | 0 | 1 | 1 |
| **IA** | 0 | 0 | 1 | 1 |
| **Integraciones** | 1 | 0 | 5 | 6 |

### Velocidad de Desarrollo

- **Últimos 30 días**: 16 features completadas
- **Promedio mensual**: 8-10 features
- **Próximos 3 meses (estimado)**: 12-15 features

### Métricas de Código

- **Líneas de código**: ~45,000 (Frontend) + ~18,000 (Backend)
- **Componentes Angular**: 85+
- **Servicios**: 32
- **Tests unitarios**: 77 (Backend) + 0 (Frontend - pendiente)
- **Cobertura de tests**: 100% CRUD (Backend)

---

## 🤝 Contribución

¿Quieres contribuir al roadmap? 

1. Revisa las issues abiertas en GitHub
2. Comenta en la issue que te interesa
3. Fork el repositorio
4. Implementa la feature siguiendo las guías de estilo
5. Crea un Pull Request con descripción detallada

**Prioridades para contribuciones externas**:
- 🔥 Sistema de notificaciones en tiempo real
- 🔍 Corrección de filtros de búsqueda
- 💾 Sistema de backup

---

## 📞 Contacto

**Desarrollador**: Adrián Dávila Guerra  
**Email**: adrian.davilaguerra@gmail.com  
**GitHub**: [github.com/Adravilag](https://github.com/Adravilag)  
**LinkedIn**: [linkedin.com/in/adravilag](https://www.linkedin.com/in/adrián-dávila-guerra-97a15496/)

---

## 📝 Notas

- Este roadmap es dinámico y se actualiza regularmente
- Las estimaciones son aproximadas y pueden variar
- Las prioridades pueden cambiar según feedback de usuarios
- Features pueden moverse entre categorías según necesidades del proyecto

---

**Última revisión**: 30 de Octubre de 2025  
**Próxima revisión**: 15 de Noviembre de 2025
