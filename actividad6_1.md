# EJERCICIO 6.1

## 1. Recibir un número entero por teclado y decir si es positivo.
```bash
#!/bin//bash

#Numero entero positivo

echo "introduce un numero"
read num

if [ $num -gt 0 ]
then
	echo "${num} es positivo"
else 
	echo "${num} es negativo"
fi
```
## 2. Recibir un número entero por teclado y decir si es negativo.
```bash
#!/bin/bash

#Numero negativo

echo "introduce un numero"
read num

if [ $num -gt 0 ]
then    
        echo "${num} es positivo"
else    
        echo "${num} es negativo"
fi 
```
## 3.Recibir un número entero por teclado y decir si es igual a cero.
```bash
#!/bin/bash

#Numero igual a cero

echo "introduce un numero"
read num

if [ $num -eq 0 ]
then
	echo "es cero"
else
	echo "no es cero"
fi
```
## 4.Recibir un numero entero por teclado y decir si es positivo, negativo o cero.
```bash
#!/bin/bash

#positivo, negativo o cero

echo "introduce un numero"
read num

if [ $num -gt 0 ]
then
	echo "Numero mayor que cero"
elif [ $num -eq 0 ]
then
	echo "Es cero"
else
	echo "Numero menor que cero"
fi
```
## 5.Comprobar si el número de parámetros introducido es igual a 3, en el caso de que sea otro número mostrará un mensaje de error por pantalla.
```bash
#!/bin/bash

#Comprobar si los parametros introducidos son 3

if [ $# -eq 3 ]
then 
	echo "Has introducido 3 parametros"
else
	echo "Error"
fi
```
## 6.Recibir dos números por parámetros y lo suma. En caso de que el número de parámetros sea incorrecto mostrará un mensaje de error.
```bash
#!/bin/bash

#Sumar dos parametros

if [ $# -eq 2 ]
then
	total=$(( ${1} + ${2} ))
	echo "El total de la suma es ${total} "
else
	echo "ERROR"
fi
```
## 7.Recibir 3 parámetros. En el caso de que reciba un número diferente mostrará un mensaje de error. Los dos primeros serán dos números y el tercero será uno de los siguientes símbolos “+” “-“ “x” “/”, dependiendo del tercer parámetro introducido realizara la correspondiente operación. El en caso de que se introduzca un símbolo diferente, presentará un mensaje indicando cuales son las opciones correctas
```bash
#!/bin/bash

#Recibir 3 parametros. Dos primeros numeros tercero operando


# ![[ $1 =~ ^[0-9]+$ ]] ->Expresion regular numeros


if [ $# -eq 3 ]
then
	if [[ ${1} =~ ^[0-9]+$ && ${2} =~ ^[0-9]+$ ]]
	then
		case ${3} in
			"+") total=$(( ${1} + ${2} ))
				echo "Suma= ${total} ";;
			"-") total=$(( ${1} - ${2} ))
                       		echo "Resta= ${total} ";;
			"*") total=$(( ${1} * ${2} ))
                       		echo "Multiplicacion= ${total} ";;
			"/") total=$(( ${1} / ${2} ))
				echo "Division= ${total} ";;
			*)
				echo "Operando no valido";;
		esac
	else
		echo "Los dos primeros parametros no son numeros"
	fi
else
	echo "Introduce un numero de parametros valido"
fi
```
## 8.Recibir la ruta de un fichero e indicar si existe
```bash
#!/bin/bash

#Recibir un fichero y decir si existe

echo "Introduce una direccion a un fichero"
read  fichero
if [ -e $fichero ]
then
	echo "El fichero existe"
else
	echo "El fichero no existe"
fi
```
## 9.Recibir la ruta de un fichero e indicar si es un directorio o un fichero.
```bash
#!/bin/bash

#Recibir la ruta de un fichero e indicar si es un directorio o fichero

echo "Introduce una ruta"

read ruta

if [ -e $ruta ] 
then
	echo "Es un fichero"
elif [ -d $ruta ]
then
	echo "Es un directorio"
else
	echo "No existe"
fi
```
## 10.Recibir la ruta de un fichero e indicar los permisos que tiene (escritura, lectura, ejecución)
```bash
#!/bin/bash

#decir los permisos de un fichero

# ![[ $1 =~ ^[0-9]+$ ]] ->Expresion regular numeros

echo "Introduzca un fichero"
read fichero

if [ -e $fichero ]
then
	if [ -r $fichero ]
	then
		echo "Tiene permiso de lectura"
	fi
	if [ -w $fichero ]
	then
		echo "Tiene permiso de escritura"
	fi
	if [ -w $fichero ]
	then
		echo "Tiene permiso de ejecucion"
	fi
else
	echo "El fichero no existe"
fi
```
## 11.Imprimir por pantalla 50 veces la palabra hola.
```bash
#!/bin/bash

#Imprimir 50 veces hola

cont=50

for (( i=1; i<=$cont; i++ ))
do
	echo "hola"
done
```
## 12.Leer una palabra por teclado y mostrarla por consola. Debe realizar esta operación 10 veces.
```bash
#!/bin/bash

#Leer una palabra por consola y mostrarla 10 veces

echo "introduce una palabra"
read palabra

for (( i=1; i<=10; i++ ))
do
	echo ${palabra}
done
```
## 13.Recibir un número por parámetro. El programa imprimirá la palabra “hola” el número de veces indicado por parámetro.
```bash
#!/bin/bash

#Repetir hola un numero de veces determinado por el usuario

echo "Introduce el numero de veces que quieres que se repita hola"
read num

for (( i=1; i<=$num; i++ ))
do
	echo "hola"
done
```
## 14.Se debe pasar un número n por parámetro. El programa imprimirá los números del 0 al n por pantalla.
```bash
#!/bin/bash

#Imprimir los numeros desde el 0 hasta el n

for ((i=0; i<=${1}; i++ ))
do
	echo $i
done
```
## 15.Recibir un número n por parámetro. El programa tendrá que sumar todos los números entre 1 y n. Posteriormente mostrará el resultado de la suma por pantalla.
```bash
#!/bin/bash

#Sumar numeros desde 1 hasta n

suma=0

for (( i=1; i<=${1}; i++ ))
do
	suma=$(( ${suma} + ${i} ))
done
echo "La suma es $suma "
```
## 16.Recibir dos números por parámetro. El programa deberá hacer que el primer parámetro tome el valor del segundo parámetro y el segundo parámetro tome el valor del primero. Por ejemplo si se introduce el 2 y el 9, en un principio $1 es 1 y $2 es 9. Tras la ejecución del programa $1 valdrá 9 y $2 1.
```bash
#!/bin/bash

#Recibir dos numeros por parametros y cambiarlos

aux=${1}
aux2=${2}

echo "El valor de la variable 1 es ${aux2} y el valor de la variable 2 es ${aux}"
```
## 17.Programa que lea palabras hasta que se escriba “:q”
```bash
#!/bin/bash

#Programa que lea palabras hasta que se 

palabra="a"
until [ $palabra == ":q" ]
do
	echo "Introduce una palabra"
	read palabra
done
```
## 18.Programa que lea palabras y las guarde en un fichero, hasta que se escriba “:q”
```bash
#!/bin/bash

#Lea palabras y los guarde en un fichero hasta poner :q

palabra="inicio"

until [ $palabra == ":q" ]
do
	echo "Introduce una palabra"
	read palabra
	echo $palabra >> fichero.txt
done
```
## 19.Programa que lea palabras y las guarde en un fichero de forma ordenada, hasta que se escriba “:q”
```bash
#!/bin/bash

#guardar palabras en un fichero ordenadas hasta que se introduca :q

palabra="inicio"

until [ $palabra == ":q" ]
do
	echo "Introduce una palabra"
	read palabra
	echo $palabra >> ficheroOrdenado.txt
	sort -o ficheroOrdenado.txt ficheroOrdenado.txt
done´
```
## 20.Realiza un programa que solicite un número y compruebe si se encuentre en un archivo llamado números.txt
```bash
!/bin/bash

#Comprobar si un numero esta o no en un fichero

echo "Introduce un numero a comprobar"
read num

for i in `cat numeros.txt`
do
	if [ $i -eq $num ]
	then
		echo "El numero se encuentra en el fichero"
		exit 0
	fi
done

echo "El numero no se encuentra en el fichero"
```
