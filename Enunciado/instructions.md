## Introducción

En tu camino hacia la clase de Introducción a la Programación, decidiste tomar un atajo por una ruta poco transitada. Al avanzar, te topas con un imprevisto. Resulta que el puente sobre el río local se ha derrumbado, bloqueándote el paso.

En la orilla encuentras a un grupo de ponys que se dirigen a Ponyville y se han visto detenidos por el mismo accidente. Al observarlos, notas que poseen distintas habilidades según su tipo y que, si colaboran de manera organizada, podrían construir un paso provisional para que todos logren cruzar.

Los tipos de ponys son:

  - **Pegasos:** Tienen la capacidad de volar. Si el día está despejado ("Despejado"), vuelan por su cuenta sin necesidad de un paso (aunque esperan a que todos crucen primero). Sin embargo, si el día está nublado ("Nublado"), les da miedo volar y deberán cruzar caminando por un paso provisorio.
    
  - **Terrestres:** Poseen una gran fuerza. Cada pony terrestre es capaz de talar **2 árboles** a su alcance para usarlos como pasarela.
    
  - **Unicornios:** Tienen poderes mágicos. No pueden volar a través del río, pero cada unicornio puede mover mediante magia hasta **1 árbol** desde la orilla opuesta para ser utilizado.

Organiza al grupo de ponys para determinar si es posible que los ponys y tú crucen al otro lado.

## Objetivo

El objetivo de esta pregunta es simular el cruce del río de acuerdo a los recursos disponibles y la cantidad de ponys.

- Al cruzar, existirá un grupo que **solo puede pasar caminando**. Este grupo está conformado por los ponys terrestres, los ponys unicornios y tú. Si el día está nublado, los ponys pegasos se suman a este grupo.

- Para lograr que este grupo pase al otro lado, debes organizar a los ponys para traer y talar los árboles. **Cada árbol talado sirve para crear una pasarela provisoria por la que pueden cruzar hasta dos integrantes (pueden ser dos ponys, o un pony y tú)**. Luego de que dos integrantes crucen, la pasarela se vuelve inestable y no se puede volver a usar.

- En la orilla actual no hay árboles. Los unicornios deben traer los árboles desde la orilla opuesta usando su magia. **Cada unicornio puede traer como máximo 1 árbol antes de agotarse.**
  
- Luego, los ponys terrestres deben talar los árboles que hayan traído. **Cada terrestre puede talar como máximo dos árboles antes de agotarse**.

_(Nota: En los mensajes de salida se utiliza siempre la palabra "ponys", independientemente de si la cantidad es 1 o mayor)._

### Input

El programa recibirá como input los siguientes datos en orden estricto:
1. Un entero $n$, correspondiente a la cantidad de ponys que encuentras.
2. $n$ strings que corresponderán al tipo de cada pony, los cuales pueden ser "Terrestre", "Unicornio" o "Pegaso".
3. Un entero $a$, correspondiente a la cantidad de árboles al otro lado del río.
4. Un string $clima$, que indica el estado del tiempo y puede ser "Nublado" o "Despejado".

### Output

Si no es posible que todos crucen, se deberá imprimir una sola línea especificando la causa (evaluando en este estricto orden):

- Si los árboles disponibles de la otra orilla no alcanzan para que todos crucen debe imprimir: "No hay suficientes árboles en el entorno para construir el puente"
- Si faltan unicornios para traer los árboles necesarios de la otra orilla: "¡Debemos llamar a más unicornios!"
- Si faltan ponys terrestres para talar la madera necesaria: "¡Debemos llamar a más terrestres!"

Si es posible que todos crucen, se deben imprimir las siguientes líneas en el orden indicado:
1. "Los unicornios han traído _x_ árboles desde el otro lado para poder cruzar el río", donde _x_ es la cantidad (int) de árboles necesaria a talar para que todos los ponys puedan cruzar (Notar que este número puede ser cero, y no puede ser mayor a la cantidad de árboles dada)
2. "Se han necesitado _n_ ponys unicornios para traer x árboles", donde _n_ es la cantidad de ponys unicornios necesarios para traer los árboles
3. "Los ponys terrestres han talado _x_ árboles para poder cruzar al otro lado del río, obteniendo pasarelas temporales"
4. "Se han necesitado _m_ ponys terrestres para talar _x_ árboles", donde _m_ es la cantidad de ponys terrestres necesarios para talar los árboles
5. "Han cruzado _t_ ponys terrestres", donde _t_ es la cantidad de ponys terrestres
6. "Han cruzado _u_ ponys unicornios", donde _u_ es la cantidad de ponys unicornios
7. "He cruzado el río"
8. Si el clima es "Despejado" : "Han cruzado _p_ ponys pegasos volando", donde _p_ es la cantidad de ponys pegasos
9. Si el clima es "Nublado": "Han cruzado _p_ ponys pegasos caminando"
10. " .𖥔 ݁ ˖ Hemos cruzado gracias al poder de la amistad -` ♡ ´- "

## Ejemplo

#### Input
```py
6
Unicornio
Unicornio
Unicornio
Terrestre
Terrestre
Pegaso
10
Despejado

```

#### Output
```
Los unicornios han traído 3 árboles desde el otro lado para poder cruzar el río
Se han necesitado 3 ponys unicornios para traer 3 árboles
Los ponys terrestres han talado 3 árboles para poder cruzar al otro lado del río, obteniendo pasarelas temporales
Se han necesitado 2 ponys terrestres para talar 3 árboles
Han cruzado 2 ponys terrestres
Han cruzado 3 ponys unicornios
He cruzado el río
Han cruzado 1 ponys pegasos volando
 .𖥔 ݁ ˖ Hemos cruzado gracias al poder de la amistad -` ♡ ´- 

```
**Explicación:** 

Debido a que los pegasos pueden cruzar volando en este ejemplo, la cantidad de ponys que necesitan cruzar caminando el río es 5 (2 terrestres y 3 unicornios), siendo el total 6 al contarte a ti. Por lo tanto, se necesitan 3 árboles, lo cual es posible porque el total es 10. Para traer esos 3 árboles necesitamos 3 unicornios. Para talarlos, 2 terrestres. Como contamos con la cantidad suficiente de árboles, unicornios y terrestres, es posible que todos crucen el río gracias al poder de la amistad.

## Ejemplo 2

#### Input
```py
4
Unicornio
Unicornio
Terrestre
Pegaso
9
Nublado

```

#### Output
```
¡Debemos llamar a más unicornios!

```
**Explicación:** 

Debido a que los pegasos **no** pueden cruzar volando en este ejemplo, la cantidad de ponys que necesitan cruzar caminando el río es 4 (2 unicornios, 1 terrestre y 1 pegaso), siendo el total 5 al contarte a ti. Por lo tanto, se necesitan 3 árboles, lo cual es posible porque el total es 9. Para traer esos 3 árboles necesitamos 3 unicornios. Para talarlos, 2 terrestres. Como contamos con la cantidad suficiente de árboles, pero no de unicornios y tampoco de terrestres, no es posible que todos crucen el río. Debido al orden de prioridad para evaluar las condiciones de cruce, se debe imprimir que necesitamos más unicornios.


## 

<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/5e356d0b-46f5-4f2d-af66-6551093bd75c" />

