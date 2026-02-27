# 📚 Clase 03: Scrum, BDD y Redacción de Casos en Gherkin
**Fecha:** 26 de Febrero de 2026 | **Bootcamp:** QA Innovation Lab - NTT DATA

## 🎯 1. Fundamentos de Scrum para QA
Scrum es el marco de trabajo ágil donde el QA se desenvuelve, entregando valor en ciclos cortos (Sprints).

![Scrum Framework](https://scrumorg-website-prod.s3.amazonaws.com/drupal/inline-images/2021-01/scrumorg-scrum-framework-3000.png)

* **Roles:** Product Owner (define el qué), Scrum Master (facilita el cómo), Equipo de Desarrollo (construye), **QA** (valida contra requisitos).
* **Artefactos:** Product Backlog (lista total de requisitos) y Sprint Backlog (lo que se hará en el sprint actual).
* **Conceptos Críticos para QA:**
  * **Definition of Ready (DoR):** La historia de usuario está lista para empezar a desarrollarse. *Si no tiene criterios de aceptación claros, QA debe rechazarla para proteger al equipo.*
  * **Definition of Done (DoD):** El incremento está desarrollado, probado (por QA) y documentado.

## 📝 2. Historias de Usuario (El Contrato de QA)
Es la fuente de la verdad para probar una funcionalidad desde la perspectiva del valor para el usuario.
* **Estructura Estándar:** `Como` [rol], `quiero` [funcionalidad], `para` [beneficio].
* **Criterios de Aceptación:** Son las condiciones que definen si la historia está terminada. Deben ser SMART (Específicos, Medibles, Alcanzables, Relevantes, con límite de Tiempo).

## ⚖️ 3. BDD vs. TDD

* **TDD (Desarrollo Guiado por Pruebas):** Enfoque técnico (bajo nivel). Ciclo: Escribir prueba que falla (Rojo) ➔ Escribir código que la pasa (Verde) ➔ Refactorizar.
* **BDD (Desarrollo Guiado por Comportamiento):** Enfoque colaborativo (alto nivel). Usa ejemplos concretos para alinear el entendimiento entre negocio, desarrollo y QA antes de programar.

## 🥒 4. Gherkin (Especificaciones Ejecutables)
Es el lenguaje que materializa el BDD, eliminando la ambigüedad y preparando el terreno para la automatización.
* **Dado (Given):** El contexto o precondición inicial.
* **Cuando (When):** La acción que ejecuta el usuario.
* **Entonces (Then):** El resultado esperado y validado por el sistema.

## 🕵️ 5. El Rol Proactivo del QA
Un QA moderno no solo dice "esto falló". Un QA previene y analiza:
1. Replica el error para confirmarlo.
2. Aísla el problema ejecutando los pasos manualmente.
3. **Busca la causa raíz:** Por ejemplo, si un botón en la interfaz no funciona, el QA usa Postman para probar el servicio/API subyacente y ver si el fallo viene del backend.
4. Redacta un reporte de bug detallado con toda esta evidencia.