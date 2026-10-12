# Laboratorio 5

Este repositorio contiene una serie de ejercicios desarrollados en C# con el objetivo de practicar y reforzar conceptos fundamentales de programación orientada a objetos, estructuras de datos, métodos, recursividad y generación de datos aleatorios. Cada problema aborda una temática diferente y permite comprender cómo aplicar estos conceptos mediante ejemplos prácticos y la ejecución de instrucciones en consola.

## 1. Diccionario de datos y generación dinámica de consultas SQL

### Descripción
En este ejercicio se implementa un diccionario utilizando la estructura `Dictionary<string, object>` para almacenar información relacionada con un producto de inventario. Los datos registrados incluyen el nombre del producto, su precio y la cantidad disponible.

A partir de la información almacenada, el programa recorre las claves del diccionario para generar dinámicamente una cláusula `SET` y construir una cadena SQL destinada a representar una operación de inserción de datos en una tabla llamada `productos`.

<img width="1894" height="984" alt="image" src="https://github.com/user-attachments/assets/486e17c5-76c4-4f37-bd6b-27178180d345" />


### Conceptos aplicados
- **Diccionarios (`Dictionary<TKey, TValue>`):** permiten almacenar información mediante pares de clave y valor, facilitando el acceso a los datos mediante identificadores.
- **Tipos de datos:** se utiliza `string` para representar el nombre del producto, `decimal` para el precio y `int` para la cantidad.
- **Colecciones dinámicas:** se emplea `List<string>` para almacenar los elementos que posteriormente conforman la cláusula `SET`.
- **Ciclo `foreach`:** permite recorrer las claves del diccionario y generar las asignaciones correspondientes.
- **Métodos de cadenas:** se utiliza `string.Join()` para unir los elementos de una colección y formar fragmentos de texto.
- **Interpolación de cadenas:** permite construir mensajes y sentencias SQL de manera dinámica.

### Funcionamiento
El programa crea un diccionario con los datos de una laptop HP Envy, cuyo precio es de 850.99 y cuya cantidad disponible es de 15 unidades. Posteriormente, recorre las claves almacenadas y genera una representación de las asignaciones correspondientes a cada campo.

Finalmente, construye e imprime una cadena SQL utilizando los nombres de las claves como columnas y como marcadores de parámetros.

Este ejercicio permite comprender cómo las estructuras de datos pueden facilitar la organización de información y la generación dinámica de instrucciones para trabajar con bases de datos.

**Nota técnica:** la sentencia SQL del código original contiene un error de sintaxis en la construcción del `INSERT`: falta cerrar correctamente la lista de columnas antes de `VALUES`. Además, los marcadores de parámetros deben asociarse a sus valores al ejecutar la consulta. Para una implementación real, se recomienda utilizar consultas parametrizadas mediante una biblioteca de acceso a datos, evitando concatenar directamente valores en las sentencias SQL.

## 2. Cálculo del factorial mediante recursividad

### Descripción
Este ejercicio desarrolla un programa capaz de calcular y mostrar el factorial de los números enteros comprendidos entre 0 y 10. Para realizar los cálculos, se implementa un método recursivo denominado `Factorial`, que recibe un número como argumento y devuelve su factorial.

El programa utiliza un ciclo `for` para recorrer los valores del intervalo establecido y llamar al método recursivo en cada iteración.

### Conceptos aplicados
- **Métodos:** permiten encapsular una operación específica y reutilizarla en diferentes partes del programa.
- **Recursividad:** consiste en que un método se invoque a sí mismo para resolver un problema mediante versiones más pequeñas del mismo.
- **Caso base:** establece la condición que detiene las llamadas recursivas.
- **Parámetros y valores de retorno:** el método recibe un número y devuelve el resultado de su cálculo.
- **Ciclo `for`:** permite recorrer los números desde 0 hasta 10.
- **Tipo de dato `long`:** se utiliza para almacenar los valores enteros calculados.
- **Salida por consola:** presenta los resultados de cada operación.

### Funcionamiento
El programa recorre los números del 0 al 10 e invoca al método `Factorial` para calcular el resultado de cada uno.

El método utiliza un caso base: cuando el número es menor o igual que 1, devuelve 1. En caso contrario, multiplica el número actual por el resultado de llamar nuevamente al método con el número inmediatamente anterior.

Por ejemplo, el factorial de 5 se calcula de la siguiente manera:

`5! = 5 × 4 × 3 × 2 × 1 = 120`

El resultado se muestra en consola junto con el número correspondiente, utilizando un formato que permite identificar fácilmente cada operación.
<img width="1833" height="676" alt="image" src="https://github.com/user-attachments/assets/c6ff6a32-185d-4005-af49-a1fce418744f" />



Este ejercicio permite comprender la estructura de una función recursiva, la importancia del caso base y la relación entre las llamadas sucesivas de un método.

## 3. Sobrecarga de métodos

### Descripción
En este ejercicio se implementa una clase denominada `SobreCarga`, que contiene dos métodos con el mismo nombre: `Cuadrado`. Ambos métodos realizan la misma operación matemática, calcular el cuadrado de un número, pero reciben parámetros de diferentes tipos.

El primer método acepta un valor de tipo `int` y devuelve un resultado entero. El segundo recibe un valor de tipo `double` y devuelve un resultado decimal.

### Conceptos aplicados
- **Clases y métodos:** se organiza el comportamiento del programa dentro de una clase.
- **Sobrecarga de métodos (Method Overloading):** permite definir varios métodos con el mismo nombre siempre que sus listas de parámetros sean diferentes.
- **Tipos de datos:** se utilizan `int` y `double` para trabajar con números enteros y decimales.
- **Valores de retorno:** cada método devuelve el cuadrado del valor recibido.
- **Selección de métodos:** el compilador determina qué versión del método debe ejecutarse según el tipo del argumento proporcionado.
- **Mensajes por consola:** permiten observar qué versión del método fue invocada y cuál fue el resultado obtenido.

### Funcionamiento
La clase contiene un método denominado `ProbarMetodosSobreCargados()`, que ejecuta dos pruebas. En la primera, llama a `Cuadrado(7)`, utilizando la versión que recibe un entero. En la segunda, llama a `Cuadrado(7.5)`, utilizando la versión que recibe un número decimal.

Cada método muestra un mensaje indicando el tipo de argumento recibido y devuelve el resultado de multiplicar el valor por sí mismo.

Los resultados esperados son:

- Cuadrado de 7: `49`
- Cuadrado de 7.5: `56.25`

Este ejercicio demuestra cómo la sobrecarga de métodos permite mantener nombres descriptivos y reutilizar una misma operación lógica con diferentes tipos de datos, mejorando la organización y legibilidad del código.

## 4. Simulación de lanzamientos de un dado y registro de frecuencias

### Descripción
Este ejercicio consiste en simular 6,000 lanzamientos de un dado de seis caras mediante la generación de números aleatorios. El objetivo es contabilizar cuántas veces aparece cada una de las seis caras y presentar los resultados en una tabla por consola.
<img width="1900" height="871" alt="image" src="https://github.com/user-attachments/assets/620f6900-1759-4592-a87a-23c8852d5dee" />


Aunque el ejercicio está identificado como un problema de recursividad, el código implementado utiliza principalmente ciclos, estructuras de selección y contadores para realizar la simulación.

### Conceptos aplicados
- **Generación de números aleatorios:** se utiliza la clase `Random` para simular los resultados de los lanzamientos.
- **Ciclo `for`:** ejecuta el proceso de simulación un total de 6,000 veces.
- **Estructura `switch`:** identifica el resultado de cada lanzamiento y dirige la ejecución hacia el contador correspondiente.
- **Contadores:** se utilizan seis variables enteras, desde `frecuencia1` hasta `frecuencia6`, para registrar la cantidad de apariciones de cada cara.
- **Operador de incremento (`++`):** aumenta en una unidad el contador asociado al resultado obtenido.
- **Estructuras de control:** permiten repetir las operaciones y tomar decisiones según el valor generado.
- **Formato de salida:** organiza los resultados en una tabla que relaciona cada cara con su frecuencia.

### Funcionamiento
Al iniciar el programa, se crea un objeto de la clase `Random` y se inicializan en cero los seis contadores de frecuencia.

A continuación, el ciclo `for` ejecuta 6,000 iteraciones. En cada iteración, se genera un número aleatorio mediante `numerosAleatorios.Next(1, 7)`, que puede producir valores enteros desde 1 hasta 6, ya que el límite superior no está incluido.

El resultado se almacena en la variable `cara` y se evalúa mediante una estructura `switch`. Dependiendo del número obtenido, se incrementa el contador correspondiente.

Una vez finalizados todos los lanzamientos, el programa imprime una tabla con dos columnas: la cara del dado y la cantidad de veces que apareció durante la simulación.

Las frecuencias obtenidas pueden variar en cada ejecución, debido a la naturaleza aleatoria de los lanzamientos. Sin embargo, al aumentar el número de simulaciones, las frecuencias relativas suelen aproximarse a una sexta parte del total para cada cara, aunque no tienen que ser exactamente iguales.

Este ejercicio permite practicar la simulación de eventos aleatorios, el uso de contadores y la recopilación de resultados para analizar el comportamiento de un proceso repetitivo.

**Aclaración:** el código presentado no implementa recursividad, porque no existe una llamada de un método a sí mismo. Su enfoque principal es la simulación mediante iteraciones. Por ello, puede describirse con mayor precisión como un ejercicio de generación de números aleatorios y conteo de frecuencias.

## Conclusión

Los cuatro ejercicios permiten reforzar diferentes fundamentos de la programación en C#. A través de ellos se practica el almacenamiento de información mediante diccionarios, la construcción dinámica de cadenas, el uso de métodos recursivos, la sobrecarga de métodos y la simulación de eventos aleatorios.

En conjunto, estas actividades contribuyen al desarrollo del razonamiento lógico, la comprensión de las estructuras de control y la capacidad de dividir los problemas en operaciones más pequeñas y manejables. También permiten reconocer la importancia de utilizar correctamente los tipos de datos, organizar el código en métodos y verificar que las instrucciones produzcan los resultados esperados.
