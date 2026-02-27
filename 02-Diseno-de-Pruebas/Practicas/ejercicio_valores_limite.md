# Ejercicio: Análisis de Valores Límite - Validación de Edad

## Requisito de Negocio
El sistema debe aceptar usuarios entre 18 y 60 años.

## Técnica Aplicada
Análisis de Valores Límite y Partición de Equivalencia.

## Datos de Prueba Seleccionados

### Valores Válidos
- **18** (límite inferior)
- **40** (valor nominal)
- **60** (límite superior)

### Valores Inválidos
- **17** (fuera del límite inferior)
- **61** (fuera del límite superior)

## Justificación

Probar con los valores 17 y 61 es vital para verificar que el sistema maneje correctamente las excepciones y rechace valores fuera del rango permitido. 

Los valores límite (18 y 60) son críticos porque son los puntos donde el comportamiento del sistema cambia de inválido a válido o viceversa. Estos son los lugares más propensos a errores de implementación, como usar operadores incorrectos (< en lugar de <=, por ejemplo).

Al probar tanto los valores límite válidos como los valores inmediatamente fuera de los límites, aseguramos que:
1. El sistema acepta correctamente usuarios en el rango permitido
2. El sistema rechaza apropiadamente usuarios fuera del rango
3. La lógica de validación no presenta errores en los puntos críticos de transición
4. El sistema no se rompe al recibir entradas inválidas y maneja las excepciones de forma controlada