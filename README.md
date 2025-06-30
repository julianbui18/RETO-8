# RETO 8 - FUNCIONES RECURSIVAS
1. De los retos anteriores selecione 3 funciones y escribalas en forma de lambdas.
  * Funcion 1 - Reto 5: Diseñe una función que calcule la cantidad de carne de aves en kilos si se tienen N gallinas, M gallos y K pollitos cada uno pesando 6 kilos, 7 kilos y 1 kilo respectivamente.

**Codigo normal:**
```python
def calcular_carne(gallinas, gallos, pollitos):
    total = (gallinas * 6) + (gallos * 7) + (pollitos * 1)
    return total

n = int(input("Ingrese el número de gallinas: "))
m = int(input("Ingrese el número de gallos: "))
k = int(input("Ingrese el número de pollitos: "))

carne_total = calcular_carne(n, m, k)
print("La cantidad total de carne es: " + str(carne_total) + " kilos")
```
**Con lambdas:**
```python
# Ingresar el número de gallinas
n = int(input("Ingrese el número de gallinas: "))

# Ingresar el número de gallos
m = int(input("Ingrese el número de gallos: "))

# Ingresar el número de pollitos
k = int(input("Ingrese el número de pollitos: "))

# Se usa un lambda anónimo para calcular la cantidad total de carne, donde ultiplicamos el número de gallinas por 6, el número de gallos por 7 y el número de pollitos por 1, para luego sumar todo.
carne_total = (lambda gallinas, gallos, pollitos: (gallinas * 6) + (gallos * 7) + (pollitos * 1))(n, m, k)

# Imprimir resultado
print("La cantidad total de carne es: " + str(carne_total) + " kilos")
```
* Funcion 2 - Reto 5: Haga un programa que utilice una función para calcular el valor de un préstamo C usando interés compuesto del i por n meses.
  
**Codigo normal:**
```python
def calcular_prestamo(capital, interes, meses):
    total = capital * (1 + interes) ** meses
    return total

P = float(input("Ingrese el capital prestado: "))
i = float(input("Ingrese la tasa de interés mensual: "))
n = int(input("Ingrese el número de meses: "))

C = calcular_prestamo(P, i, n)

print("El valor total a pagar es: " + str(C))
```
**Con lambdas:**
```python 
# Ingresar el capital prestado
P = float(input("Ingrese el capital prestado: "))

# Ingresar la tasa de interés mensual
i = float(input("Ingrese la tasa de interés mensual: "))

# Ingresar el número de meses
n = int(input("Ingrese el número de meses: "))

# Usar un lambda anónimo para calcular el monto total a pagar
C = (lambda capital, interes, meses: capital * (1 + interes) ** meses)(P, i, n)

# Imprimir valor a pagar
print("El valor total a pagar es: " + str(C))
```
* Funcion 3 - Reto 5: Dado la figura de la imagen, desarrolle:
* Una función matemática para calcular el área y el perimetro.
* Cree dos funciones en python para calcular los valores antes establecidos, al ingresar por teclado ```r```, ```a``` y ```b```.
* Revise como utilizar el valor de ```pi``` usando import math y math.pi

  **Codigo normal:**
```python
import math

def area_de_la_figura(a: float, b: float, r:float)->float:
    return (a*b) + 2*(math.pi*r**2)

def perimetro_de_la_figura (a: float, b: float, r:float)->float:
    return (2*a + 2*b) + 2* (2*math.pi*r)

if __name__ == "__main__":
    a = float(input("Ingrese la altura del rectángulo: "))
    b = float(input("Ingrese la base del rectángulo: "))
    r = float(input("Ingrese el radio de los círculos: "))
    area = area_de_la_figura(a,b,r)
    perimetro = perimetro_de_la_figura (a,b,r)
    print ("El área de la figura es "+str(area))
    print ("El perímetro de la figura es "+ str(perimetro))
```
  **Con lambdas:**
```python 
import math  # Importar el módulo math para poder usar pi

if __name__ == "__main__":
    # Definir la función anónima (lambda) para calcular el área de la figura:
    area_de_la_figura = lambda a, b, r: (a * b) + 2 * (math.pi * r ** 2)
    
    # Definir la función anónima (lambda) para calcular el perímetro de la figura:
    perimetro_de_la_figura = lambda a, b, r: (2 * a + 2 * b) + 2 * (2 * math.pi * r)

    # Ingresar la altura del rectángulo
    a = float(input("Ingrese la altura del rectángulo: "))
    
    # Ingresar la base del rectángulo
    b = float(input("Ingrese la base del rectángulo: "))
    
    # Ingresar el radio de los círculos
    r = float(input("Ingrese el radio de los círculos: "))

    # Calcular el área usando la función lambda y los valores ingresados
    area = area_de_la_figura(a, b, r)
    
    # Calcular el perímetro usando la función lambda y los valores ingresados
    perimetro = perimetro_de_la_figura(a, b, r)

    # Mostrar el área calculada
    print("El área de la figura es " + str(area))
    
    # Mostrar el perímetro
    print("El perímetro de la figura es " + str(perimetro))
```
2. De los retos anteriores selecione 3 funciones y escribalas con argumentos no definidos (*args).
* Funcion 1 - Reto 5: Diseñe una función que calcule la cantidad de carne de aves en kilos si se tienen N gallinas, M gallos y K pollitos cada uno pesando 6 kilos, 7 kilos y 1 kilo respectivamente.

**Codigo normal:**
```python
def calcular_carne(gallinas, gallos, pollitos):
    total = (gallinas * 6) + (gallos * 7) + (pollitos * 1)
    return total

n = int(input("Ingrese el número de gallinas: "))
m = int(input("Ingrese el número de gallos: "))
k = int(input("Ingrese el número de pollitos: "))

carne_total = calcular_carne(n, m, k)
print("La cantidad total de carne es: " + str(carne_total) + " kilos")
```
**Con args:**
```python
def calcular_carne(*args):
    # Usar args los argumentos para que el cálculo sea claro
    gallinas, gallos, pollitos = args
    total = (gallinas * 6) + (gallos * 7) + (pollitos * 1)
    return total

# Ingresar datos
n = int(input("Ingrese el número de gallinas: "))
m = int(input("Ingrese el número de gallos: "))
k = int(input("Ingrese el número de pollitos: "))

# Llamar la función pasando los datos
carne_total = calcular_carne(n, m, k)

# Imprimir el resultado
print("La cantidad total de carne es: " + str(carne_total) + " kilos")
```
* Funcion 2 - Reto 5: Haga un programa que utilice una función para calcular el valor de un préstamo C usando interés compuesto del i por n meses.
  
**Codigo normal:**
```python
def calcular_prestamo(capital, interes, meses):
    total = capital * (1 + interes) ** meses
    return total

P = float(input("Ingrese el capital prestado: "))
i = float(input("Ingrese la tasa de interés mensual: "))
n = int(input("Ingrese el número de meses: "))

C = calcular_prestamo(P, i, n)

print("El valor total a pagar es: " + str(C))
```
**Con args:**
```python
def calcular_prestamo(*args):
    # Usar args para los argumentos en variables con nombre
    capital, interes, meses = args
    total = capital * (1 + interes) ** meses
    return total

# Ingresar datos 
P = float(input("Ingrese el capital prestado: "))
i = float(input("Ingrese la tasa de interés mensual: "))
n = int(input("Ingrese el número de meses: "))

# Llamar la función pasando los valores
C = calcular_prestamo(P, i, n)

# Imprimir el resultado
print("El valor total a pagar es: " + str(C))
```
* Funcion 3 - Reto 5: Dado la figura de la imagen, desarrolle:
* Una función matemática para calcular el área y el perimetro.
* Cree dos funciones en python para calcular los valores antes establecidos, al ingresar por teclado ```r```, ```a``` y ```b```.
* Revise como utilizar el valor de ```pi``` usando import math y math.pi

  **Codigo normal:**
```python
import math

def area_de_la_figura(a: float, b: float, r:float)->float:
    return (a*b) + 2*(math.pi*r**2)

def perimetro_de_la_figura (a: float, b: float, r:float)->float:
    return (2*a + 2*b) + 2* (2*math.pi*r)

if __name__ == "__main__":
    a = float(input("Ingrese la altura del rectángulo: "))
    b = float(input("Ingrese la base del rectángulo: "))
    r = float(input("Ingrese el radio de los círculos: "))
    area = area_de_la_figura(a,b,r)
    perimetro = perimetro_de_la_figura (a,b,r)
    print ("El área de la figura es "+str(area))
    print ("El perímetro de la figura es "+ str(perimetro))
```
**Con args:**
```python
import math

def area_de_la_figura(*args) -> float:
    # Args para los argumentos
    a, b, r = args
    return (a * b) + 2 * (math.pi * r ** 2)

def perimetro_de_la_figura(*args) -> float:
    a, b, r = args
    return (2 * a + 2 * b) + 2 * (2 * math.pi * r)

if __name__ == "__main__":
    a = float(input("Ingrese la altura del rectángulo: "))
    b = float(input("Ingrese la base del rectángulo: "))
    r = float(input("Ingrese el radio de los círculos: "))

    # Llamar a las funciones pasando los valores
    area = area_de_la_figura(a, b, r)
    perimetro = perimetro_de_la_figura(a, b, r)
    # Imprimir resultados
    print("El área de la figura es " + str(area))
    print("El perímetro de la figura es " + str(perimetro))
```
3. Escriba una función recursiva para calcular la operación de la potencia.

**SOLUCION**
```python
def potencia(base, exponente):
    # Cualquier número elevado a 0 es 1
    if exponente == 0:
        return 1
    else:
        # Si el exponente no es 0, multiplicamos la base por el resultado de llamar la función otra vez pero con el exponente restado en 1
        return base * potencia(base, exponente - 1)

# Ingresar la base del número
base = float(input("Ingrese la base: "))

# Ingresar el exponente
exponente = int(input("Ingrese el exponente: "))

# Función para calcular el resultado
resultado = potencia(base, exponente)

# Imprimir el resultado
print("El resultado de " + str(base) + " elevado a la " + str(exponente) + " es " + str(resultado))
```
4. Utilice la siguiente plantilla de code para contar el tiempo:
```python
import time

start_time = time.time()
# instrucciones sobre las cuales se quiere medir tiempo de ejecución
end_time = time.time()

timer = end_time - start_time
print(timer)
```
* Primero se hizo uno para la opcion recursiva:
```python
import time

def fiboRecursivo(n: int) -> int:
    if n <= 1:
        return 1
    else:
        return fiboRecursivo(n - 1) + fiboRecursivo(n - 2)

if __name__ == "__main__":
    start_time = time.time()
    num = int(input("Ingrese número para Fibonacci recursivo: "))
    resultado = fiboRecursivo(num)
    print("El Fibonacci recursivo de " + str(num) + " es " + str(resultado))
    end_time = time.time()

    timer = end_time - start_time
    print("El tiempo que se demoró el programa fue de: " + str(timer) + " segundos")
```
* Y ya despues esta en la manera iterativa
```python
import time

def fiboIterativo(n: int) -> int:
    if n <= 1:
        return 1
    else:
        a = 1
        b = 1
        for _ in range(2, n + 1):
            a, b = b, a + b
        return a

if __name__ == "__main__":
    start_time = time.time()
    num = int(input("Ingrese número para Fibonacci iterativo: "))
    resultado = fiboIterativo(num)
    print("El Fibonacci iterativo de " + str(num) + " es " + str(resultado))
    end_time = time.time()

    timer = end_time - start_time
    print("El tiempo que se demoró el programa fue de: " + str(timer) + " segundos")
```
5. Crear cuenta en stackoverflow.
   ![image](https://github.com/user-attachments/assets/91c66486-04a4-4a73-9a16-01b598cc2a02)
6. Cosas de adultos....ir a linkedin y crear perfil....NO IMPORTA que estén iniciando, si tienen tiempo para redes poco útiles como fb, insta, o tiktok tienen tiempo para crear un perfil mamalón.

   www.linkedin.com/in/julian-esteban-buitrago-cruz-70527a372
   
   **JULIAN ESTEBAN BUITRAGO CRUZ**
   
