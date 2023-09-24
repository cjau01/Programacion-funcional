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
# Proyecto del primer parcial en streamlit con comentarios de explicación paso a paso.
~~~ python
import streamlit as st

#Clase con los datos que se pediran para cada contacto que se desee agregar.
class Persona:
    def __init__(self, nombre, numTel, correo, domicilio, cumple, notas):
        self.nombre = nombre
        self.numTel = numTel
        self.correo = correo
        self.domicilio = domicilio
        self.cumple = cumple
        self.notas = notas
        
#Para declarar una lista global en este programa, primero me aseguro que no exista ya una.
if "personas_db" not in st.session_state:
    #Una vez verificado que no existe ninguna lista global, la declaramos con "st.sessio_state" y el nombre de nuestra lista.
    st.session_state.personas_db = [] 

#Inicio de las operaciones CRUD
#Primera operacion: CREATE - Crear nuevos registros
def crear_persona():
    nombre = st.text_input('Ingrese el nombre:')
    numTel = st.number_input('Ingrese un numero de teléfono:')
    correo = st.text_input('Ingrese el correo electrónico:')
    domicilio = st.text_input('Ingresa tu Domicilio:')
    cumple = st.text_input('Ingresa tu fecha de cumpleaños:')
    notas = st.text_input('Ingresa notas adicionales:')
    
    if st.button("Añadir a la agenda"):
        newperson = {
            "nombre": nombre,
            "Número de teléfono": numTel,
            "Correo Electrónico": correo,
            "Domicilio": domicilio,
            "Fecha de Cumpleaños": cumple,
            "Notas": notas,
        }
        #Al ingresar todos los datos que te solicita para un nuevo contacto, se añadirán a una variable temporal y esa variable será...
        #...agregada posteriormente a nuestra lista global. 
        st.session_state.personas_db.append(newperson)             
        st.success(f"{nombre} ha sido añadido a la agenda")
        
#Segunda operacion: READ - Leer/Mostrar todos los registros actuales.
def mostrar_informacion():
    #Para poder mostrar el registro de contactos, primero verificamos que no esté vacía nuestra agenda.
    if len(st.session_state.personas_db) > 0:
        st.write("Lista de contactos: ", st.session_state.personas_db)
    else:
        st.write("No hay personas por mostrar")
#Tercera operacion: UPDATE - actualizar/modificar registros.
def modificar_persona():
    #Para poder modificar un contacto, primero lo mandamos llamar desde nuestra lista donde fue almacenado anteriormente.
    elegir = st.selectbox('Selecciona una persona', [p['nombre'] for p in st.session_state.personas_db])
    persona = next((p for p in st.session_state.personas_db if p['nombre'] == elegir), None)
    #Una vez sabemos que contacto modificar, los datos que queramos cambiar se van a sobre escribir en una variable temporal...
    #...para ser añadidos de vuelta a nuestra base de datos.
    if persona is not None:
        persona['nombre'] = st.text_input('Ingrese el nombre:', value=persona['nombre'])
        persona['Número de teléfono'] = st.number_input('Ingrese un numero de teléfono:', value=persona['Número de teléfono'])
        persona['Correo Electrónico'] = st.text_input('Ingrese el correo electrónico:', value=persona['Correo Electrónico'])
        persona['Domicilio'] = st.text_input('Ingresa tu Domicilio:', value=persona['Domicilio'])
        persona['Fecha de Cumpleaños'] = st.text_input('Ingresa tu fecha de cumpleaños:', value=persona['Fecha de Cumpleaños'])
        persona['Notas'] = st.text_input('Ingresa notas adicionales:', value=persona['Notas'])
        if st.button('Realizar cambios'):
            st.success(f"{persona['nombre']} ha sido actualizado en la agenda")
    else:
        st.warning("No hay personas para modificar")
#Cuarta y ultima operacion CRUD: DELETE - Eliminar registros
def eliminar_personas():
    elegir = st.selectbox('Selecciona una persona', [p['nombre'] for p in st.session_state.personas_db])
    persona = next((p for p in st.session_state.personas_db if p['nombre'] == elegir), None)
    if persona is not None:
        if st.button("Eliminar de la agenda"):
            st.session_state.personas_db.remove(persona)
            st.success(f"{persona['nombre']} ha sido eliminado de la agenda")
    else:
        st.warning("No existen personas para eliminar")

#Interfaz del menu principal
def main():
    st.title("Agenda de Contactos")

    #Con este "sidebar" agregamos estas cuatro opciones a una barra lateral izquierda
    menu = st.sidebar.selectbox("Menú", ["Mostrar Contactos", "Agregar Contacto", "Modificar Contacto", "Eliminar Contacto"])

    #Aquí simplemente al seleccionar la opción que necesitamos, se mmandará a llamar una de las operaciones CRUD que creamos anteriormente
    if menu == "Mostrar Contactos":
        mostrar_informacion()
    elif menu == "Agregar Contacto":
        crear_persona()
    elif menu == "Modificar Contacto":
        modificar_persona()
    elif menu == "Eliminar Contacto":
        eliminar_personas()

if __name__ == "__main__":
    main()

~~~
