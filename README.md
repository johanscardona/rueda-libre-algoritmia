Algoritmo CotizacionBasica
    
    Definir nombreCliente Como Caracter;
    Definir horasAlquiler Como Entero;
    Definir totalPagar Como Entero;
    Definir PRECIO_HORA Como Entero;
    
    PRECIO_HORA <- 10000;
    
    
    Escribir "Por favor, ingrese el nombre del cliente:";
    Leer nombreCliente;
    
    Escribir "Ingrese la cantidad de horas de alquiler:";
    Leer horasAlquiler;

    totalPagar <- horasAlquiler * PRECIO_HORA;
    
    Escribir "Hola, ", nombreCliente, ": tu alquiler de ", horasAlquiler, " horas cuesta $", totalPagar;
FinAlgoritmo
# rueda-libre-algoritmia
