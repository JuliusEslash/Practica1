# Practica1
Practica 1 de listas
[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/zQRHq8rg)

# Práctica 2: Pilas

#### Introducción

El objetivo de esta práctica fue implementar las funcionalidades de conversión de expresiones de notación infija a posfija y la evaluación de expresiones posfijas utilizando C++. Para esto, se desarrolló un archivo de cabecera llamado posfija.h que contiene las funciones in2pos y evaluar.

#### Descripción de la implementación de posfija.h

El archivo posfija.h contiene dos funciones principales: in2pos y evaluar.

##### Función in2pos

La función in2pos convierte una expresión en notación infija a notación posfija. Para lograr esto, se implementó un algoritmo que recorre la expresión infija y utiliza una pila de operadores para reorganizar los tokens de la expresión en notación posfija.

- *Paso a paso:*
  1. Crear una pila pilaops para guardar los operadores. 
  2. Inicializar un string vacío salida para almacenar la expresión posfija resultante.![Powtoon_GIF](https://github.com/AGN-Teaching/practica-2-pilas-brizavda/assets/141947806/197c5ebc-d25e-47b1-b2c6-b524f116f049)

  3. Recorrer los tokens de la expresión infija.![Powtoon_GIF (1)](https://github.com/AGN-Teaching/practica-2-pilas-brizavda/assets/141947806/ba0da8f9-f206-44f4-8cfe-6bc6c4cc9bd0)

  4. Si el token es un operando (número o variable), se agrega al final del string salida.
  5. Si el token es un paréntesis izquierdo, se coloca en la pila pilaops.
  6. Si el token es un paréntesis derecho, se sacan los operadores de la pila hasta encontrar el paréntesis izquierdo y se agregan al string salida.
  7. Si el token es un operador, se compara su precedencia con los operadores en la pila. Se sacan operadores de la pila con igual o mayor precedencia y se agregan al string salida. Luego, se coloca el operador actual en la pila.![Powtoon_GIF (2)](https://github.com/AGN-Teaching/practica-2-pilas-brizavda/assets/141947806/97d14afc-7ce2-48fb-9195-435e59307c93)
![Powtoon_GIF (3)](https://github.com/AGN-Teaching/practica-2-pilas-brizavda/assets/141947806/893bb817-a67a-4319-9404-08f4295d9485)
![Powtoon_GIF (4)](https://github.com/AGN-Teaching/practica-2-pilas-brizavda/assets/141947806/cf1e8ec1-60bd-4ba7-97fc-43fc260c6272)
![Powtoon_GIF (5)](https://github.com/AGN-Teaching/practica-2-pilas-brizavda/assets/141947806/4ced01ff-1084-4665-9a34-5f492409c7f5)

  8. Al final, se vacía la pila de operadores, agregando los operadores restantes al string salida.
  9. La función retorna la expresión en notación posfija.
![Powtoon_GIF (6)](https://github.com/AGN-Teaching/practica-2-pilas-brizavda/assets/141947806/afe5610f-5c1e-4b42-a5ca-01379ab0083b)

##### Función evaluar

La función evaluar toma una expresión en notación posfija y calcula su resultado utilizando una pila de operandos para realizar las operaciones correspondientes.

- *Paso a paso:*
  1. Crear una pila pilaoperandos para guardar los operandos.
  2. Recorrer los tokens de la expresión posfija.![Powtoon_GIF (7)](https://github.com/AGN-Teaching/practica-2-pilas-brizavda/assets/141947806/4ff343e7-de3c-4f17-ab4b-14cc95bab816)

  3. Si el token es un dígito, se convierte a su valor numérico y se agrega como operando a la pila.
  4. Si el token es un operador, se extraen los dos operandos más recientes de la pila y se realiza la operación correspondiente.
  5. El resultado se vuelve a agregar a la pila como nuevo operando.![Powtoon_GIF (8)](https://github.com/AGN-Teaching/practica-2-pilas-brizavda/assets/141947806/f0b62e3c-6c91-4ee9-8fe7-721be324ac30)
![Powtoon_GIF (9)](https://github.com/AGN-Teaching/practica-2-pilas-brizavda/assets/141947806/65cbd81c-cbac-497e-ae80-0f9836eb37f1)
![Powtoon_GIF (10)](https://github.com/AGN-Teaching/practica-2-pilas-brizavda/assets/141947806/1fb82f0f-f94f-4a71-9f39-6b49357b4959)
![Powtoon_GIF (11)](https://github.com/AGN-Teaching/practica-2-pilas-brizavda/assets/141947806/0f4387be-2bc2-41ba-817e-07d42282d4d3)
![Powtoon_GIF (12)](https://github.com/AGN-Teaching/practica-2-pilas-brizavda/assets/141947806/2486eed4-5dfb-4b21-860b-8bba74f4ed21)

  6. Al finalizar el recorrido de la expresión, se obtiene el resultado final de la pila, que representa el resultado de la expresión posfija.

#### Análisis del trabajo realizado

La implementación de posfija.h permitió convertir expresiones infijas a posfijas y evaluar estas últimas de manera eficiente y precisa. El uso de estructuras de datos como pilas resultó fundamental para el manejo de operadores y operandos en ambos procesos.

**Implementación de la conversión de infija a posfija (in2pos):**

1. *Uso de pilas:* Se utilizó una pila para almacenar temporalmente los operadores mientras se manipulaba la expresión infija. Esta estructura de datos resulta crucial para mantener el orden de precedencia de los operadores.

2. *Manejo de paréntesis:* Los paréntesis en una expresión infija afectan el orden de las operaciones. La implementación recorre la expresión infija y maneja adecuadamente los paréntesis, sacando los operadores de la pila hasta encontrar su correspondiente paréntesis izquierdo.

3. *Precedencia de operadores:* Se usaron condiciones que determinaban cuándo sacar operadores de la pila basándose en su precedencia. Esto se hizo mediante bucles y comprobaciones de condiciones lógicas que garantizan la coherencia en el orden de los operadores.

La estrategia utilizada consiste en recorrer la expresión infija carácter por carácter y procesar cada uno según sea un operando, paréntesis o un operador. Se garantiza que la conversión a posfija mantenga la integridad de la expresión original.
El algoritmo empleado para la conversión de notación infija a posfija aprovechó el uso de pilas para organizar los operadores según su precedencia y así obtener la expresión posfija equivalente.

**Implementación de la evaluación de expresión posfija (evaluar):**

1. *Uso de pilas para operandos:* Se utilizó una pila para almacenar temporalmente los operandos mientras se evaluaba la expresión posfija. Esta estructura de datos permite evaluar la expresión siguiendo el orden correcto de las operaciones.

2. *Manejo de operandos y operadores:* Se iteró a través de la expresión posfija, manejando los operandos y operadores. Cuando se encontraba un operador, se aplicaba la operación correspondiente utilizando los operandos previamente almacenados en la pila.

3. *Evaluación coherente:* La implementación garantiza que se evalúe la expresión posfija de manera coherente, siguiendo las reglas de precedencia de operadores y manteniendo el orden correcto de las operaciones.

La función evaluar operó de manera eficiente, utilizando la pila de operandos para calcular el resultado de la expresión posfija con las operaciones correspondientes.

En resumen, el trabajo se estructuró siguiendo las reglas fundamentales de las expresiones infijas y posfijas, aprovechando las propiedades de las pilas para mantener y manipular los elementos de manera adecuada. Las decisiones en la implementación se basaron en la lógica de las operaciones aritméticas para garantizar la precisión en la conversión y evaluación de las expresiones.

#### Conclusiones

 La práctica permitió comprender la importancia de las pilas como estructuras de datos fundamentales en informática. Su capacidad para almacenar y recuperar datos de manera eficiente, especialmente en operaciones LIFO (Last In, First Out), es esencial en múltiples aplicaciones. La correcta implementación de algoritmos permitió realizar conversiones y evaluaciones de expresiones de manera eficiente y precisa.

El uso de pilas simplificó el manejo de operadores y operandos, facilitando el proceso de conversión y evaluación de expresiones matemáticas, demostrando su relevancia en la resolución de problemas computacionales. Se observó la versatilidad de las pilas en términos de su aplicación en diversos contextos. Además de las aplicaciones directas, su estructura y operaciones pueden adaptarse a una variedad de problemas y escenarios, lo que subraya su importancia en la resolución de problemas informáticos.

En resumen, la práctica proporcionó una sólida comprensión del concepto de pilas y cómo sus operaciones pueden emplearse para resolver problemas, destacando su importancia en la estructura y gestión de datos en informática.

#### Nota: 
Por favor si los gifs no cargan comuniquese conmigo para enviarle la liga de estos mismo y pueda visualizarlos.
