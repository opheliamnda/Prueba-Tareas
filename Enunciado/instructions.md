## Introducción

En tu camino hacia la clase de Introducción a la Programación, decidiste tomar un atajo por una ruta poco transitada. Al avanzar, te topas con un imprevisto. Resulta que el puente sobre el río local se ha derrumbado, bloquéandote el paso.

En la orilla encuentras a un grupo de ponys que se dirigen a Ponyville y se han visto detenidos por el mismo accidente. Al observarlos, notas que poseen distintas habilidades según su tipo y que, si colaboran de manera organizada, podrían construir un paso provisional para que todos logren cruzar.

Los tipos de ponys son:

  - **Pegasos:** Tienen la capacidad de volar. Si el día está despejado, vuelan por su cuenta sin necesidad de un paso (aunque esperan a que todos crucen primero). Sin embargo, si el día está nublado, les da miedo volar y deberán cruzar caminando por el puente.
    
  - **Terrestres:** Poseen una gran fuerza. Cada pony terrestre es capaz de talar **2 árboles** a su alcance para usarlos como pasarela.
    
  - **Unicornios:** Tienen poderes mágicos. No pueden volar a través del río, pero cada unicornio puede mover mediante magia hasta **1 árbol** desde la orilla opuesta para ser utilizado.

Organiza al grupo de ponys para determinar si es posible que los ponys y tu crucen al otro lado.

## Objetivo

El objetivo de esta pregunta es simular el cruce del río de acuerdo a los recursos disponibles y la cantidad de ponys.

- Al cruzar, existirá un grupo que debe **solo puede pasar caminando**. Este grupo esta conformado por los ponys terrestres, los ponys unicornios y tu. Si el día está nublado, los ponys pegasos se suman a este grupo.

- Para lograr que este grupo pase al otro lado, debes organizar a los ponys para traer y talar los árboles. **Cada árbol talado sirve para crear una pasarela provisoria por la que pueden cruzar dos ponys (o un pony y tu)**. Luego que de dos ponys crucen la pasarela se vuelve inestable y no es posible usarla. Notar que pueden cruzar un pony terrestre junto a un unicornio, un unicornio junto a ti, o cualquier combinación de quienes deban cruzar caminando.

- Para recolectar madera, los unicornios deben traer con magia árboles de la otra orilla, pues en el lado en el que estás no hay árboles. **Cada unicornio puede traer como máximo un árbol antes de agotarse**.
  
- Luego, los ponys terrestres deben talar los árboles que hayan traído. **Cada terrestre puede talar como máximo dos árboles antes de agotarse**.

### Input

El programa recibirá como input un _entero_ n, que corresponde a la cantidad de ponys que encuentras. Después, recibirá n _strings_ que corresponderán al tipo de cada pony, el cual puede ser "Terrestre", "Unicornio" o "Pegaso".

Luego, se entregará un _entero_ a, que corresponderá a la cantidad de árboles al otro lado del rio.

Finalmente, el programa recibirá un _booleano_ esta_nublado (que puede ser True o False); indicando si el día esta nublado o no.

### Output

Si no es posible que todos crucen, se deberá imprimir una sola línea especificando la causa (evaluando en este estricto orden):

- Si los árboles disponibles de la otra orilla no alcanzan para todos que todos crucen debe imprimir: "No hay suficientes árboles en el entorno para construir el puente"
- Si faltan unicornios para traer los árboles necesarios de la otra orilla: "¡Debemos llamar a más unicornios!"
- Si faltan ponys terrestres para talar la madera necesaria: "¡Debemos llamar a más terrestres!"

Si es posible que todos crucen, se deben imprimir las siguientes líneas en el orden indicado:
1. "Los unicornios han traído _x_ árboles desde el otro lado para poder cruzar el río", donde _x_ es la cantidad (int) de árboles necesaria a talar para que todos los ponys puedan cruzar (Notar que este número puede ser cero, y no puede ser mayor a la cantidad de árboles dada)
2. "Se han necesitado _n_ ponys unicornios para traer x árboles", donde _n_ es la cantidad de ponys unicornios necesarios para traer los árboles
3. "Los ponys terrestres han talado _x_ árboles para poder cruzar al otro lado del río, obteniendo pasarelas temporales"
5. "Se han necesitado _m_ ponys terrestres para talar _x_ árboles", donde _m_ es la cantidad de ponys terrestres necesarios para talar los árboles
6. "Han cruzado _t_ ponys terrestres", donde _t_ es la cantidad de ponys terrestres
7. "Han cruzado _u_ ponys unicornios", donde _u_ es la cantidad de ponys unicornios
8. "He cruzado el río"
9. Si esta_nublado es False: "Han cruzado _p_ ponys pegasos volando", donde _p_ es la cantidad de ponys pegasos
10. Si esta_nublado es True: "Han cruzado _p_ ponys pegasos caminando"
11. " .𖥔 ݁ ˖ Hemos cruzado gracias al poder de la amistad -` ♡ ´- "

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
False

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
True

```

#### Output
```
¡Debemos llamar a más unicornios!

```
**Explicación:** 

Debido a que los pegasos **no** pueden cruzar volando en este ejemplo, la cantidad de ponys que necesitan cruzar caminando el río es 4 (2 unicornios, 1 terrestre y 1 pegaso), siendo el total 5 al contarte a ti. Por lo tanto, se necesitan 3 árboles, lo cual es posible porque el total es 9. Para traer esos 3 árboles necesitamos 3 unicornios. Para talarlos, 2 terrestres. Como contamos con la cantidad suficiente de árboles, pero no de unicornios y tampoco de terrestres, no es posible que todos crucen el río. Debido al orden de prioridad para evaluar las condiciones de cruce, se debe imprimir que necesitamos más unicornios.


## 

<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/5e356d0b-46f5-4f2d-af66-6551093bd75c" />

