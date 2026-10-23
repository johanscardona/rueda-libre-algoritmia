# Bitácora de Alquiler de Bicicletas

## Algoritmo en Lenguaje Natural (Paso a Paso)
1. El cliente ingresa al local de alquiler.
2. El cliente solicita el alquiler de una bicicleta al personal de atención.
3. El personal verifica la disponibilidad de bicicletas, cascos y candados.
4. El cliente presenta su documento de identidad y completa el formulario de registro.
5. El cliente realiza el pago correspondiente por el tiempo de alquiler solicitado.
6. El personal selecciona una bicicleta adecuada para la estatura del cliente.
7. El personal ajusta la altura del sillín de la bicicleta.
8. El personal entrega un casco de seguridad de la talla del cliente y verifica que se lo ajuste correctamente.
9. El personal entrega un candado de seguridad junto con su respectiva llave o código.
10. El personal realiza una última revisión visual de los frenos y la presión de las llantas.
11. El cliente recibe la bicicleta, el casco y el candado.
12. El cliente sale del local con todo el equipo listo para su uso.

## MiniReto 2: Modelo Entrada - Proceso - Salida

| Entrada (Dato y Tipo) | Proceso (Cálculo matemático) | Salida (Resultado a mostrar) |
| :--- | :--- | :--- |
| - nombreCliente (Caracter)<br>- horasAlquiler (Entero) | totalPagar <- horasAlquiler * PRECIO_HORA | Mensaje: "Hola [nombre]: tu alquiler de [horas] horas cuesta $[total]" |

## Casos de Prueba
- **Caso 1 (1 hora):** Esperado: $10.000 \| Obtenido: $10.000
- **Caso 3 (3 horas):** Esperado: $30.000 \| Obtenido: $30.000
- **Caso 8 (8 horas):** Esperado: $80.000 \| Obtenido: $80.000

## Análisis de Valores Especiales
- **Si se ingresa 0 horas:** El algoritmo procesará la operación (0 * 10000) y arrojará como resultado que el costo es $0. Lógicamente no tiene sentido alquilar algo por cero tiempo, pero el programa no se detendrá.
- **Si se ingresa un número negativo (ej. -2):** El algoritmo calculará -2 * 10000 y mostrará un total a pagar negativo ($-20000). Esto significaría que el local le debe dinero al cliente, lo cual es un error lógico de negocio que se corregirá en la próxima semana con condicionales.
