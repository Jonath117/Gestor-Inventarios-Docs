#### ADR 002: Elección de Base de Datos

**Estado:** Aceptado  

**Contexto:** El módulo de inventario maneja transacciones críticas (Kárdex, entradas, salidas). Se necesita garantizar la integridad referencial (ej. no borrar una categoría si tiene productos) y propiedades ACID (Atomicidad, Consistencia, Aislamiento, Durabilidad) estables, especialmente al calcular el stock en tiempo real. 

**Decisión:** Se elige **PostgreSQL** como motor de base de datos relacional.  

**Alternativas descartadas:**

- _MongoDB (NoSQL):_ Descartado categóricamente. Las bases de datos documentales no son adecuadas para sistemas transaccionales y de kárdex donde las relaciones entre Movimientos, Productos y Bodegas son estrictas.
    
- _MySQL:_ Descartado a favor de PostgreSQL debido al rendimiento superior de este último en consultas complejas, manejo de concurrencia y soporte avanzado para tipos de datos JSON si se requiere en el futuro.

- **Consecuencias:** Garantía total de integridad de datos. Obliga al equipo a gestionar correctamente las migraciones mediante Entity Framework Core para reflejar los cambios del modelo.