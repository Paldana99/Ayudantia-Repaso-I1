# Repaso I1

- Variables
- Operadores
- Control de Flujo
  - If, else
  - For
  - While
- Funciones
- String


```python
print("Hola mundo!")
```

    Hola mundo!


# Variables
## Tipos de variable
Distintos tipos de variable:
### INT
Números enteros
### Float
Números decimales
### Str
String, texto. Siempre entre comillas dobles o simples.
### Booleanos
Asignar Verdad o Falso: `True` o `False`


```python
print(type(1))
print(type(1.0))
print(type("Un string"))
print(type('Otro string'))
print(type(True))
```

    <class 'int'>
    <class 'float'>
    <class 'str'>
    <class 'str'>
    <class 'bool'>


## Operaciones basicas
Suma:


```python
1 + 2
```




    3



Resta


```python
1 - 2
```




    -1



Multiplicacion



```python
10 * 5
```




    50



División


```python
20/3
```




    6.666666666666667



División entera


```python
20//3
```




    6



Exponente


```python
2**8
```




    256



Modulo


```python
10%3
```




    1



Ejemplo:
Obtener las primeras tres cifras del numero: `167 980`


```python
167980//1000
```




    167



O las ultimas dos cifras


```python
167980%100
```




    80



## Operaciones booleanas


```python
print(1 == 2)
print(1 == "2")
print("1" == "1")
print("Uno" == "Dos")
```

    False
    False
    True
    False



```python
print(1 != 2)
print(1 != "2")
print("1" != "1")
print("Uno" != "Dos")
```

    True
    True
    False
    True



```python
print(1 < 2)
print(1 > 2)
print(1 <= 2)
print(1 >= 2)
```

    True
    False
    True
    False



```python
print(True and False)
print(True or False)
print(not True)
print(not False)
```

    False
    True
    False
    True


## Operaciones sobre string


```python
"Hola" + "Mundo"
```




    'HolaMundo'




```python
"Hola"*3
```




    'HolaHolaHola'



Podemos utilizar parentesis para ordenar!


```python
print((True and False) or (not False))
```

    True


## Definir Variables


```python
nombre = "Intro "
prueba = "i1 "
nota = 7
print(nombre + prueba + str(nota))
```

    Intro i1 7


## Input
Para pedirle al usuario que ingrese un mensaje. Este va a ser un string


```python
nombre = input()
print("Hola " + nombre)
```

     Diego


    Hola Diego


# Control de Flujo

## If/else
Si cumple la condicion, entonces entra en el if

En caso contrario, entra en el else


```python
numero = 4
# Si es par
if numero % 2 == 0:
    print("par")
else:
    print("impar")
```

    par



```python
numero = 4
# Si es impar
if numero % 2 != 0:
    print("impar")
else:
    print("par")
```

    par


## If/elif/else
Entra en la primera condicion que encuentre. Y deja de ejecutarse!


```python
nombre = "Pablo"
if nombre == "Juan":
    print("Hola Juan!")
elif nombre == "Pablo" or "Diego":
    print("Hola Pablo o Diego")
elif nombre == "Pablo":
    print("Hola Pablo")
else:
    print("No saludo a extraños")
```

    Hola Pablo o Diego


## While
Itera hasta que la condicion se haga `False`


```python
contador = 0
while contador < 5:
    print("El contador va en: " + str(contador))
    contador += 1

```

    El contador va en: 0
    El contador va en: 1
    El contador va en: 2
    El contador va en: 3
    El contador va en: 4


Muy util cuando no sabemos cuantas veces tendremos que iterar!


```python
mensaje = input()
while mensaje != "STOP":
    print("El mensaje es:" + mensaje)
    if mensaje == "Sigue":
        print("Vamos a seguir!")
    mensaje = input()
```

     mensaje


    El mensaje es:mensaje


     Sigue


    El mensaje es:Sigue
    Vamos a seguir!


     vamos


    El mensaje es:vamos


     sigue


    El mensaje es:sigue


     STOP


## For
Itera dentro de un rango. 
`range(a, b)` permite definir un rango desde `a` hasta `b-1`


```python
maximo = 4
for iterador in range(0, maximo):
    print("Paso: " + str(iterador))
```

    Paso: 0
    Paso: 1
    Paso: 2
    Paso: 3



```python
for i in range(3, 7):
    print("Paso: " + str(i))
```

    Paso: 3
    Paso: 4
    Paso: 5
    Paso: 6


# Funciones

Una funcion puede recibir parametros o ninguno, y retornar algo o nada (None)

## Funciones built-in


```python
# Imprimir un mensaje en la consola, separados por espacios
print("Hola mundo", 1, True, 3)

# Recibir un texto desde la consola
texto = input() # Parámetro: (), Retorna: texto

# Convertir un número a string
numero = str(123) # Parámetro: (número), Retorna: "123"
print(type(numero))

# Convertir un string a número
numero = int("123") # Parámetro: (string), Retorna: 123
print(type(numero))

# Crear un rango de números
rango = range(10) # Parámetro: (fin), Retorna: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

# Crear un rango desde 3 hasta 10
rango = range(3, 11) # Parámetros: (inicio, fin), Retorna: [3, 4, 5, 6, 7, 8, 9, 10]
```

    Hola mundo 1 True 3


     Texto


    <class 'str'>
    <class 'int'>


### Modulos adicionales

Modulo random

randint recibe dos enteros a, b y genera un numero entero entre a y b inclusive



```python
import random

for i in range(0, 5):
    numero = random.randint(0, 5)
    print(numero)
```

    1
    4
    5
    0
    1


Modulo math
Util para operaciones matematicas complejas

sqrt efectua la raiz cuadrada de un numero, y retorna un float


```python
import math

raiz = math.sqrt(16)
print(raiz)
```

    4.0


## Funciones externas
Tambien podemos utilizar funciones creadas por otros que se encuentren en otro archivo.
Por ejemplo si tengo un archivo `funciones_secretas.py` que contiene la funcion secreta: `mi_secreto(nombre)`
Puedo utilizarla tal que:


```python
import funciones_secretas

nombre = input()
a = funciones_secretas.mi_secreto(nombre)
```

## Definir nuestra funciones
Queremos definir nuestras propias funciones!


```python
def mi_funcion(mensaje):
    print("Mi propia funcion, con un mensaje especial:", mensaje)
```


```python
mi_funcion("por fin logre crear una funcion!")
mi_funcion("Que feliz estoy!")
```

    Mi propia funcion, con un mensaje especial: por fin logre crear una funcion!
    Mi propia funcion, con un mensaje especial: Que feliz estoy!



```python
def es_par(numero):
    if numero%2 == 0:
        return True
    else:
        return False
```


```python
print(es_par(10))
print(es_par(323))
```

    True
    False


Cuidado con las variables locales y globales.
Dentro de una funcion estas variables solo existen en la funcion!


```python
variable_global = 0
def juego_de_variable():
    variable_local = 100
    print("La variable local dentro de la funcion ", variable_local)
    variable_global = 10
    print("La variable global dentro de la funcion", variable_global)
juego_de_variable()
print("La variable global fuera de la funcion ", variable_global)
```

    La variable local dentro de la funcion  100
    La variable global dentro de la funcion 10
    La variable global fuera de la funcion  0


La variable local dejo de existir!


```python
print(variable_local)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[5], line 1
    ----> 1 print(variable_local)


    NameError: name 'variable_local' is not defined


## Funcion round
Permite redondear un numero decimal, segun la cantidad de decimales


```python
numero = 1.356671
redondeo = round(numero, 3)
print(redondeo)

redondeo = round(numero, 1)
print(redondeo)

redondeo = round(numero, 5)
print(redondeo)
```

    1.357
    1.4
    1.35667


# String

# Len
Permite saber el largo de un string


```python
largo = len("Que tan larga sera esta frase?")
print(largo)
```

    30


## Indexacion

Podemos acceder a un caracter de un string segun su posicion.
Estas comienzan en 0 hasta len(string) - 1

O podemos indexar con negativos, para hacerlo en sentido contrario

O darle un rango de posiciones


```python
mi_string = "Un string muy especial"
print(mi_string[0])
print(mi_string[3])
print(mi_string[len(mi_string)-1])
print(mi_string[-1])
print(mi_string[-2])
print(mi_string[3:9])
```

    U
    s
    l
    l
    a
    string


## Iterar en string

Usando su posicion numerica:


```python
mi_string = "Hola a todos!"
for index in range(0, len(mi_string)):
    print(mi_string[index])
```

    H
    o
    l
    a
     
    a
     
    t
    o
    d
    o
    s
    !


O iterando directamente los caracteres:


```python
for caracter in mi_string:
    print(caracter)
```

    H
    o
    l
    a
     
    a
     
    t
    o
    d
    o
    s
    !


## Substring


```python
mi_string = "Tengo un string que representa a todos"
esta = "todos" in mi_string
print(esta)
# Las mayusculas importan!
esta = "Representa" in mi_string
print(esta)
```

    True
    False


## Inmutabilidad
Los string son inmutables! No podemos cambiar un caracter en una posicion!


```python
s = "Holo"
s[3] = "a"
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Cell In[72], line 2
          1 s = "Holo"
    ----> 2 s[3] = "a"


    TypeError: 'str' object does not support item assignment


Tendremos que crear un nuego string e ingeniarnos alguna forma


```python
nuevo = s[0:3] + "a"
print(nuevo)
```

    Hola


## Metodos de string
Los metodos son funciones que se aplican a ciertos objetos.
### Upper
- upper() transforma a mayusculas
- isupper() retorna True si todos los caracteres esnta en mayusculas, caso contrario retorna False


```python
string = "quiero gritar!"
print(string.isupper())
string_upper = string.upper()
print(string_upper)
print(string_upper.isupper())
```

    False
    QUIERO GRITAR!
    True



```python
string_bizarro = "MAYUSCULAS CON 123NUMEROS?"
print(string_bizarro.isupper())
```

    True


### Lower
- lower() transforma a minusculas
- islower() retorna True si todos los caracteres estan en minusculas, caso contrario retorna False


```python
string = "QUIERO DEJAR DE GRITAR"
print(string.islower())
string_lower = string.lower()
print(string_lower)
print(string_lower.islower())
```

    False
    quiero dejar de gritar
    True


## verificar digitos
- Queremos ver si un string tiene solo digitos


```python
def solo_digitos(palabra):
    digitos = "1234567890"
    solo_digito = True
    for char in palabra:
        if char not in digitos:
            solo_digito = False
    return solo_digito
            

print(solo_digitos("123"))
print(solo_digitos("H23"))
print(solo_digitos("no tengo digito"))
```

    True
    False
    False



```python

```
