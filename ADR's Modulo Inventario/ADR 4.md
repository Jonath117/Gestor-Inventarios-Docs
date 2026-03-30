#### ADR 004: Dimensionamiento de Servidores y Especificaciones

**Estado:** Aceptado  

**Contexto:** Se requiere alojar la base de datos, la API y el Frontend asegurando alta disponibilidad, costos controlados para la etapa inicial, y una latencia mínima para los usuarios objetivo ubicados en la región sudamericana.  

**Decisión:** Se desplegará la infraestructura en servidores virtuales privados (VPS) alojados en la región de **São Paulo (Brasil)** o **Miami**, dependiendo del proveedor (ej. AWS EC2, DigitalOcean). Las especificaciones iniciales mínimas serán:

- _Servidor API & DB:_ Linux (Ubuntu), 2 vCPUs, 4GB RAM, 50GB SSD NVMe.
    
- _Frontend:_ Alojamiento en CDN estático (Vercel, Netlify o AWS S3) para carga instantánea. 

- **Alternativas descartadas:**
    
- _Arquitectura Serverless (AWS Lambda):_ Descartada temporalmente debido a los tiempos de arranque en frío (_cold starts_) que pueden afectar la experiencia del usuario en sistemas ERP, y la complejidad de configurar Entity Framework con conexiones pooling serverless.
    
- _Hosting Compartido (cPanel):_ Descartado por falta de acceso root y la incapacidad de correr el entorno .NET 10 de manera nativa y segura. **Consecuencias:** Un costo mensual predecible y bajo (aprox. $15 - $25 USD). Latencia optimizada (< 80ms) por la cercanía geográfica. Se asume la responsabilidad de configurar la seguridad del servidor Linux y los respaldos automáticos de la base de datos PostgreSQL.