# Estructura del Proyecto
````
ERP_System/
├── 📂 backend (C# .NET 10)
│   ├── 📂 Backend.API                 # Controladores (Endpoints), Middlewares y Program.cs
│   └── 📂 src
│       └── 📂 Modules
│           └── 📂 Inventory
│               ├── 📂 Inventory.Domain      # Entidades (Product, Movement) e Interfaces
│               ├── 📂 Inventory.Application # DTOs y Servicios (Reglas de negocio)
│               └── 📂 Inventory.Infrastructure # DbContext, Migraciones PostgreSQL y Repositorios
│
└── 📂 frontend (React + TypeScript)
    ├── 📂 public
    └── 📂 src
        ├── 📂 components                # Componentes genéricos UI (Button, Modal, Toast)
        ├── 📂 features                  # Módulos específicos (ProductForm, StockTable)
        ├── 📂 services                  # Llamadas HTTP a la API (fetch)
        ├── 📂 types                     # Interfaces de TypeScript para tipado
        └── 📜 App.tsx                   # Punto de entrada de la aplicación
````