# Funciones map, filter y lambda
## Map
Aplica una función sobre todos los elementos de un objeto, que puede ser una lista o un dataframe, entre otros y como resultado se devuelve un iterable de tipo map.

**map()** permite ahorrar el uso de bucles for.

Ejemplos:

1. Disponemos de una función que multiplica por 3

```python
def multiplica(numero):
    return numero * 3

multiplica(14)
```

Supongamos que disponemos de una lista de elementos que han de ser multiplicados, entonces

```python
lista = [2,3,4,5,6,7,8]
map(multiplica,lista) # Map aplica la multiplicación al objeto pasado como parámetro
```

Si quisieramos devolver el resultado en otra lista, utilizamos `list()`

```python
lista = [2,3,4,5,6,7,8]
lista2 = list(map(multiplica,lista))
````

2. En este ejemplo multiplicamos los elementos de 2 listas, utilizando una función `lambda`

```python
a = [1, 2, 3, 4, 5]
b = [6, 7, 8, 9, 10]

lista3 = list(map(lambda x,y : x*y, a,b))
```

## Lambda

Se trata de crear funciones de manera rápida, `just in time`, para acciones requieran de una pequeña operación o comprobación. Toda función lambda puede expresarse como una función convencional pero no a la inversa.

Se utlizan para simplificar el código, pueden tener cualquier numero de argumentos pero solo puede tener una expresión.

Sintaxis: `lambda argumentos: expresión`

Utilizaremos como ejemplo la función multiplicar

```python
def multiplica(numero):
    return numero * 3
```

Vamos a simplificar el código un poco:

```python
def multiplica(numero): return numero * 3
```

Esta notación simple es la que una función lambda intenta replicar, se convierte la función en anónima:

```python
lambda numero: numero*3
```
Para que sea reutilizable podemos guardarla en una variable

```python
portres = lambda numero: numero*3

portres(6)
```

En este ejemplo multiplicamos los elementos de 2 listas, utilizando `lambda` y `map`

```python
a = [1, 2, 3, 4, 5]
b = [6, 7, 8, 9, 10]

lista3 = list(map(lambda x,y : x*y, a,b))
```
## Filter

A partir de una lista o iterador y una función condicional, es capaz de devolver una nueva colección con los elementos filtrados que cumplan la condición.

Tenemos una función que obtiene los pares

```python
def pares(numero):
    if (numero % 2 == 0):
        return numero
```

Ahora disponemos de una lista de números y se quiere disponer una lista solo de números pares

```python
lista = [2, 3, 5, 6, 10,14 , 23, 50, 33]
pares = list(filter(pares, lista)) 
```

list( filter(lambda numero: numero%5 == 0, numeros) )
```