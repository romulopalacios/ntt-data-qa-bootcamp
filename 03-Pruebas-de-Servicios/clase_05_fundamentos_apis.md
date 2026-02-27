# 🌐 Clase 05: Fundamentos de Pruebas de Servicios (API Testing)
**Fecha:** 27 de Febrero de 2026 | **Bootcamp:** QA Innovation Lab - NTT DATA 

---

## 🏗️ 1. Arquitectura y Conceptos Base

En el desarrollo de software moderno, las aplicaciones no son bloques únicos, sino conjuntos de piezas que se comunican entre sí.

### Conceptos Fundamentales

* **Servicio Web (Web Service):** Es una función o recurso expuesto en una red (vía HTTP) que permite la comunicación sistema a sistema. Es el "plano" o la definición de cómo hablarse.

* **API (Application Programming Interface):** Es la implementación concreta del servicio. Si el servicio web es el plano, la API es el edificio construido y listo para ser usado.

* **SOA (Service Oriented Architecture):** Un enfoque donde el sistema se descompone en servicios pequeños e independientes. Esto mejora la continuidad del negocio: si un servicio falla, el resto del sistema puede seguir operando.

* **ESB (Enterprise Service Bus):** Actúa como un "enrutador" inteligente o mediador. Pone en cola las solicitudes y las entrega al servicio correcto, evitando que el sistema se sature.

---

## 🛰️ 2. Estilos de Comunicación: SOAP vs. REST

Como QA, entender la diferencia entre estos dos es vital para saber qué validar en los paquetes de datos (Payloads).

| Característica | SOAP (Protocolo) | REST (Estilo Arquitectónico) |
|----------------|------------------|------------------------------|
| **Formato** | Exclusivamente XML | Principalmente JSON (más ligero) |
| **Rigidez** | Muy estricto, reglas predefinidas | Flexible y desacoplado |
| **Verbos** | Usa principalmente GET y POST | Usa verbos HTTP estándar (GET, POST, PUT, DELETE) |
| **Uso común** | Entornos empresariales, banca, alta seguridad | Apps web, móviles, redes sociales, IoT |

### Los Verbos HTTP en REST

Un error común de desarrollo que el QA debe reportar es el uso incorrecto de los métodos:

* **GET:** Recuperar información (no debe modificar nada en la base de datos).
* **POST:** Crear un nuevo recurso.
* **PUT:** Actualizar un recurso existente.
* **DELETE:** Eliminar un recurso.

---

## ⏱️ 3. Sincronismo: ¿Cómo viaja la información?

La forma en que el cliente espera la respuesta define la experiencia del usuario y la estrategia de carga.

### Sincrónico
El cliente envía la solicitud y se queda "bloqueado" esperando la respuesta.

* **Ejemplo:** Una consulta de saldo en un cajero automático.

### Asincrónico
El cliente envía la solicitud, recibe una confirmación de "recibido" y continúa con otras tareas. El servicio avisa cuando el proceso termina.

* **Ejemplo:** El procesamiento de un video pesado en una plataforma; puedes seguir navegando mientras se procesa.

---

## 🛠️ Notas para el Repositorio de QA

### Pruebas Estáticas
Antes de ejecutar una API, se deben revisar los contratos (Swagger/WSDL) para asegurar que los nombres de campos y tipos de datos coincidan con los requisitos.

### Validación de Status Codes
Es fundamental verificar que la API devuelva los códigos correctos:
* `200 OK` - Solicitud exitosa
* `201 Created` - Recurso creado exitosamente
* `400 Bad Request` - Error en la solicitud del cliente
* `404 Not Found` - Recurso no encontrado
* `500 Internal Server Error` - Error del servidor