
### ADR 1: Selección de Stack Tecnológico (Backend y Frontend)

**Estado:** Aceptado  

**Contexto:** El sistema requiere un backend tipado, seguro y de alto rendimiento para manejar reglas de negocio complejas (transacciones de inventario multi-empresa), junto con una interfaz de usuario reactiva, moderna y mantenible a largo plazo. C# es requisito para el desarrollo del backend.   

**Decisión:** Se adopta **.NET 10 (C#)** para la construcción de una API RESTful, y **React (con Vite) + TypeScript + Tailwind CSS** para el frontend.  

**Alternativas descartadas:**  

- _Node.js / Express:_ Descartado debido a que C# ofrece un tipado estricto nativo mucho más robusto para operaciones financieras y de kárdex, además de contar con Entity Framework Core.
    
- _Angular:_ Descartado por tener una curva de aprendizaje mayor y mayor verbosidad para el tamaño actual del equipo, prefiriendo la agilidad de los ecosistemas basados en componentes de React.  

- **Consecuencias:** Se obtiene seguridad de tipos "end-to-end" (C# y TypeScript). La mantenibilidad del código es alta, aunque exige que los desarrolladores dominen ambos paradigmas y ecosistemas.