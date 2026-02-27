# 🍔 Tarea BDD: "El Sanguchón y el Campesino" (Rediseño Web)
**Autor:** Rómulo Palacios | **Rol:** QA Automation Trainee

## 📖 Historia de Usuario: HU-001 - Gestión del Carrito de Pedidos
**Descripción:**
* **Como** cliente frecuente de "El Sanguchón y el Campesino",
* **Quiero** poder agregar diferentes sándwiches y bebidas a mi carrito de compras virtual,
* **Para** armar mi pedido online, visualizar el total a pagar y evitar hacer filas o llamar por teléfono.

---

## ✅ Criterios de Aceptación (Gherkin format)

*(Nota del QA: Se han diseñado escenarios para probar tanto el "Camino Feliz" como el manejo de excepciones de negocio).*

### Escenario 1: Agregar un producto disponible al carrito vacío (Camino Feliz)
**Dado** que el cliente se encuentra en la página principal del menú y su carrito virtual está vacío
**Cuando** hace clic en el botón "Agregar al carrito" del "Sánguche de Chicharrón"
**Entonces** el sistema debe añadir 1 unidad de ese producto al carrito
**Y** el icono del carrito en la barra superior debe actualizar su contador a "1"
**Y** el subtotal del carrito debe actualizarse con el precio exacto del producto seleccionado.

### Escenario 2: Límite máximo de ítems por pedido (Análisis de Valores Límite)
**Dado** que el cliente ya tiene 10 ítems en su carrito de compras (límite máximo configurado por el negocio para pedidos web)
**Cuando** el cliente intenta agregar un 11vo ítem haciendo clic en "Agregar al carrito"
**Entonces** el sistema no debe añadir el producto al carrito
**Y** debe mostrar un mensaje de alerta UI indicando: "Para pedidos mayores a 10 ítems, por favor contáctenos por WhatsApp para ventas corporativas".

### Escenario 3: Producto agotado en base de datos (Excepción / Caja Negra)
**Dado** que el producto "Jugo de Papaya" tiene un inventario de "0" en la base de datos del restaurante
**Cuando** el cliente visualiza la sección de bebidas en el menú web
**Entonces** el botón de "Agregar al carrito" para ese producto debe estar deshabilitado (no clickeable)
**Y** debe mostrar una etiqueta visual que diga "Agotado".