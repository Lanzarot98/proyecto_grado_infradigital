# InfraDigital - Plataforma Web Progresiva (PWA) para MiPyMEs

**Proyecto de Grado - Ingeniería de Sistemas**  
Universidad Nacional Abierta y a Distancia (UNAD)  
Curso: Proyecto de Grado - Código: 202016907

## Descripción

InfraDigital es una Aplicación Web Progresiva (PWA) orientada a facilitar la digitalización y gestión integral de los procesos productivos en micro y pequeñas empresas (MiPyMEs) colombianas. La plataforma integra módulos de gestión de inventarios, facturación electrónica con IVA del 19%, administración de clientes (CRM básico), y un dashboard analítico con indicadores de productividad.

## Stack Tecnológico

| Capa | Tecnología |
|------|-----------|
| **Frontend** | React.js 18, React Router v6, Recharts, jsPDF |
| **Backend** | Node.js, Express.js, Sequelize ORM |
| **Base de Datos** | PostgreSQL |
| **Autenticación** | JWT (JSON Web Tokens) |
| **PWA** | Service Workers, IndexedDB, Web App Manifest |
| **Documentación API** | Swagger / OpenAPI 3.0 |

## Arquitectura

```
┌─────────────────────────────────────────────────┐
│                  FRONTEND (PWA)                  │
│        React.js + Service Workers + IndexedDB    │
├─────────────────────────────────────────────────┤
│                   API REST                       │
│           Express.js + JWT Auth                  │
├─────────────────────────────────────────────────┤
│               BASE DE DATOS                      │
│          PostgreSQL + Sequelize ORM              │
└─────────────────────────────────────────────────┘
```

## Módulos Funcionales

1. **Gestión de Inventarios** - CRUD de productos, control de stock en tiempo real, alertas de desabastecimiento, registro de movimientos de entrada/salida
2. **Facturación** - Generación de facturas con IVA 19%, historial de transacciones, exportación PDF, métodos de pago
3. **CRM Básico** - Registro de clientes, historial de compras, segmentación por tipo (Persona Natural/Jurídica)
4. **Dashboard Analítico** - KPIs en tiempo real, gráficas de ventas, productos más vendidos, tendencias de ingresos
5. **Capacidades PWA** - Funcionamiento offline, instalación desde navegador, sincronización en segundo plano

## Requisitos Previos

- **Node.js** >= 18.x
- **PostgreSQL** >= 14.x
- **npm** >= 9.x
- **Git**


## Estructura del Proyecto

```
infradigital/
├── backend/
│   ├── src/
│   │   ├── config/          # Configuración de BD y Swagger
│   │   ├── controllers/     # Lógica de negocio
│   │   ├── middleware/       # Auth JWT, validación, errores
│   │   ├── models/           # Modelos Sequelize (User, Product, Client, Invoice...)
│   │   ├── routes/           # Endpoints API REST
│   │   ├── seeders/          # Datos de ejemplo
│   │   └── utils/            # Funciones auxiliares
│   ├── .env.example
│   └── package.json
├── frontend/
│   ├── public/
│   │   ├── index.html        # Shell HTML
│   │   ├── manifest.json     # PWA Manifest
│   │   └── sw.js             # Service Worker
│   ├── src/
│   │   ├── components/       # Componentes reutilizables (Layout, Card, Table, Modal...)
│   │   ├── context/          # AuthContext, AppContext
│   │   ├── hooks/            # Custom hooks (useOnlineStatus)
│   │   ├── pages/            # Páginas por módulo (Auth, Dashboard, Inventory, Invoices, Clients)
│   │   ├── services/         # API service, IndexedDB offline
│   │   ├── styles/           # Variables CSS, estilos globales
│   │   └── utils/            # Formatters (moneda colombiana, fechas)
│   └── package.json
├── .gitignore
└── README.md
```


## Licencia

Este proyecto fue desarrollado como trabajo de grado para el programa de Ingeniería de Sistemas de la UNAD.


