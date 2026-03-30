## Diagrama de Arquitectura del Sistema
### **Arquitectura Cliente-Servidor con Backend en Clean Architecture**

- **Capa de Presentación (Frontend):** Single Page Application (SPA) construida en React + TypeScript. Se comunica con el backend exclusivamente a través de peticiones HTTP RESTful.
    
- **Capa de API (Backend - Entrypoint):** Expone los endpoints, maneja la autenticación/autorización y extrae el identificador multi-empresa (`x-company-id`) de los headers.
    
- **Capa de Aplicación (Casos de Uso):** Contiene los Servicios (ej. `ProductService`, `MovementService`) y los DTOs. Orquesta las reglas de negocio.
    
- **Capa de Dominio (Core):** Contiene las Entidades puras (`Product`, `InventoryStock`) y las interfaces de los repositorios. No tiene dependencias externas.
    
- **Capa de Infraestructura:** Implementa los repositorios utilizando Entity Framework Core 10 y maneja la comunicación directa con PostgreSQL.
![[diag_serv.png]]


## Diagrama de Base de datos

![[diag_bdd.png]]