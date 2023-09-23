## Anotaciones de la primera parcial

~~~ python
import random

variable = random.randint(1,10)

if variable > 5:
    print(f"El número {variable} es mayor a 5")
else:
    print(f"El número {variable} es menor a 5")
~~~
~~~ python
import random

if (variable = random.randint(1,10)) > 5:
    print(f"El número {variable} es mayor a 5")
else:
    print(f"El número {variable} es menor a 5")
~~~
~~~ python
import random

if (variable := random.randint(1,10)) > 5:
    print(f"El número {variable} es mayor a 5")
else:
    print(f"El número {variable} es menor a 5")
~~~
### 1.3.2.2 Lógicos: Bool
~~~ python
# True
# False

if 5 > 4:
    print(True)
else:
    print(False)

print(5 > 7)

recive: bool = False
not recive
~~~
### 1.3.2.3 Cadena: String
~~~ python
name: str = "oliver"
print(name)
print(type(name))

print(name.capitalize())
print(name.upper())
~~~
~~~ python
num: int = 10
pi: float = 3.14
is_student: bool = True
name: str = "Oliver"

print(f"{num} - {pi} - {is_student} - {name}")
~~~
### 1.3.3 Operadores
#### 1.3.3.1 Aritméticos
~~~ python
print(5 + 4) # Suma
print(5 - 4) # Resta
print(5 * 4) # Multiplicación
print(5 / 4) # División
print(5 // 4) # División Entera
print(5 % 4) # Módulo o Residuo
print(5 ** 4) # Exponencial
~~~
### 1.3.3.2 Lógicos
~~~ python
print(True and False) # Y
print(True or False) # O
print(not False) # NO
~~~
### 1.3.3.3 Condicionales
~~~ python
n1: int = 30
n2: int = 20

if n1 > n2:
    print(f"{n1} > {n2}")
~~~
~~~ python
n1: int = 10

if n1 > n2:
    print(f"{n1} > {n2}")
else:
    print(f"{n1} < {n2}")
~~~
~~~ python
age: int = 18

if age > 18:
    print("Mayor de edad")
elif age == 18:
    print("Acabas de llegar a la mayoría de edad")
else:
    print("Menor de edad")
~~~
~~~ python
# Listas
# Colecciones (Collections)

def suma(a, b):
    return a + b

def resta(a, b):
    return a - b

def multiplicacion(a, b):
    return a * b

def division(a, b):
    return a / b

operaciones = [suma, resta, multiplicacion, division]

print(operaciones[0](5, 4))
print(operaciones[1](5, 4))
print(operaciones[2](5, 4))
print(operaciones[3](5, 4))

for operacion in operaciones:
    print(operacion(5, 4))

lista = [1, 2, 3, 4, 5, True, 4.5, "Oliver", [1, 2, 3]]
~~~
~~~ python
# Es indexable

lista[8]
~~~
~~~ python
# Slices

print(lista)
print(lista[:])

print(lista[0:1])
print(lista[0:])
print(lista[-3:-1])
def suma(a, b):
    pass

print(suma(3, 4))
~~~
~~~ python
def operaciones(a, b):
    return [a + b, a - b, a * b, a / b]

respuestas= operaciones(5, 4)
print(respuestas)
w, x, y, z = operaciones(5, 4)
print(w)
~~~
~~~ python
# Tuplas (Tuples)

tupla_funciones = (suma, resta, multiplicacion, division)
print(tupla_funciones[1](5, 4))

tupla = (1, 2, 3, 4, 5, True, 4.5, "Oliver", [1, 2, 3])
~~~
~~~ python
# tupla[0] = 10 es inmutable

lista.append(10)
lista
~~~
~~~ python
def suma(a: int, b: int) -> int:
    return a + b

def operacion(a: int, b: int) -> tuple:
    return (a + b, a - b)

(a, b) = operacion(5, 6)
a, b = operacion(6, 5)
print(a, b)
~~~
~~~ python
# Rangos (Ranges)

numeros = range(10)
print(numeros)
~~~
~~~ python
for i in numeros:
    print(i, end=" ")
~~~
~~~ python
numeros_pares = range(2, 11, 2)
for par in numeros_pares:
    print(par, end=" ")
~~~
~~~ python
# Set (Conjuntos)

mi_set = {1, 2, 3, 3, 3, 3, 3}
mi_set
~~~
~~~ python
data = [15, 14, 13, 12, 11, 10, 1, 2, 3, 4, 5, 6, 7, 8, 9, 1, 2, 1, 2, 1, 2, 1, 2]
set(data)
~~~
~~~ python
# Dccionarios

mi_dict = {"llave": "valor"}
mi_dict["llave"]
~~~
~~~ python
mi_dict.keys()
~~~
~~~ python
mi_dict.keys()
~~~
~~~ python
mi_dict.values()
~~~
~~~ python
days_of_week = {
    "Monday": "1",
    "Tuesday": "2",
    "Wednesday": "3",
    "Thursday": "4",
    "Friday": "5",
    "Saturday": "6",
    "Sunday": "7"
}

for e in mi_set:
    print(e, end=" ")

for key in days_of_week.keys():
    print(key)

for value in days_of_week.values():
    print(value)

for key, value in days_of_week.items():
    print(key, value)

print(days_of_week)
~~~
# Deme chance de subirle mi código del proyecto aquí, por favor.
