# hexadecimal  Equipo 3 1VC4

Proyecto final

//Descripción del problema y la solución//
Programa diseñado para convertir números en sistema decimal, a números en sistemas hexadecimal y viseversa

Hexadecimal es un adjetivo que se emplea en el ámbito de las matemáticas para aludir al sistema de numeración cuya base es el número dieciséis (16).

//CODIGO FUENTE//

```
#include <stdio.h>

// Convierte un número decimal a hexadecimal
void decimalToHexadecimal(int decimal) {
    char hexadecimal[100];
    int i = 0;
    
    while (decimal != 0) {
        int remainder = decimal % 16;
        if (remainder < 10) {
            hexadecimal[i] = remainder + '0';
        } else {
            hexadecimal[i] = remainder + 55; // A=65, 10+55=65
        }
        decimal = decimal / 16;
        i++;
    }
    
    printf("El número hexadecimal es: ");
    for (int j = i - 1; j >= 0; j--) {
        printf("%c", hexadecimal[j]);
    }
    printf("\n");
}

// Convierte un número hexadecimal a decimal
void hexadecimalToDecimal(char *hexadecimal) {
    int decimal = 0;
    int base = 1;
    int length = strlen(hexadecimal);
    
    for (int i = length - 1; i >= 0; i--) {
        if (hexadecimal[i] >= '0' && hexadecimal[i] <= '9') {
            decimal += (hexadecimal[i] - '0') * base;
        } else if (hexadecimal[i] >= 'A' && hexadecimal[i] <= 'F') {
            decimal += (hexadecimal[i] - 55) * base; // A=65, 65-55=10
        } else if (hexadecimal[i] >= 'a' && hexadecimal[i] <= 'f') {
            decimal += (hexadecimal[i] - 87) * base; // a=97, 97-87=10
        }
        base *= 16;
    }
    
    printf("El número decimal es: %d\n", decimal);
}

int main() {
    int decimal;
    char hexadecimal[100];
    int choice;

    printf("Conversor decimal-hexadecimal y hexadecimal-decimal\n");
    printf("1. Decimal a Hexadecimal\n");
    printf("2. Hexadecimal a Decimal\n");
    printf("Ingrese su opción: ");
    scanf("%d", &choice);
    
    switch (choice) {
        case 1:
            printf("Ingrese un número decimal: ");
            scanf("%d", &decimal);
            decimalToHexadecimal(decimal);
            break;
        case 2:
            printf("Ingrese un número hexadecimal: ");
            scanf("%s", hexadecimal);
            hexadecimalToDecimal(hexadecimal);
            break;
        default:
            printf("Opción inválida.\n");
            break;
    }
    
    return 0;
}
```
//INDICACIONES//

Para poder ejecutar el programa es necesario descargarlo y utilizar cualquier compilador de lenguaje C o C++

Descargar el programa. Abrirlo en un compilador y ejecutar. 
El usuario va a ingresar algún número decimal
Se arrojará el resultado con números hexadecimales
El usuario ingresara un número en sistema hexadecimal
El programa arrojara el número en sistema numérico decimal





