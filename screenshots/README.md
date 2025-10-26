# 📸 Screenshots Guide

## Qué Capturar

### 1. Dashboard (dashboard.png)
**Prioridad: ALTA**
- Vista general con métricas visibles
- Gráficos poblados con datos
- Navbar visible
- Asegúrate de que se vean números realistas

**Resolución recomendada**: 1920x1080

---

### 2. Lista de Pacientes (patients.png)
**Prioridad: ALTA**
- Tabla con al menos 5-6 pacientes visibles
- Barra de búsqueda visible
- Botones de acción visibles
- Estado de carga correcto

**Tip**: Ejecuta seed antes de capturar

---

### 3. Formulario de Paciente (patient-form.png)
**Prioridad: MEDIA**
- Formulario completo visible
- Varios campos rellenados
- Secciones expandidas (dirección, historial médico)
- Validaciones funcionando

---

### 4. Detalle de Tratamiento (treatment-detail.png)
**Prioridad: ALTA**
- Información del tratamiento
- Lista de evoluciones/sesiones
- Estadísticas visibles
- Timeline de progreso

---

### 5. GraphQL Playground (graphql-playground.png)
**Prioridad: MEDIA**
- Query de ejemplo ejecutada
- Schema documentation visible (panel derecho)
- Respuesta JSON formateada
- URL visible en la barra

**Ejemplo de query para capturar**:
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

### 6. Swagger Documentation (swagger-ui.png)
**Prioridad: BAJA**
- Vista de endpoints expandidos
- Modelo de datos visible
- Try it out ejecutado (opcional)

---

### 7. Mobile View (mobile-dashboard.png)
**Prioridad: BAJA**
- Vista responsive en móvil (375px)
- Menú hamburguesa visible
- Contenido adaptado correctamente

---

## 🛠️ Herramientas Recomendadas

### Captura
- **Windows**: Win + Shift + S (Snipping Tool)
- **Browser DevTools**: F12 → Device Toolbar (Ctrl+Shift+M)
- **Full Page**: Extensión "Full Page Screen Capture"

### Edición
- **Básica**: Paint / Paint.NET (Windows)
- **Profesional**: Photoshop / GIMP
- **Anotaciones**: Greenshot / Snagit

### Optimización
- **TinyPNG**: https://tinypng.com (reduce tamaño sin perder calidad)
- **Squoosh**: https://squoosh.app

---

## ✨ Tips para Screenshots Profesionales

1. **Limpia la pantalla**: Cierra tabs innecesarias, oculta bookmarks
2. **Datos realistas**: Usa nombres/emails que suenen reales, no "Test 1", "Test 2"
3. **Resolución**: Mínimo 1920x1080, guarda en PNG
4. **Consistencia**: Todas las screenshots con el mismo tema/estilo
5. **Zoom**: 100% (evita texto borroso)
6. **Sin información sensible**: Verifica que no hay datos reales
7. **Cursor**: Evita que aparezca el cursor en la captura
8. **Luz**: Usa tema claro para mejor legibilidad en README

---

## 📁 Nomenclatura

Guarda con estos nombres exactos (el README los referencia):

```
screenshots/
├── dashboard.png
├── patients.png
├── patient-form.png
├── treatment-detail.png
├── graphql-playground.png
├── swagger-ui.png
└── mobile-dashboard.png
```

---

## 🎨 Post-Procesamiento

### Agregar Anotaciones (Opcional)
- Flechas apuntando a features clave
- Texto descriptivo
- Highlight de funcionalidades importantes

### Crear Mockup (Opcional)
Usa herramientas como:
- https://mockuphone.com
- https://deviceframes.com
- https://mockup.io

Agrega tus screenshots en un marco de laptop/monitor para efecto profesional.

---

## 📊 Tamaño Recomendado

| Screenshot | Tamaño Máximo | Formato |
|-----------|---------------|---------|
| Dashboard | 500 KB | PNG |
| Patients | 400 KB | PNG |
| Forms | 300 KB | PNG |
| Mobile | 200 KB | PNG |
| GraphQL | 300 KB | PNG |

**Comprime después de capturar** con TinyPNG para optimizar carga en GitHub.

---

## ✅ Checklist Pre-Screenshot

- [ ] Base de datos con seed data ejecutado
- [ ] Sin errores en consola (F12)
- [ ] Zoom del browser al 100%
- [ ] Tema/colores consistentes
- [ ] Datos ficticios realistas (nombres, emails, DNIs falsos)
- [ ] Sin información personal o sensible
- [ ] Navbar/UI completamente cargada
- [ ] Sin spinners de loading (a menos que sea intencional)

---

**Una imagen vale más que mil palabras - haz que cuenten** 📸

