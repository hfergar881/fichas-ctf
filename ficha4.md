# Ficha 4 · Caso guiado 4: Base64
    Enunciado. Decodifica el contenido en Base64 del reto y obtendrás una contraseña. Envía flag{md5} con el MD5 de esa contraseña.

## **1. Tipo de reto:**
Codificación. No es un cifrado ya que Base64 no altera directamente los caracteres. Convierte grupos de 24 bits en 4 bloques de 6 bits.
Aumenta el tamaño del archivo original.

## **2. Concepto.**  
Codificar consiste en cambiar la representación del contenido de un archivo en base a una palabra o una clave. Es un proceso bidireccional y reversible.
Base64 usa caracteres hexadecimales (0-9, a-z, A-Z, +, /). El "=" del final sirve para rellenar el contenido hasta hacer su longitud un múltiplo de 3.  
No se necesita una clave para leerlo.  
En la codificación de correos electrónicos, imágenes incrustadas en páginas web, autenticación web y transferencias de datos en APIs y JSON.

## **3. Procedimiento:**  
Comandos: 
1. base64 -d fichero.txt
2. echo -n recuerdaquebase64NOescifrar | md5sum

| Parte del comando | Qué hace |
| --- | --- |
| base64 -d | Descodifica el contenido de un fichero codificado en Base64. La opción "-d" es la que indica descodificación |
| fichero.txt | Localización del fichero a descodificar |
| echo -n recuerdaquebase64NOescifrar | Imprime el mensaje sin salto de línea |
| md5sum | Vuelve a codificar la contraseña en formato md5 |
	
## **4. Por qué lo hacemos así:**  
Ṕodemos reconocer una codificación en Base64 porque su longitud es un múltiplo de 3 y tiene 1 o 2 "=" al final.
Es un proceso que no puede usarse para el almacenamiento de contraseñas ya no se trata de un cifrado y es reversible.

## **5. Uso de la IA:**  
| Pregunta que le hicimos |	Qué aprendimos | ¿Se equivocó? ¿Cómo lo comprobamos? |
| --- | --- | --- |
| "¿Por qué en ocasiones las codificaciones en Base64 tienen "=" al final?" | a | a |
| "Usos de Base64 en la vida real" | a | a |
		
## **6. Flag:**
flag{cf9df460535b4ec175a464c6c120d3fe}

## **7. Verificación:**
**¿Cómo comprobáis que habéis copiado la contraseña exacta, sin espacios ni signos de más?**  
Porque la longitud del resultado debe corresponderse con la de la codificación y el padding de "=".