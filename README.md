# reto_8_me_toco_pedir_ayuda_hasta_que_entendi-b
1. Imprimir un listado con los números del 1 al 100 cada uno con su respectivo cuadrado.
   ```pseudocode
range(1, 101) # estableci una lista con un rango del 1 al 100 
c:int = 2 # estableci la variable con 2 para luego hallar la potencia del rango
for n in range(1, 101): # para cada elemento n de la lista del rango previamente establecido
    cuadrado = n ** c #aqui solo calcule el cuadrado para cada elemento de n al cuadrado por la variable establecida
    print("el numero: " + str(n)+ " y su cuadrado es: " + str(cuadrado)) #imprimi el numero y su cuadrado
```
2. Imprimir un listado con los números impares desde 1 hasta 999 y seguidamente otro listado con los números pares desde 2 hasta 1000.

```pseudocode
range(1, 1000) #estableci el primer listado con un rango de 1 a 999
for n in range(1, 101):  #utilice for para iterar el rango, para cada elemento n
    if n%2 == 0: #<bloque> verifica si el numero es par y lo exceptua
        continue 
    print("el valor i en el ciclo es: " + str(n)) #imprime los valores del primer listado establecido
range(2, 1001) #estableci el segundo listado con un rango de 2 a 1000 
for i in range(2, 1001):     #utilice for para iterar el rango, para cada elemento de i
    if i%2 != 0: #<bloque> verifica si el numero es impar y lo exceptua
        continue
    print("el valor i en el ciclo es: " + str(i)) #imprime los valores del segundo listado establecido
```
3. Imprimir los números pares en forma descendente hasta 2 que son menores o iguales a un número natural n ≥ 2 dado
```pseudocode
n = int(input("Ingrese numero natural mayor a 2: ")) #le pide al usuario que ingrese un numero que sea mayor de dos
if n < 2: #verifica que el numero sea menor de dos, de lo contrario funcionara la condicion sera falsa y se ejecutara la otra
    print("el numero debe ser mayor o igual a dos") #imprime indicandole al usuario que el numero debe ser mayor
else: #se verifica esta condicion 
    for i in range (n, 1, -1): #n es el valor inicial de la secuencia, 1 es el valor final de la lista que sera 2 y -1 sera lo que define la descendencia en la lista y los pasos
        if i%2 != 0: #exceptua todos los qeu son impares
            continue
    print(("el valor en el ciclo es: " + str(i))) #<bloque> verifica si el numero es impar y lo exceptua
```
4. Imprimir los números de 1 hasta un número natural n dado, cada uno con su respectivo factorial
   
```pseudocode
n = int(input("Ingrese numero natural: ")) #el usuario ingresa el numero
for i in range(1, n + 1): #itere el rango de uno hasta n, para cada elemento de i
        factorial = 1 #estableci la variable del numero del factorial
        for j in range(1, i + 1): #itere el rango desde 1 hasta los elementos de i, para cada elemnto de j
            factorial *= j #multiplice el factorial para cada elemento j
print("el factorial de su numero " + str(n)+ " es: " + str(factorial)) #imprimi el numero y su factorial
```
5. Calcular el valor de 2 elevado a la potencia n usando ciclos for.

```pseudocode
print("programa para calcular el resultado del numero 2 a una potencia dada")
potencia = int(input("Ingrese numero natural: ")) #el usuario ingresa el numero
resultado:int = 1 #defini la variable resultado con un valor de 1
for i in range(potencia): #se itera el valor del numero n dado para cada elemento de i
    resultado *= 2 #eleva a 2 por el numero dado
print("el numero 2 elevado a " +str(potencia)+ " es: " +str(resultado)) #imprime los resultados
```

6. Leer un número natural n, leer otro dato de tipo real x y calcular x^n usando ciclos for. Disclaimer: Trate de no utilizar el operador de potencia (**).

```pseudocode
n = int(input("ingrese la potencia, un numero natural: ")) #el usuario indica la potencia
x = float(input("ingrese un numero real: ")) #el usuario indica el numero a elevar con la potencia dada
resultado:float = 1.0 #defini la variable con 1 en flotante 
print("el numero " +str(x)+ " elevado al numero " + str(n)+ " es: ") #se imprime los valores dados para luego dar el resultado
for i in range(n): #se intera los valores 0 a n dado para cada elemento de i
    resultado *= x #se eleva x dado por el numero n dado
print(resultado) #imprime el resultado
```

7. Diseñe un programa que muestre las tablas de multiplicar del 1 al 9.

```pseudocode
for i in range(1, 10): #establezco el rango para los elementos de i de 1 a 9
    print("Tabla de multiplicar del: " + str(i)) #imprimo el numero de la tabla de multiplicar de la lista i se itera hasta que se termine el rango de i dado
    for j in range(1, 11): #establezco el rango de j de 1 a 10 
        resultado = i * j #multiplico el numero de la lista i por el numero de la lista j 
        print(str(i)+ " x " + str(j)+ " = " + str(resultado)) #imprimo el resultado se itera hasta finalizar el rango de la lista j 
    print()
```

8. Diseñar una función que permita calcular una aproximación de la función exponencial alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Maclaurin. Nota: use math para traer la función exponencial y mostrar la diferencia entre el valor real y la aproximación.

```pseudocode
import math #importe la funcion math para luego poder implementarla

def aproximacion_exponencial(x, n): #defini la aproximacion exponencial con los argumentos x y n 
    aproximacion = 0 #estableci la variable aproximacion con un valor de 0
    
    for i in range(n): #se intera los valores 0 a n dado para cada elemento de i
        termino = (x ** i) / math.factorial(i) #calcule la ecuacion dada por taylor para la funcion exponencial
        aproximacion += termino #sume la aproximacion con el termino segun los terminos dados n y asi calcular la aproximacion con la formula de taylor 
    
    return aproximacion #retorna la aproximacion
# Calcular la aproximación de la función exponencial para x = 0.9, utilizando los primeros 7 términos de la serie de Maclaurin
x:float = 0.9
n:int = 7
while True: #use el ciclo while para que luego este cumpla la funcion if
  aproximacion = aproximacion_exponencial(x, n) #llame la funcion def para luego imprimirla y para hallar el error
  error = abs(valor_real - aproximacion) #calcule el error con el valor real restando a la aproximacion hayada y use la funcion abs para que lo calcule con el valor absoluto
  # Imprimir la diferencia si es menor del 0.1% de lo contrario no se ejecutara el programa ya que no se podra imprimir la cadena
  if error < 0.001: 
     break
  valor_real = math.exp(x) #se haya el valor real para luego imprimirlo
porcentaje = error * 100 #multiplice el erro por 100 para darlo en porcentaje
cadena = "{:.2f}%".format(porcentaje) #lo puse en un cadena de solo dos decimales 
print("el valor real es de: " + str(valor_real)) #imprime el valor real
print("la aproximacion es de: " + str(aproximacion)+ " y un error de: "+ str(cadena)) # imprime la aproximacion y el error
```
 
9. Diseñar una función que permita calcular una aproximación de la función seno alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Maclaurin. Nota: use math para traer la función seno y mostrar la diferencia entre el valor real y la aproximación.

```pseudocode
import math #importe la funcion math para luego poder implementarla

def aproximacion_seno(x, n): #defini la aproximacion seno con los argumentos x y n 
    aproximacion = 0 #estableci la variable aproximacion con un valor de 0
    
    for i in range(n): #se itera los valores 0 a n dado para cada elemento de i
        termino = ((-1) ** i) * (x ** (2 * i + 1)) / math.factorial(2 * i + 1) #calcule la ecuacion dada por taylor para la funcion seno
        aproximacion += termino #sume la aproximacion con el termino segun los terminos dados n y asi calcular la aproximacion con la formula de taylor 
    
    return aproximacion #retorna la aproximacion
# Calcular la aproximación de la función exponencial para x = 3.5, utilizando los primeros 7 términos de la serie de Maclaurin
x:float = 3.5
n:int = 7
while True: #use el ciclo while para que luego este cumpla la funcion if
  aproximacion = aproximacion_seno(x, n) #llame la funcion def para luego imprimirla y para hallar el error
  error = abs(valor_real - aproximacion) #calcule el error con el valor real restando a la aproximacion hayada y use la funcion abs para que lo calcule con el valor absoluto
  # Imprimir la diferencia si es menor del 0.1% de lo contrario no se ejecutara el programa ya que no se podra imprimir la cadena
  if error < 0.001: 
     break
  valor_real = math.sin(x) #se haya el valor real para luego imprimirlo
porcentaje = error * 100 #multipliquee el error por 100 para darlo en porcentaje
cadena = "{:.2f}%".format(porcentaje) #lo puse en un cadena de solo dos decimales 
print("el valor real es de: " + str(valor_real)) #imprime el valor real
print("la aproximacion es de: " + str(aproximacion)+ " y un error de: "+ str(cadena)) # imprime la aproximacion y el error
```
 
10. Diseñar una función que permita calcular una aproximación de la función arcotangente alrededor de 0 para cualquier valor x en el rango [-1, 1], utilizando los primeros n términos de la serie de Maclaurin. Nota: use math para traer la función arctan y mostrar la diferencia entre el valor real y la aproximación.

```pseudocode
i: int = 1 #<inicia>
print("el valor de i antes del ciclo: " + str(i))
while(i <= 100): #<cond>
    cuadrado = i ** 2 #<bloque>
    print("el valor dentro del ciclo: " + str(i)+ "y su cuadrado: " + str(cuadrado))
    i += 1 #<actualizada>
print("valor final de i: " + str(i))
```
