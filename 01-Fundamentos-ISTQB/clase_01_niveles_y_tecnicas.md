# 📚 Clase 01: Niveles de Pruebas y Técnicas de Diseño
**Fecha:** 25 de Febrero de 2026 | **Bootcamp:** QA Innovation Lab - NTT DATA

## 🎯 1. Verificación vs. Validación
Entender esta diferencia es fundamental para asegurar el éxito del proyecto y evitar retrabajos costosos. Como QA, aplicamos la estrategia *Shift Left* (preguntas tempranas) para garantizar ambos aspectos.

* **Verificación ("¿Estamos construyendo el producto correctamente?"):** Se enfoca en la adherencia a las especificaciones técnicas.
* **Validación ("¿Estamos construyendo el producto correcto?"):** Se enfoca en satisfacer la necesidad real del negocio.
* **Ejemplo Práctico:** Si el cliente pide un "vehículo de transporte" para su familia de cinco personas y el equipo construye una motocicleta con un código perfecto, el producto pasa la Verificación, pero falla críticamente en la Validación porque no resuelve el problema del usuario.

## 🔄 2. El Modelo V (Vinculando Desarrollo con Pruebas)


[Image of V-Model in software testing]

Este modelo establece que cada fase de desarrollo tiene su contraparte exacta en los niveles de prueba, permitiendo diseñar las pruebas desde el inicio del ciclo de vida.

**Fases de Desarrollo (Izquierda) ➔ Niveles de Prueba (Derecha)**
1. Requisitos de negocio ➔ Pruebas de Aceptación
2. Especificación del proyecto ➔ Pruebas de Sistema
3. Diseño técnico / Arquitectura ➔ Pruebas de Integración
4. Diseño específico / Codificación ➔ Pruebas de Componente

## 🏗️ 3. Los 4 Niveles de Prueba en Detalle

### Nivel 1: Pruebas de Componente (Unitarias)
* **Objetivo:** Probar unidades de código individuales y aisladas.
* **Métodos:** Dinámico (ejecución del código) y Estático (revisión de código en busca de contraseñas quemadas o variables sin uso).
* **Herramientas de Aislamiento:**
  
  * **Stubs:** Simulan la *respuesta* de un componente para probar de forma independiente a su consumidor.
  * **Drivers:** Simulan la *invocación* de un componente para probarlo sin necesidad de un consumidor real (Ej. Usar Postman para disparar peticiones a una API).

### Nivel 2: Pruebas de Integración
* **Objetivo:** Probar las interfaces e interacciones entre componentes (que previamente pasaron sus pruebas unitarias).
* **Estrategias principales:**
  * *Big Bang:* Integrar todos los componentes de golpe (más riesgoso).
  * *Incremental:* Integrar y probar los componentes uno por uno.

### Nivel 3: Pruebas de Sistema
* **Objetivo:** Probar el sistema completo e integrado en un entorno de QA idéntico al de producción.
* **Enfoque Dual:**
  * **Funcional:** Qué hace el sistema (Ej. Imprimir una factura).
  * **No Funcional:** Cómo rinde el sistema (Ej. Imprimir la factura en menos de 5 segundos).

### Nivel 4: Pruebas de Aceptación (UAT)
* **Objetivo:** Pruebas lideradas por los usuarios finales para confirmar que el sistema satisface las necesidades del negocio. No buscan encontrar bugs, sino validar flujos de trabajo.
* **Tipos:**
  * *Pruebas Alfa:* Realizadas internamente por el equipo de desarrollo.
  * *Pruebas Beta:* Realizadas externamente por usuarios reales en un entorno similar a producción.

## 🔁 4. Modelo V Iterativo
Es la aplicación del Modelo V en metodologías ágiles. El proyecto se divide en fases (Fase 1, Fase 2...), donde cada fase pasa por el ciclo completo (Definir ➔ Desarrollar ➔ Probar ➔ Implementar), resultando en entregables completamente funcionales que se integran progresivamente.