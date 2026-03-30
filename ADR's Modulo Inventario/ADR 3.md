#### ADR 003: Arquitectura de Monolito Modular vs Microservicios

**Estado:** Aceptado  

**Contexto:** El proyecto corresponde a un sistema ERP/Gestión Empresarial en fase de lanzamiento. Se necesita iterar rápidamente sin añadir complejidad innecesaria en la infraestructura y despliegue.  

**Decisión:** Se implementa un **Monolito Modular** utilizando el patrón de _Clean Architecture_. Todos los módulos (Inventario, etc.) conviven en la misma base de código y base de datos, pero están estrictamente separados por carpetas y dominios lógicos.

**Alternativas descartadas:**

- _Microservicios:_ Descartado por el alto costo operativo y la complejidad técnica que conlleva (latencia de red, consistencia eventual, orquestación con Kubernetes) para un producto que recién inicia y aún no tiene cuellos de botella masivos de tráfico.  

- **Consecuencias:** Despliegues simples y código altamente cohesivo. Si en el futuro un módulo específico (ej. Facturación masiva) requiere escalar desproporcionadamente, la separación lógica actual (Clean Architecture) permitirá extraerlo a un microservicio sin reescribir la lógica de negocio.