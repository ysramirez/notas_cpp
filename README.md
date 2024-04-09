# Sesión 01

## Introducción a la programación y conceptos básicos.

## Instalación del entorno de desarrollo (IDE) y configuración.

### Visual Studio Code
Para el curso usaremos Visual Studio Code (aunque podríamos usar un editor más ligero):
https://code.visualstudio.com/

Vamos a utilizar dos extensiones:

https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools

https://marketplace.visualstudio.com/items?itemName=danielpinto8zz6.c-cpp-compile-run

### Instalar G++ en Linux:
```shell
sudo apt install build-essential
```

### Instalar G++ en Windows:
#### Instalando MinGW para compilar en C/C++:
Para poder compilar un programa de C/C++ en Windows se necesita tener el compilador MinGW instalado
https://winlibs.com/

[Para 32 bits](https://github.com/brechtsanders/winlibs_mingw/releases/download/13.2.0posix-17.0.6-11.0.1-ucrt-r5/winlibs-i686-posix-dwarf-gcc-13.2.0-llvm-17.0.6-mingw-w64ucrt-11.0.1-r5.zip)

[Para 64 bits](https://github.com/brechtsanders/winlibs_mingw/releases/download/13.2.0posix-17.0.6-11.0.1-ucrt-r5/winlibs-x86_64-posix-seh-gcc-13.2.0-llvm-17.0.6-mingw-w64ucrt-11.0.1-r5.zip)


## Conceptos de compilación y ejecución.
### Compilación:
 Compilar es el proceso de transformar un programa informático escrito en un lenguaje en un conjunto de instrucciones en otro formato o lenguaje. Un compilador es un programa de computadora que realiza dicha tarea.

 Normalmente, un compilador transforma código escrito en un lenguaje de alto nivel como C++ en código ejecutable — llamado código binario o código máquina.

 El compilador que usaremos para nuestro curso se llama gcc.

https://developer.mozilla.org/es/docs/Glossary/Compile

### Ejecución:
La ejecución es el proceso mediante el cual se llevan a cabo las instrucciones de un programa en el ordenador.

Durante la ejecución, el sistema operativo carga el archivo ejecutable en la memoria RAM, asigna recursos como CPU y dispositivos de entrada/salida según sea necesario, y comienza a ejecutar las instrucciones del programa en secuencia.

### Práctica 01:
a) Verifica la versión de gcc que tienes instalada en tu ordenador:
```shell
g++ --version
```
b) Mi primer programac en C++:
Escribe un programa que imprima la frase "Hola mundo" en C++ y compilalo:

Escribiendo el programa:
```cpp
//main.cpp
#include <stdio.h>

int main() {
    printf("Hola mundo");
    return 0;
}
```

Compilando el programa:
```shell
g++ main.cpp
```

Ejecutando el programa:
```shell
./a.out
```

Nota: Este programa está escrito al estilo de C pero es compatible con C++.


## Estructura básica de un programa en C++.

```cpp
// Comentario: Inclusión de bibliotecas o cabeceras necesarias
#include <stdio.h>

// Función principal del programa
int main() {
    // Declaración de variables
    int edad;
    
    // Código del programa
    printf("Ingrese su edad: ");
    scanf("%d", &edad);
    printf("Su edad es: %d\n", edad);

    // Indicación de la finalización del programa
    return 0;
}
```

## Declaración de variables y tipos de datos.

En C++, una variable es un espacio reservado en la memoria que se utiliza para almacenar datos. 

```cpp
int main(){
	/*Ejemplos de declaración de variables*/
	int x=0;//se declara una variable de tipo int, de nombre x
	int y(5);//se declara la variable y con valor 5, de tipo int
	char c='c';//se declara una variable de tipo char de nombre c
}
```
### Tipos de datos básicos:

| Tipo de dato | Descripción | Tamaño | Rango de valores |
| --- | --- | --- | --- |
| `bool` | Booleano | 1 byte | Verdadero o falso |
| `char` | Carácter | 1 byte | -128 a 127 |
| `int` | Entero | 4 bytes | -2147483648 a 2147483647 |
| `float` | Flotante | 4 bytes | ±1.8e-38 a ±3.4e38, 6 dígitos de precisión |
| `double` | Doble precisión | 8 bytes | ±2.2e-308 a ±1.8e308, 15 dígitos de precisión |
| `void` | Sin valor | - | - |
| `wchar_t` | Carácter ancho | 2 o 4 bytes | 1 carácter ancho |

### Tipos de datos complejos:
- **Enumerados**: Permiten agrupar constantes simbólicas. Por ejemplo, puedes definir un tipo `dias` con los valores `lunes`, `martes`, etc., y cada uno de estos valores se asocia internamente con un número entero.
- **Matrices**: Permiten almacenar múltiples valores del mismo tipo en una sola variable.
- **Punteros**: Almacenan la dirección de memoria de otra variable.
- **Estructuras**: Permiten agrupar variables

### Modificadores
- **signed**: Las variables con signo pueden almacenar números enteros positivos, negativos y cero1.
- **unsigned**: Las variables sin signo pueden almacenar solo valores enteros no negativos1.
- **short**: Modifica los valores mínimos que puede contener un tipo de datos1.
- **long**: Modifica los valores máximos que puede contener un tipo de datos1.

## Entrada y salida de datos.
### Práctica 02
**Tipos de datos básicos:**

a) Tipo de datos carácter: Ingresa tu nombre y muestralo junto a un mensaje de bienvenida.
``` cpp
#include <stdio.h>

int main() {
    char nombre[50]; 
  
    printf("Por favor, ingresa tu nombre: ");
    scanf("%s", nombre); 
    printf("Hola, %s Bienvenido al curso de C++\n", nombre);

    return 0;
}
```
b) Tipo de datos entero: Ahora vamos a combinar tu nombre con tu edad, ¡ya la ingresaste en el primer programa!
``` cpp
#include <stdio.h>

int main() {
    
    char nombre[50]; 
    int edad;

    printf("Por favor, ingresa tu nombre: ");
    scanf("%s", nombre); 
    printf("Ingresa su edad: ");
    scanf("%d", &edad);
    printf("Hola, %s. Bienvenido al curso de C++. Tu edad es %d \n", nombre, edad);

    return 0;
}
```
c) Usemos un tipo booleano: Cuentame si te gusta el lenguaje C y C++

``` cpp
#include <stdio.h>

int main() {
    
    
    bool me_gusta_c;
    printf("Cuentame: Te gusta el lenguaje C C++\n");
    printf("(1) Si te gusta\n");
    printf("(0) No te  gusta\n");
    scanf("%d", &me_gusta_c);
    printf("(1) te gusta  (0) no te gusta: Tu respuesta --> %d \n", me_gusta_c);

    return 0;
}
```
d) Trabajemos con el tipo flotante: Veamos que tan buen alumno eres, para eso ingresa tus 3 mejores calificaciones.
``` cpp
#include <stdio.h>

int main() {
    float c1, c2, c3, pm; 

  
    printf("Ingresa tu primera mejor calificacion: ");
    scanf("%f", &c1);
    printf("Ingresa tu segunda mejor calificacion: ");
    scanf("%f", &c2);
    printf("Ingresa tu tercera mejor calificacion: ");
    scanf("%f", &c3);
  
    pm = (c1 + c2 + c3) / 3.0;

    printf("El promedio de tus tres mejores calificaciones es: %.2f\n", pm);

    return 0;
}
```
**Tipos de datos complejos:**

e) Uso de una estructura: Mejoremos nuestro ejemplo b a traves del uso de una estructura.
``` cpp
#include <stdio.h>

// Definición de la estructura
struct Estudiante {
    char nombre[50];
    int edad;
};

int main() {
    
    // Declaración de una variable de tipo estructura
    struct Estudiante estudiante;

    printf("Por favor, ingresa tu nombre: ");
    scanf("%49s", estudiante.nombre); 

   
    printf("Por favor, ingresa tu edad: ");
    scanf("%d", &estudiante.edad);

  
    printf("Hola, %s. Bienvenido al curso de C++. Tu edad es %d.\n", estudiante.nombre, estudiante.edad);

    return 0;
}
```
f) Usemos una matriz: Simplifiquemos el ejemplo d asiganando nuestras 3 mejores calificaciones a una variable de tipo matriz.
``` cpp
#include <stdio.h>

int main() {
    float calificaciones[3], pm;

    printf("Ingresa tus tres mejores calificaciones:\n");
    scanf("%f", &calificaciones[0]);
    scanf("%f", &calificaciones[1]);
    scanf("%f", &calificaciones[2]);

    pm = (calificaciones[0] + calificaciones[1] + calificaciones[2]) / 3.0;

    printf("El promedio de tus tres mejores calificaciones es: %.2f\n", pm);

    return 0;
}
```
g) Usando un puntero: Usando un puntero en lugar de un array; la asignación de memoria malloc() y el uso de la libreria stdlib.h los veremos mas detenidamente en el dearrollo del curso.
``` cpp
#include <stdio.h>
#include <stdlib.h>

int main() {

    // Usando un puntero en lugar de un array
    char *nombre; 
    printf("Por favor, ingresa tu nombre: ");
    
    nombre = (char *)malloc(50 * sizeof(char));
    scanf("%s", nombre); 
    printf("Hola, %s. Bienvenido al curso de C++\n", nombre);

    free(nombre);

    return 0;
}
```
h) Enumerado: Definición del tipo de datos enum para representar los días de la semana.
``` cpp
#include <stdio.h>

enum DiasSemana {
    LUNES,
    MARTES,
    MIERCOLES,
    JUEVES,
    VIERNES,
    SABADO,
    DOMINGO
};

int main() {
    
    enum DiasSemana dia; 
    dia = MIERCOLES;
    printf("Hoy es %d\n", dia);
    return 0;

}
```
## Tablas de caracteres y códigos
### secuencias de escape en C

| Secuencia de escape | Significado                       |
|---------------------|-----------------------------------|
| \a                  | Alerta (beep)                     |
| \b                  | Retroceso (backspace)             |
| \f                  | Salto de página (form feed)       |
| \n                  | Nueva línea (newline)             |
| \r                  | Retorno de carro (carriage return)|
| \t                  | Tabulación (horizontal tab)       |
| \v                  | Tabulación vertical (vertical tab)|
| \\                  | Barra invertida (backslash)       |
| \'                  | Apóstrofo o comilla simple       |
| \"                  | Comillas dobles                   |
| \?                  | Signo de interrogación            |
| \0                  | Carácter nulo                     |

### Códigos de formato en la función printf()

| Código de formato | Descripción                               |
|-------------------|-------------------------------------------|
| %d                | Entero con signo decimal                  |
| %i                | Entero con signo decimal                  |
| %u                | Entero sin signo decimal                  |
| %f                | Número de punto flotante                  |
| %c                | Carácter                                   |
| %s                | Cadena de caracteres                       |
| %p                | Puntero                                    |
| %x                | Entero hexadecimal sin signo (minúsculas) |
| %X                | Entero hexadecimal sin signo (mayúsculas) |
| %o                | Entero octal sin signo                    |
| %e                | Notación científica en minúsculas         |
| %E                | Notación científica en mayúsculas         |
| %g                | Elige automáticamente %f o %e             |
| %G                | Elige automáticamente %f o %E             |
| %%                | Imprime un signo de porcentaje literal    |
