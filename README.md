# CreditSmart - Aplicación de Créditos con React

Aplicación dinámica desarrollada con **React 18** y **Vite** para gestionar productos crediticios de forma interactiva.

## ✨ Características

### 1. **Catálogo de Créditos (Home)**
- Lista dinámica de 6 tipos de productos crediticios
- Componente `CreditCard` reutilizable con props
- Renderizado con `.map()` desde array de datos
- Tarjetas interactivas con hover effects

### 2. **Simulador de Créditos**
- **Búsqueda en tiempo real** por nombre/descripción
- **Filtro por rango de monto** (mín y máx)
- **Ordenamiento** por: Nombre, Tasa (asc/desc), Monto máximo
- Mensaje "No hay créditos disponibles" cuando no hay resultados
- Panel filtrable con validación visual

### 3. **Solicitud de Crédito**
- **Formulario completo** con validaciones en tiempo real
- Captura de datos personales y laborales
- **Cálculo automático de cuota mensual** al cambiar monto/plazo
- **Resumen dinámico** en panel lateral (sticky)
- Validaciones:
  - Campos requeridos
  - Rangos de montos y plazos por tipo de crédito
  - Email válido
  - Ingreso > 0
- **Mensaje de éxito** tras enviar
- **Tabla de solicitudes** registradas (en memoria)
- Limpieza automática del formulario

## 🛠️ Tecnologías

- **React 18** - Librería UI
- **Vite** - Build tool moderno
- **Bootstrap 5** - Framework CSS
- **Bootstrap Icons** - Iconografía
- **JavaScript ES6+** - Hooks (useState, useMemo)

## 📁 Estructura del Proyecto

```
proyecto_creditos/
├── index.html                    # Punto de entrada
├── package.json
├── vite.config.js
├── src/
│   ├── main.jsx                 # ReactDOM render
│   ├── App.jsx                  # Componente principal con ruteo
│   ├── components/
│   │   ├── Navbar.jsx           # Navegación
│   │   └── CreditCard.jsx       # Tarjeta de crédito reutilizable
│   ├── pages/
│   │   ├── Home.jsx             # Catálogo de créditos
│   │   ├── Simulator.jsx        # Simulador con filtros
│   │   └── RequestCredit.jsx    # Formulario de solicitud
│   └── data/
│       └── creditsData.js       # Array de productos crediticios
└── css/
    └── styles.css               # Estilos personalizados
```

## 🚀 Instalación y Ejecución

### 1. Instalar dependencias
```bash
npm install
```

### 2. Ejecutar en modo desarrollo
```bash
npm run dev
```
Accede en: `http://localhost:5173`

### 3. Construir para producción
```bash
npm run build
```

## 📊 Productos Crediticios Disponibles

1. **Crédito Personal** - 12.5% anual (500k - 50M)
2. **Crédito Vehicular** - 9.8% anual (5M - 200M)
3. **Crédito Hipotecario** - 7.5% anual (30M - 500M)
4. **Microcrédito** - 18.5% anual (100k - 5M)
5. **Crédito Educativo** - 6.8% anual (1M - 30M)
6. **Crédito para Negocios** - 11.2% anual (2M - 300M)

## 🎯 Funcionalidades Clave

### Gestión de Estado
- **useState** para formularios, búsqueda y filtros
- **useMemo** para optimización de filtrado

### Componentes Reutilizables
- `CreditCard` recibe props: credit, onRequest
- `Navbar` recibe props: onNavigate, currentPage

### Validaciones
- Email formato válido
- Montos dentro de rango permitido
- Plazos dentro de rango permitido
- Campos obligatorios

### Cálculos
- **Fórmula de cuota mensual**: `(P × i × (1+i)^n) / ((1+i)^n - 1)`
  - P = Principal
  - i = Tasa mensual (anual/12)
  - n = Meses

## 💾 Almacenamiento de Datos

Las solicitudes se almacenan en **memoria** (useState):
- Tabla visible de solicitudes registradas
- Persiste durante la sesión
- Se reinicia al refrescar la página

## 🎨 Estilos

- **Variables CSS** para colores consistentes
- **Gradientes** en hero section
- **Animaciones** fade-in y hover
- **Responsive** para móvil y desktop
- **Accessibility** con iconos y labels

## 📱 Compatibilidad

- ✅ Desktop (Chrome, Firefox, Safari, Edge)
- ✅ Tablet
- ✅ Mobile

## 🔄 Flujo de la Aplicación

```
App (ruteo)
├── Home → Catálogo completo
├── Simulator → Búsqueda y filtros
└── RequestCredit → Formulario + resumen
```

Cada página es independiente pero comparte datos de créditos desde `creditsData.js`.

## 📝 Notas de Desarrollo

- Los datos son estáticos en `creditsData.js` pero fácilmente integrable con API
- Las solicitudes se guardan en memoria (agregar backend para persistencia)
- El cálculo de cuota es aproximado (sin seguros/comisiones adicionales)
- Bootstrap simplifica el responsive design

---

**Desarrollado con React + Vite | 2024**
