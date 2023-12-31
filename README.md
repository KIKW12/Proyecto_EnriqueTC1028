# TC1028 Proyecto Juan Enrique Ayala Zapata

## Generador de Password

### Contexto

"En la actualidad, sabemos que debemos cambiar nuestras contraseñas cada cierto tiempo para evitar que personas indeseadas accesen a nuestras cuentas personales y toda nuestra informacion.
Se sabe que es recomendable cambiar de contraseñas al menos cada 3 meses, pero siempre llegamos a la capacidad límite de nuestro cerebro para poder crear nuevas combinaciones, es por ello
que este programa te permitirá crear una nueva contraseña que cumpla con los parámetros que tu le pidas, ya sea que contenga letras mayúsculas, minúsculas, caracteres especiales, así como 
la longitud deseada."


Este programa es un generador de contraseñas de acuerdo a las características requeridas por el usuario. El programa corre en la terminal de python3. Muestra una serie de elementos que debe 
de llenar el usuario asignando las características de la contraseña requerida. Al final, imprime la contraseña cumpliendo los parámetros ya establecidos. 

### Avance 2
En este avance se implementó un elemento importante para el generador de contraseñas, un generador de numeros primos. Este funciona pidiéndole al usuario un límite superior, para poder
calcular todos los números primos hasta el límite dado por el usuario. En posteriores avances se realizará un cambio en esta parte para que sea de manera más autónoma.

### Avance 3

En este avance se transforma el codigo anteriormente presentando a una funcion, para durante el desarrollo del proyecto, sea más fácil acceder a cada una de las partes del código. Se realizó la optimización del proceso para saber si un numero es primo utilizando un patron llamado "El patrón de los números primos" que se presenta de la forma x = 6k + 1 y x = 6k - 1. 
Un ejemplo de este patrón es x = (6)(1) - 1, siendo x = 5. Como sabemos, 5 es numero primo. 

### Avance 4

Este avance pide la implementación de estrcuturas de decisión, en el código ya se encontraban desde el avance 3, estas estructuras se encuentran dentro de la función "es_primo". Se utilizan para comprar si el numero ingresado o no cumple con algunas condicioes para saber si es primo o no, antes de entrar al proceso de optimización. 

### Avance 5

Este avance solicita la implementación de estructuras condicionales, en el código ya se encontraban desde el avance No. 3, dentro de la función "es_primo". Estas se utilizaron para poder iterar por el número límite ingresado por el usuario, utilizando un patrón de los números primos llamado 6k+1. Así mismo se incluye un ciclo for para ir imprimiendo los números primos hasta el límite puesto por el usuario.

### Avance 6
En este avance se realiza una reestructuración total del código, tras haber encontrado la forma más optima de calcular los numeros primos, que es utilizando el patrón 6k+1. También se incorporan la parte de la selección de características de la contraseña. Se utilizan listas para ir almacenando tanto la cadena de numeros primos, así como las contraseñas que pidio el usuario que se generaran. Se utiliza la librería **RANDOM** para escoger un caracter o numero de manera "aleatoria" de las listas que proporciona la librería **STRING**, siendo estos parte del alfabeto ASCII. 

### Avance 7
En este avance se realiza la implementación de listas anidadas, sirviendo para brindarle más opciones de contraseñas generadas al usuario, ya que podrá decir cuantas veces quiere que se ejecute el código para poder generar las contraseñas que pide. La lista anidada almacena las contraseñas generadas en cada ejecución. La salida se ha modificado para mostrar las contraseñas generadas en cada ejecución junto con su índice de ejecución. Esto permite tener un registro de las contrasñeas en las diferentes ejecuciones del programa.

## Incorporación de API de Python

A lo largo del desarrollo de este proyecto, se utilizaron 2 librerias propias de Python, siendo estas **Random** y **String** para realizar todo lo necesario en la generación de contraseñas.
### Librería RANDOM
Para el desarrollo del presente código se utlizó principalmente la instrucción *random.choice*, la cual retorna pseuodoaleatoriamente un elemento de una secuencia *seq* no vacía. 

https://docs.python.org/es/3.12/library/random.html?highlight=random%20choice#random.choice

### Libreria STRING
Para el desarrollo del presente código se utilizaron las siguientes funciones presentes en esta librería:

  •string.ascii_lowercase --> Las letras minúsculas 'abcdefghijklmnopqrstuvwxyz'. Este valor es independiente de la configuración regional y no cambiará.
  
  •string.ascii_uppercase --> Las letras mayúsculas 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'. Este valor es independiente de la configuración regional y no cambiará.
  
  •string.punctuation --> Esta función importa una cadena de caracteres ASCII que se consideran caracteres de puntuación en la configuración regional.
  
  •string.digits --> La cadena '0123456789'.

  https://docs.python.org/es/3.12/library/string.html?highlight=string#module-string

## CORRECCIONES
Sub-Competencia: 
	componente: usa la forma más a apropiada al problema para guardar los datos (listas, variable, tipo de dato, etc...) (avance 6 y avance 7)

Error original: No recordé el mandar el avance del proyecto para el avance 6, más sin embargo en el avance 7 ya contaba tanco con las listas y listas anidadas.  

Cambio realizado: Agregué los elementos faltantes para cumplir con el avance 6 y 7 y obtener una buena retroalimentación. 
_Avance 6_

    '''
    Se inicializa una lista vacia que contendra los numeros primos encontrados.
    '''
    primos = []
    '''
    Se incia la variable numero en 5, ya que los primeros numeros primos en el patron 6k±1 son 5 y 7.
    '''
    numero = 5 

    '''
    La variable paso se inicia en 2, esto determina el cambio entre los numeros 6k-1 y 6k+1 alternadamente,
    se comienza en 2 que representa 6k-1.
    '''
    paso = 2  
    
    '''
    Este bucle while se ejecutara hasta que hayamos encontrado la cantidad de numros primos especificados
    'cantidad'.
    '''
    while len(primos) < cantidad:
        '''
        Este condicional comprueba si el numero actual (numero) es primo. Verifica que numero no sea
        divisible por un numero anterior en la lista primos. 
        '''
        if all(numero % p != 0 for p in primos):
            '''
            Si el numero actual que estamos analizando pasa la prueba de ser primo se agrega a la lista. 
            '''
            primos.append(numero)

Líneas de código donde se ve la corrección: 78 a 104

_Avance 7_

    '''
    Se crea la lista contraseñas_generadas vacia para almacenar las contraseñas generadas. 
    '''
    contraseñas_generadas = []
    
            '''
            Este bucle nos permite generar multiples contraseñas en cada ejecucion, que se almacenaran en 
            la lista creada anteriormente. 
            '''
            for _ in range(cantidad_contraseñas):
                contraseña_generada = generar_contraseña(longitud, usar_mayusculas, usar_especiales, usar_numeros, usar_primos)
                
                '''
                Despues de generar todas las contraseñas generadas en una ejecución específica, se agrega
                a la lista principal contraseñas_generadas, creando la estructura de lista anidada. 
                '''
                contraseñas_generadas_ejecucion.append(contraseña_generada)
            
            '''
            Despues de generar todas las contraseñas en una ejecucion especifica, la lista donde se 
            almacenan estas, se agrega a la lista principal. 
            '''
            contraseñas_generadas.append(contraseñas_generadas_ejecucion)

Líneas de código donde se ve la corrección: 127, y 184 a 197
