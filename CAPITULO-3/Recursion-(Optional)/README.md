# Recursión (Opcional)

## ¿Que es la recursión? (Opcional)

>Bienvenido de nuevo. ¿Cómo te sientes depués de la última prueba?

Estamos empezando a aprender algunas cosas bastante interesantes que podríamos hacer con nuestro código. ¿Quién sabía que los bucles pueden ser tan fascinantes?

Ahora que hemos descubierto dos técnicas de bucle que podríamos usar en Python: `bucles while` y `bucles for`.

Utilizamos `bucles while` cuando queremos hacer una operación repetidamente mientras una determinada condición es verdadera. Utilizamos `bucles for` cuando queremos iterar sobre los elementos de una secuencia.

Ahora, vamos a revisar una tercera técnica llamada **`recursión`**. Pero antes de sumergirnos, es posible que hayas notado que esta parte es "opcional". Esto se debe a que si bien la recursión es una técnica muy común utilizada en la ingeniería de software, no se usa tanto en la automatización. Aún asi, pienso que es valioso para nosotros saber acerca de la **`recursión`** y tener una idea de cómo usarla. Puedes verlo en código escrito por otros o puedes enfrentarte a un problema donde la recursión es la mejor manera de resolverlo.

Por lo tanto, mientras que en los próximos apartados estén marcados como opcionales, siguen siendo cosas muy valiosas.

La **`recursión`** es una aplicación repetida del mismo procedimiento a un problema más pequeño.

>¿Alguna vez has jugado con una muñeca rusa de anidación (una matrioshka)?. Son un gran ejemplo visual de recursión. Cada muñeca tiene una muñeca más pequeña dentro de ella. Cuando abres la muñeca para encontrar la más pequeña dentro, sigues avanzando hasta llegar a la muñeca más pequeña que no se puede abrir.

La **`recursión`** nos permite abordar problemas complejos reduciendo el problema a uno más simple.

>Toma nuestras muñecas rusas anidadas, todas anidadas una dentro de la otra. Imagina que queremos saber cuántas muñecas hay en total. Tendrñiamos que abrir cada muñeca una por una hasta l a la última y luego contar cuantas muñecas hemos abierto. Eso es recursión en acción.

Aquí hay otro ejemplo con un problema más complejo. Imagina que estás en una fila de personas y quieres saber cuántas personas están frente a ti. Si la línea es larga podría ser difícil contrar a la gente sin salir de la línea y perder tu lugar. En cambio, puedes preguntarle a la persona que está delante de ti cúantas personas hay delante de ellos. Dado que esta persona estará en la misma situación que tu tendrá que hacerle la misma pregunta a la persona que está delante de ella y así sucesivamente hasta que la pregunta llegue a la primera persona de la línea. Esta persona puede responder con confianza que no hay personas delante de ella. Entonces la segunda persona en la fila puede responder *uno*, la persona detrás de ella *dos*, y así sucesivamente hasta que la respuesta llegue a ti.

**¿Cómo se traduce esto en programación?**

Bueno, en la programación, **la recursión es una forma de hacer una tarea repetitiva haciendo que una función se llame a sí misma.**

Una función recursiva se llama a sí misma generalmente con un parámetro modificado hasta que alcanza una condición específica. Esta condiciñon se denimina **`caso base`**.

>En nuestros ejemplos anteriores, la caja base sería la muñeca rusa más pequeña. o la persona del principio de la cola.

Vamos a ver un ejemplo de función recursiva para entender de lo que estamos hablando.

Aquí, estamos definiendo una función llamada factorial.

```python
def factorial(n):
    if n < 2:
        return 1
    return n * factorial(n-1)
```
Al comienzo de la función, tenemos un bloque condicional que define el caso base (`if n < 2:`) donde n es menor que 2. Simplemente devuelve el valor 1 (`return 1`). Despues del caso base, tenemos una línea donde la función factorial se llama a sí misma con n menos 1 (`return n * factorial(n-1)`). Esto se denomina **caso recursivo**. Esto crea un bucle.

Cada vez que se ejecuta la función, se llama a sí misma con un número menor hasta que llega al caso base. Una vez que llega al caso base, devuelve el valor 1. Luego, la función previamente llamada multiplica eso por dos y la funciñon previamente llamada la multiplica por tres y así sucesivamente.

Este bucle continuará hasta que la primera función factorial llamada devuelva el resultado deseado. Es un poco complejo.

Vamos a añadir algunas declaraciones de impresión para ver exactamente cómo funciona esto.

```python
def factorial(n):
    print("Factorial called with " + str(n))
    if n < 2:
        print("Returning 1")
        return 1
    result = n * factorial(n-1)
    print("Returning " + str(result) + " for factorial of " + str(n))
    return result

factorial(4)
```

<details><summary>Resultado</summary>
<p>
```
Factorial called with 4
Factorial called with 3
Factorial called with 2
Factorial called with 1
Returning 1
Returning 2 for factorial of 2
Returning 6 for factorial of 3
Returning 24 for factorial of 4
```
</p>
</details>