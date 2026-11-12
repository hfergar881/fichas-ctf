# Ficha 2 · Caso guiado 2: SHA-256 y después MD5
    Enunciado. La contraseña es ThisIsAMoreSecureHashFunction. Calcula su SHA-256 y, sobre ese resultado, su MD5. Envía flag{md5}.

## **1. Tipo de reto:**  
Hash.

## **2. Concepto:** 
El hash MD5 tiene una longitud de 32 carácteres en formato hexadecimal; mientras que el SHA-256 usa una cadena de 64 carácteres también en formato hexadecimal.  
Encadenar funciones hash consiste en tomar la salida de una función de hasheo y volver a hashearla con otro formato distinto.  
Importa el orden, ya que cada formato tiene un proceso y longitud distintas que alterarían el resultado final. 

## 3. Procedimiento. Comando exacto y explicación de cada parte:
### Comando: _echo -n ThisIsAMoreSecureHashFunction | sha256sum | awk '{printf $1}' | md5sum_
| Parte del comando | Qué hace |
| --- | --- |
| echo -n ThisIsAMoreSecureHashFunction | Imprime el mensaje sin salto de línea |
| sha256sum | Hashea el mensaje en formato SHA-256 |
| awk '{printf $1}' | Formatea la salida del comando de hash para eliminar espacios, guiones y el salto de línea final |
| md5sum | Vuelve a hashear el resultado del primer hasheo con formato md5 (para mayor seguridad) |

## 4. Por qué lo hacemos así. 
Muestra varios espacios y un guión, que debemos eliminar para no alterar el mensaje original de cara al siguiente hash al pasarle la salida.
awk '{printf $1}' es la parte del comando encargada de eliminar precisamente esta parte adicional.


Prueba 	MD5 obtenido 	¿Coincide con el correcto?
Con awk '{printf $1}' 		
Sin awk (sha256sum | md5sum) 		

## 5. Uso de la IA
| Pregunta que le hicimos |	Qué aprendimos | ¿Se equivocó? ¿Cómo lo comprobamos? |
| --- | --- | --- |
| "¿Qué devuelve sha256sum" | El formato del hash sha256 | No se equivocó. Lo contrastamos con la propia salida del comando ejecutado. |
| "¿Qué significa encadenar funciones hash?" | Funcionamiento del encadenamiento de hasheos | No se equivocó. Comparamos los resultados del comando, probando con distintos órdenes y usando solo 1 formato a la vez en distintas ejecuciones. |

## 6. Flag: 
flag{dd321a22229e0bbb5f8271e370b61eb0}

## 7. Verificación.
**¿Cuántos caracteres tiene el SHA-256 intermedio?**  
64 carácteres.

**¿Y el MD5 final?**  
32 carácteres.
