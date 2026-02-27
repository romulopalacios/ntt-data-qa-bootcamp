# 📚 Clase 04: BDD y Redacción Profesional en Gherkin
**Fecha:** 27 de Febrero de 2026 | **Bootcamp:** QA Innovation Lab - NTT DATA
## 💡 1. Filosofía BDD (Behavior-Driven Development)
BDD no es solo escribir pruebas; es una metodología de colaboración para cerrar la brecha entre el negocio y la tecnología.

* **Entendimiento Compartido:** El objetivo es que el Product Owner, el Desarrollador y el QA (Los Tres Amigos) tengan la misma visión antes de escribir código.
* **Documentación Viva:** Los archivos `.feature` sirven como manual de usuario y, a la vez, como scripts de prueba automatizables. Nunca se desactualizan porque el sistema solo pasa si la documentación coincide con el comportamiento.



## 🏗️ 2. Estructura de Gherkin (Lenguaje Ubicuo)
Gherkin utiliza una sintaxis estructurada en lenguaje natural para describir comportamientos.

### Palabras Clave Principales:
* **Feature (Característica):** Describe la funcionalidad global (ej. Gestión de pedidos).
* **Scenario (Escenario):** Un caso de uso específico o flujo de usuario.
* **Given (Dado):** Establece las precondiciones y el estado inicial del sistema.
* **When (Cuando):** La acción clave o el evento disparador realizado por el usuario.
* **Then (Entonces):** El resultado esperado o la validación del sistema.
* **And / But (Y / Pero):** Conectores para añadir más pasos sin repetir las palabras clave anteriores.

## ⚙️ 3. Gherkin Imperativo vs. Declarativo
En este nivel de formación, NTT DATA prioriza el **Estilo Imperativo**.

* **Estilo Imperativo (Enfoque Técnico):** Describe el "Cómo". Se enfoca en acciones detalladas de la UI (ej. "Hago clic en el botón", "Escribo en el campo").
    * *Ventaja:* Facilita la creación de "Step Definitions" reutilizables en herramientas de automatización como Selenium o Playwright.
* **Estilo Declarativo (Enfoque de Negocio):** Describe el "Qué". Se enfoca en la intención del usuario (ej. "Inicio sesión correctamente").



## 🚀 4. Técnicas de Optimización y Reutilización

### Background (Antecedentes)
Se usa para definir pasos que son comunes a **todos** los escenarios de un archivo.
> **Ejemplo:** Si todos los escenarios requieren que el usuario esté en la página de "Logueo", se coloca en el Background una sola vez al inicio.

### Scenario Outline (Esquema del Escenario)
Es la herramienta más poderosa para el **Data-Driven Testing**. Permite ejecutar el mismo flujo con múltiples variaciones de datos usando una tabla de `Examples`.

```gherkin
Esquema del escenario: Validar precios del menú
  Dado que selecciono el sándwich <Producto>
  Entonces el precio mostrado debe ser <Precio>

  Ejemplos:
    | Producto    | Precio |
    | Chicharrón  | 5.50   |
    | Pavo        | 6.00   |
🏷️ 5. Organización con Tags (Etiquetas)
Las etiquetas permiten categorizar y filtrar las pruebas para ejecuciones inteligentes:

@smoke: Pruebas de humo (críticas).

@regression: Pruebas de regresión total.

@ignore: Pruebas en desarrollo que no deben ejecutarse aún.

✅ 6. Los 7 Pilares de un Escenario Altamente Efectivo
Para garantizar la calidad técnica, cada escenario debe ser:

Preciso: Sin ambigüedades.

Declarativo (en esencia): Aunque el paso sea imperativo, el escenario debe contar una historia clara.

Independiente: Un escenario no debe depender de que el anterior haya pasado.

Atómico: Probar una sola cosa a la vez.

Gramaticalmente correcto: Escrito profesionalmente.

Sin detalles de implementación innecesarios.

Orientado al valor de negocio.