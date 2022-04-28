# Examen_pokemon

## Analisis dataset

```
import pandas as pd #importamos todas las librerias de panda(nos ayudara a leer el csv)
import numpy as np #nos ayudara a hacer calculos matematicos
import matplotlib.pyplot as plt #nos permite graficar
import seaborn as sns #importamos todas las librerias de seaborn(nos ayudara a graficar)

datos = pd.read_csv('/Users/hectorbernaltrujillo/Documents/informática/Programación python/Examen_pokemon/Pokemon_limpio.csv')
#no necesitamos ordenarlos de mayor a menor porque ya estan ordenados 
#mostramos los pokemons legendarios 
legendarios = datos[datos['Legendary'] == True]
#Mostramos datos del dataset(tamaño y columnas)
print('Las columnas del dataset son:', datos.columns)
print('El tamaño del dataset es:', datos.shape)
#Mostramos los pokemons con el mayor HP
print('Los pokemons con el mayor HP son:', datos['HP'].nlargest(6)) #nos muestra los 6 pokemons con el mayor HP
#Mostramos los pokemons con la mayor defensa
print('Los pokemons con la mayor defensa son:', datos['Defense'].nlargest(6)) #nos muestra los 6 pokemons con la mayor defensa
#Mostramos los pokemons con la mayor velocidad
print('Los pokemons con la mayor velocidad son:', datos['Speed'].nlargest(6)) #nos muestra los 6 pokemons con la mayor velocidad
#Mostramos los pokemons con la mayor ataque
print('Los pokemons con la mayor ataque son:', datos['Attack'].nlargest(6)) #nos muestra los 6 pokemons con la mayor ataque
#Mostramos cuantos tipos de pokemons hay y cantidad total
print('Hay', len(datos['Type 1'].unique()), 'tipos de pokemons')
print('Hay', len(datos['Type 2'].unique()), 'tipos de pokemons')
print('Hay', len(datos['Type 3'].unique()), 'tipos de pokemons')
#Mostramos un resumen
datos_resumen = datos.describe()
print(datos_resumen)

#VISUALIZAMOS EL ANALISIS DE LOS DATOS
#GRAFICAMOS LOS DATOS
#Graficamos los datos de los pokemons con el mayor HP
plt.figure(figsize=(10,5))
plt.title('Pokemons con el mayor HP')
plt.xlabel('HP')
plt.ylabel('Cantidad')
plt.hist(datos['HP'], bins=10)
plt.show()
#Graficamos los datos de los pokemons con la mayor defensa
plt.figure(figsize=(10,5))
plt.title('Pokemons con la mayor defensa')
plt.xlabel('Defense')
plt.ylabel('Cantidad')
plt.hist(datos['Defense'], bins=10)
plt.show()
#Graficamos los datos de los pokemons con la mayor velocidad
plt.figure(figsize=(10,5))
plt.title('Pokemons con la mayor velocidad')
plt.xlabel('Speed')
plt.ylabel('Cantidad')
plt.hist(datos['Speed'], bins=10)
plt.show()
#Graficamos los datos de los pokemons con la mayor ataque
plt.figure(figsize=(10,5))
plt.title('Pokemons con la mayor ataque')
plt.xlabel('Attack')
plt.ylabel('Cantidad')
plt.hist(datos['Attack'], bins=10)
plt.show()
#Graficamos los datos de los pokemons legendarios
plt.figure(figsize=(10,5))
plt.title('Pokemons legendarios')
plt.xlabel('Legendary')
plt.ylabel('Cantidad')
plt.hist(legendarios['Legendary'], bins=10)
plt.show()
#Graficamos el porcentaje de tipos de pokemons
plt.figure(figsize=(10,5))
plt.title('Porcentaje de tipos de pokemons')
plt.xlabel('Tipos')
plt.ylabel('Porcentaje')
plt.pie(datos['Type 1'].value_counts(), labels=datos['Type 1'].value_counts().index, autopct='%1.1f%%')
plt.show()

```
