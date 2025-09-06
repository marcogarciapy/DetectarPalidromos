# DetectarPalidromos
Este código es para detectar si una palabra o frase es palíndroma
```python
import time
def detectarPalindromo(palabra):
    palabra=palabra.lower()#esto hace que quite todas las mayusaculas de la palabra o frase 
    palabra=palabra.replace(" "," ") #Esta funcion elimina los espacios entre palabras
    palabra=palabra.replace("á", "a") #Quita el acento de las letras
    palabra=palabra.replace("é", "e")
    palabra=palabra.replace("í", "i")
    palabra=palabra.replace("ó", "o")
    palabra=palabra.replace("ú", "u")
    
    primeraLetra=0
    ultimaLetra=len(palabra)-1

    for i in range(0,len(palabra)):
        if palabra[primeraLetra] == palabra[ultimaLetra]:
            primeraLetra += 1
            ultimaLetra -=1
        else:
            return False
        
    return True

palabra= input("Ingrese la palabra para detectar si es palíndromo: ")
for _ in range(3):
    print(".", end="", flush=True)
    time.sleep(1)
print()  # Salto de línea al final
if detectarPalindromo(palabra):
    print("Es una palabra o frase palíndroma")
else:
    print("No una palabra o frase palíndroma")
