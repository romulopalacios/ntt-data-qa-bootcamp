# 📚 Clase 02: Técnicas de Diseño de Pruebas Funcionales (Caja Negra)
**Fecha:** 26 de Febrero de 2026 | **Bootcamp:** QA Innovation Lab - NTT DATA

## 🎯 Concepto Clave: Pruebas de Caja Negra
Son técnicas que se enfocan en evaluar las entradas y salidas de un sistema sin conocer su estructura de código interno. El principio fundamental que rige el diseño de estos casos de prueba es: **Un caso de prueba es exitoso ("pasa") si el resultado real coincide con el resultado esperado**, incluso si ese resultado esperado es bloquear una acción no autorizada (rutas inválidas).

---

## 🛠️ Las 4 Técnicas Principales



### 1. Partición de Equivalencia (EP) y Valores Límite (BVA)
Se utilizan en conjunto para probar eficientemente campos que aceptan rangos de datos numéricos o secuencias.
* **Partición de Equivalencia (EP):** Divide los datos de entrada en grupos (particiones) donde el sistema debería comportarse igual. Probar un solo valor representativo por partición valida todo el grupo, ahorrando tiempo.
* **Análisis de Valores Límite (BVA):** Evalúa los extremos exactos de esas particiones (límites válidos e inválidos), ya que estadísticamente es donde ocurren la mayoría de los defectos de programación (errores de `<` vs `<=`).
* **Sinergia:** El BVA por sí solo no puede determinar si el fallo es exclusivo del límite o de toda la partición. Usarlos juntos (EP + BVA) permite aislar y encontrar la causa raíz del defecto.



### 2. Tablas de Decisión
* **Propósito:** Probar lógicas de negocio complejas basadas en múltiples condiciones booleanas (Verdadero/Falso). Se usan cuando EP/BVA no aplican (ej. validar si un usuario tiene permisos).
* **Estructura:** Es una matriz que cruza todas las combinaciones posibles de condiciones con las acciones que el sistema debe ejecutar.
* **Optimización:** Se utiliza el símbolo de "no importa" (`-`) para simplificar la tabla cuando una condición previa ya determinó el resultado (Ej. Si el `Usuario es Inválido`, ya no importa evaluar si la `Contraseña es Válida`).



### 3. Pruebas de Transición de Estados
* **Propósito:** Evaluar sistemas que cambian su comportamiento dependiendo de su estado actual (Ej. Un ciclo de vida de un ticket, o el estado de un pedido en un e-commerce).
* **Aplicación:** Se mapean todos los nodos (estados) y flechas (transiciones) en un diagrama. 
* **El Enfoque QA:** No solo se prueban los caminos felices (Ej. *Abierto ➔ Asignado ➔ Resuelto*), sino que es obligatorio forzar caminos inválidos (Ej. *Asignado ➔ Cerrado* sin pasar por Resuelto) para garantizar que el sistema impida correctamente la acción.

### 4. Pruebas de Casos de Uso (UAT)
* **Propósito:** Probar flujos de trabajo de negocio de extremo a extremo (End-to-End) desde la perspectiva del usuario final.
* **Integración:** Es la técnica integradora por excelencia. Un solo Caso de Uso (Ej. "Solicitar un préstamo") puede requerir:
  1. **EP/BVA** para validar la edad y el monto.
  2. **Tabla de Decisión** para aprobar o rechazar según el historial crediticio.
  3. **Transición de Estados** para cambiar la solicitud de *Pendiente* a *Aprobada*.
* **Riesgo:** Un mal levantamiento de requisitos en esta etapa genera retrabajo masivo, ya que se estaría probando un flujo que no aporta valor al negocio.

---
**Siguientes Pasos:** Analizar historias de usuario reales aplicando combinaciones de estas 4 técnicas para asegurar una cobertura de prueba sólida.