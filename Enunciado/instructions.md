## Introducción

En este apartado se espera que escribas una breve introducción a la pregunta, explicando de qué se trata a grandes rasgos. También puedes incluir un pequeño 'lore' asociado a la pregunta.

En tu camino hacia la clase de Introducción a la Programación, decidiste tomar un atajo por una ruta poco transitada. Al avanzar, te topas con un imprevisto. Resulta que el puente sobre el río local se ha derrumbado, bloquéandote el paso.

En la orilla encuentras a un grupo de ponys que se dirigen a Ponyville y se han visto detenidos por el mismo accidente. Al observarlos, notas que poseen distintas habilidades según su tipo y que, si colaboran de manera organizada, podrían construir un paso provisional para que todos logren cruzar.

Los tipos de ponys son:

  - **Pegasos:** Tienen la capacidad de volar. Si el día está despejado, vuelan por su cuenta sin necesidad de un paso (aunque esperan a que todos crucen primero). Sin embargo, si el día está nublado, les da miedo volar y deberán cruzar caminando por el puente.
    
  - **Terrestres:** Poseen una gran fuerza. Cada pony terrestre es capaz de talar **2 árboles** a su alcance para usarlos como pasarela.
    
  - **Unicornios:** Tienen poderes mágicos. No pueden volar a través del río, pero cada unicornio puede mover mediante magia hasta **1 árbol** desde la orilla opuesta para ser utilizado.

Organiza al grupo de ponys para determinar si es posible que los ponys y tu crucen al otro lado.

## Objetivo

Acá se debe explicar que hay que hacer en la pregunta, si un alumno leyese este apartado debería poder realizar un código que entregue el mismo output que el código solución a partir de un input dado. Es importante que no se den instrucciones tan explícitas, solo lo esencial para poder desarrollar la pregunta. Es muy importante que los alumnos tengan que idear por su cuenta como llegar a una solución al problema.

El objetivo de esta pregunta es simular el cruce del río de acuerdo a los recursos disponibles y la cantidad de ponys.

- Al cruzar, existirá un grupo que debe **solo puede pasar caminando**. Este grupo esta conformado por los ponys terrestres, los ponys unicornios y tu. Si el día está nublado, los ponys pegasos se suman a este grupo.

- Para lograr que este grupo pase al otro lado, debes organizar a los ponys para traer y talar los árboles. **Cada árbol talado sirve para crear una pasarela provisoria por la que pueden cruzar dos ponys**. Luego que de dos ponys crucen la pasarela se vuelve inestable y no es posible usarla.

- Para recolectar madera, los unicornios deben traer con magia árboles de la otra orilla, pues en el lado en el que estás los árboles son poco firmes y no sirven para el proceso. **Cada unicornio puede traer como máximo un árbol antes de agotarse**.
  
- Luego, los ponys terrestres deben talar los árboles que hayan traído. **Cada terrestre puede talar como máximo dos árboles antes de agotarse**.

### Input

El programa recibirá como input un _entero_ n, que corresponde a la cantidad de ponys que encuentras. Después, recibirá n _strings_ que corresponderán al tipo de cada pony, el cual puede ser "Terrestre", "Unicornio" o "Pegaso".

Luego, se entregará un _entero_ a, que corresponderá a la cantidad de árboles al otro lado del rio.

Finalmente, el programa recibirá un _booleano_ esta_nublado (que puede ser True o False); indicando si el día esta nublado o no.

### Output

Si no es posible que todos crucen, se deberá imprimir una sola línea especificando la causa (evaluando en este estricto orden):

- Si los árboles disponibles de la otra orilla no alcanzan para todos que todos crucen debe imprimir: "No hay suficientes árboles en el entorno para construir el puente"
-  Si faltan unicornios para traer los árboles necesarios de la otra orilla: "Llamando a un pony unicornio"
- Si faltan ponys terrestres para talar la madera necesaria: "Llamando a un pony terrestre"

Si es posible que todos crucen, se deben imprimir las siguientes líneas en el orden indicado:
1. "Los ponys terrestres han talado x árboles para poder cruzar al otro lado del río", donde x es la cantidad de árboles necesaria a talar para que todos los ponys puedan cruzar (Notar que este número puede ser cero, y no puede ser mayor a la cantidad de árboles dada)
2. "Se han necesitado _ ponys unicornios para traer x árboles desde el otro lado del río"
3. "Se han necesitado _ ponys terrestres para talar x árboles desde el otro lado del río"
4. "Han cruzado t ponys terrestres", donde t es la cantidad de ponys terrestres
5. "Han cruzado u ponys unicornios", donde u es la cantidad de ponys unicornios
6. "He cruzado el río"
7. Si esta_nublado es False: "Han cruzado p ponys pegasos volando", donde p es la cantidad de ponys pegasos
8. Si esta_nublado es True: "Han cruzado p ponys pegasos por el puente"

## Ejemplo

Acá se debe poner un ejemplo de input y el output esperado para dicho input, junto con una breve explicación de por qué se llega a ese output.

#### Input
```py

```

#### Output
```

```
**Explicación:** 

<img width="3840" height="2160" alt="image" src="https://github.com/user-attachments/assets/72a9c02c-de83-4300-9cb0-be6ffe7d25a8" />
