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



## MiniReto 4: Asistente de Taquilla v0.1

### 1. Descomposición del Problema (Flujo de Cálculos)
1. **Costo Alquiler:** Multiplica `cantBicicletas` * `horasAlquiler` * `PRECIO_HORA_BICI (10000)`.
2. **Costo Recorrido:** Multiplica `cantPersonas` * `precioRecorridoPersona`.
3. **Subtotal:** Suma del costo de alquiler y del recorrido.
4. **Aporte:** Calcula el 10% sobre el Subtotal.
5. **Total General:** Suma del Subtotal + Aporte.
6. **Valor Individual Redondeado:** Divide el Total General entre `cantPersonas` y aplica la fórmula de techo a la centena.

### 2. Explicación de la Fórmula de Redondeo
Para redondear hacia arriba a la centena se empleó la expresión: `trunc(valorPersonaExacto / 100 + 0.99) * 100`.
- **¿Por qué funciona?** Al dividir por 100, convertimos las centenas en unidades decimales (ej. $33334 se vuelve 333.34). Sumarle `0.99` fuerza a que cualquier residuo decimal salte al siguiente número entero (333.34 + 0.99 = 334.33). Aplicar `trunc` elimina los decimales sobrantes dejándolo en 334. Finalmente, multiplicar por 100 restaura el valor a la centena exacta ($33.400).

### 3. Registro de Casos de Prueba (Validación)
- **Caso 1 (3 personas, 3 bicis, 2 horas, Río y Parques $45k):**
  - Esperado a Mano: Total = $214.500 | Por persona = $71.500
  - Resultado Algoritmo: Total = $214.500 | Por persona = $71.500
- **Caso 2 (4 personas, 3 bicis, 3 horas, Sabores de Barrio $60k):**
  - Esperado a Mano (Exacto): Total = $363.000 | Por persona = $90.750
  - Redondeado a Centena Esperado: **$90.800**
  - Resultado Algoritmo: Total = $363.000 | Por persona = **$90.800** (Coincide perfectamente)
- **Caso 3 (Diseño propio - 2 personas, 2 bicis, 1 hora, Las Palmas $85k):**
  - Esperado a Mano: Total = $209.000 | Por persona = $104.500
  - Resultado Algoritmo: Total = $209.000 | Por persona = $104.500
