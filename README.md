# TP1
Juego de dos y tres 
'''
Se solicita desarrollar un programa que permita implementar un juego de dados simple; el Juego de Dos o Tres.

El juego se basa en lanzar dados y acumular puntos en base a los valores obtenidos. Su tarea será desarrollar un programa Python que simule el desarrollo del juego.

Se juega con 3 dados y se enfrentan 2 jugadores. El juego se desarrolla en 2 rondas, y en cada ronda ambos jugadores pueden sumar puntos según las reglas de esa ronda.

Al comenzar, el programa debe solicitar los nombres de ambos jugadores, simular dos rondas según las reglas detalladas a continuación e informar el resultado final del juego. Las reglas de puntuación que corresponden a cada ronda del juego son las siguientes:

'''

import random

print ("*" * 50)
print (" \t Bienvenidos al juego de dos o tres")
print ("*" * 50)

nom1 = input ("Ingrese el nombre del primer jugador:")
nom2 = input ("Ingrese el nombre del segundo jugador:")
print ("\nComienza el juego\n")

print ("\t\tRonda 1:")
print ("." * 50)
input ("Jugador " + nom1 + " presione enter para tirar los dados")
d1 = random.randint(1,6)
d2 = random.randint(1,6)
d3 = random.randint(1,6)

print ("Primera Ronda " + nom1 , d1, d2, d3)

res = 0

if d1 == d2 == d3:
    res = 6
else:
   if d1 == d2 and d1 != d3:
       d3 = random.randint(1,6)
       print ("Vuelve a tirar dado:", d3)
       if d3 == d2 == d1:
           res = 6
       else:
           res = 3
   if d1 != d2 and d1 != d3 and d2 == d3:
       d1 = random.randint(1,6)
       print ("Vuelve a tirar dado:", d1)
       if d1 == d2 == d3:
           res = 6
       else:
           res = 3
   if d1 != d2 and d1 == d3:
       d2 = random.randint(1,6)
       print("Vuelve a tirar dado:", d2)
       if d2 == d1 == d3:
           res = 6
       else:
           res = 3
   if d1 != d2 != d3:
       res = 0

print ("." * 50)
print ("El puntaje obtenido por " + nom1 + " es: ", res)
print ("." * 50)
input ("Presione enter para finalizar la primera partida.")
print ("\n\t\tRonda 1:")
print ("." * 50)

input ("Jugador " + nom2 + " presione enter para tirar los dados")
da1 = random.randint(1,6)
da2 = random.randint(1,6)
da3 = random.randint(1,6)

print ("." * 50)
print ("Primera Ronda " + nom2 , da1, da2, da3)
print ("." * 50)

resul = 0

if da1 == da2 == da3:
    resul = 6
else:
   if da1 == da2 and da1 != da3:
       da3 = random.randint(1,6)
       print ("Vuelve a tirar dado:", da3)
       if da3 == da1 == da2:
           resul= 6
       else:
           resul = 3
   if da1 != da2 and da1 != da3 and da2 == da3:
       da1 = random.randint(1,6)
       print ("Vuelve a tirar dado:", da1)
       if da1 == da2 == da3:
            resul = 6
       else:
            resul = 3
   if da1 != da2 and da1 == da3:
       da2 = random.randint(1,6)
       print("Vuelve a tirar dado:", da2)
       if da2 == da1 == da3:
            resul = 6
       else:
            resul = 3
   if da1 != da2 != da3:
            resul = 0
print ("El puntaje obtenido por " + nom2 + " es: ", resul)

print ("." * 50)
input ("Presione enter para finalizar la primera partida.")
print ("\n\t\tRonda 2:")
print ("." * 50)

print ("Jugador ", nom1)
print ("A continuación debe elegir:"
       "\n 1. Impar"
       "\n 2. Par")

poi = int (input ("Coloque el número que corresponda según su elección:"))

dad1 = random.randint(1,6)
dad2 = random.randint(1,6)
dad3 = random.randint(1,6)
dad4 = dad1 + dad2 + dad3
print ("El valor de cada dado es: ", dad1, dad2, dad3)
print ("Dando un valor total de ", dad4)

eleccion = poi % 2
suma = dad4 % 2
compara = eleccion == suma
puntaje = 0

if compara:
    if dad1 > dad2 and dad1 > dad3:
        puntaje = res + dad1
        print ("El puntaje obtenido es: ", puntaje)
    if dad2 > dad1 and dad2 > dad3:
        puntaje = res + dad2
        print("El puntaje obtenido es: ", puntaje)
    if dad3 > dad1 and dad3 > dad2:
        puntaje = res + dad3
        print("El puntaje obtenido es: ", puntaje)
else:
    if dad1 < dad2 and dad1 < dad3:
        puntaje = res - dad1
        print(" El puntaje obtenido es: ", puntaje)
    if dad2 < dad1 and dad2 < dad3:
        puntaje = res - dad2
        print(" El puntaje obtenido es: ", puntaje)
    if dad3 < dad1 and dad3 < dad2:
        puntaje = res - dad3
        print(" El puntaje obtenido es: ", puntaje)

print ("." * 50)
input ("Presione enter para finalizar la segunda partida.")
print ("\n\t\tRonda 2:")
print ("." * 50)

print ("Jugador ", nom2)
print ("A continuación debe elegir:"
       "\n 1. Impar"
       "\n 2. Par")

poi = int (input ("Coloque el número que corresponda según su elección:"))

dado1 = random.randint(1,6)
dado2 = random.randint(1,6)
dado3 = random.randint(1,6)
dado4 = dado1 + dado2 + dado3
print ("El valor de cada dado es: ", dado1, dado2, dado3)
print ("Dando un valor total de ", dado4)

eleccion = poi % 2
suma = dado4 % 2
compara = eleccion == suma
punt = 0

if compara:
    if dado1 > dado2 and dado1 > dado3:
        punt = resul + dado1
        print ("El puntaje obtenido es: ", punt)
    if dado2 > dado1 and dado2 > dado3:
        punt = resul + dado2
        print("El puntaje obtenido es: ", punt)
    if dado3 > dado1 and dado3 > dado2:
        punt = resul + dado3
        print("El puntaje obtenido es: ", punt)
else:
    if dad1 < dado2 and dado1 < dado3:
        punt = resul - dado1
        print(" El puntaje obtenido es: ", punt)
    if dado2 < dado1 and dado2 < dado3:
        punt = resul - dado2
        print(" El puntaje obtenido es: ", punt)
    if dado3 < dado1 and dado3 < dado2:
        punt = resul - dado3
        print(" El puntaje obtenido es: ", punt)

input ("Presione enter para finalizar la segunda partida.")
print ("\n\t\tRonda 2:")
print ("." * 50)

if punt > puntaje:
    print ("!" * 50)
    print ("Ganador", nom2 )
    print("!" * 50)
else:
    print("!" * 50)
    print("Ganador", nom1)
    print("!" * 50)
 
