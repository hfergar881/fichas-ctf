# Ficha 1 · Caso guiado 1: Hash MD5

> Enunciado. La contraseña es LearnTheHashFunction. Calcula su hash MD5 y envíalo como flag{md5}.  


## 1. **Tipo de reto:**  
Hash. Codificar consiste en cambiar de formato la contraseña, cifrar es ocultar algo con una contraseña para poder leerlo después; siendo ambos reversibles. El hasheo en cambio es un proceso irreversible que consiste en la creación de una "huella digital".

## 2. **Concepto.**  
El hasheo es un proceso que consiste en la creación de una "huella digital" determinista (dada la misma entrada siempre devuelve el mismo resultado), de longitud fija (la longitud del resultado siempre es la misma independientemente de la longitud de la entrada) e irreversible (no se puede obtener la entrada si solo se conoce el resultado). 
El formato MD5 tiene una longitud de 32 caracteres y ya no se considera seguro ya que su longitud es susceptible a ataques de fuerza bruta.

## 3. **Procedimiento.** Comando exacto y explicación de cada parte:  

### Comando: echo -n LearnTheHashFunction | md5sum

| Parte del comando | Qué hace |
| --- | --- |
| echo | Imprime en la consola el mensaje indicado |	
| -n | Elimina el salto de línea al final del mensaje |	
| LearnTheHashFunction | Mensaje a imprimir |	
| \| | Redirige la salida del comando anterior hacia el siguiente |	
| md5sum | Comando de hasheo con formato MD5 |	

## 4. **Por qué lo hacemos así.**  
 El modificador "-n" es necesario porque si no el comando echo añade automáticamente un salto de línea al final (El mensaje sería "LearnTheHashFunction/n"). Esto cambiaría completamente el hash y ya no coincidiría con la contraseña, ya que un solo carácter altera todo el resultado. 

| Prueba | Hash obtenido | ¿Coincide con el correcto? |
| --- | --- | --- |
| echo -n LearnTheHashFunction | b2f2d6b27b264d83fe1abe0169b7613e | Sí |
| echo LearnTheHashFunction (sin -n) | c6600000d8fbb39ad68728190fd3d7dd | No |
| echo -n learnTheHashFunction (minúscula) | 81b55e8d26f83b740bbd34ebb417a597 | No |

## 5. **Uso de la IA**  

| Pregunta que le hicimos | Qué aprendimos | ¿Se equivocó? ¿Cómo lo comprobamos? |
| --- | --- | --- |
| "¿Por qué usar Hash en lugar de Codificación o Cifrado?" | Diferencias entre los 3 procesos | No se equivocó. Lo revisamos en internet |
| "¿Qué carácteres puede contener un hash MD5?" | Carácteres de los hash MD5 (0-9, a-f, A-F) | No se equivocó. Lo revisamos en internet |

## 6. **Flag:**  
flag{b2f2d6b27b264d83fe1abe0169b7613e}

## 7. **Verificación.**  
**¿Cuántos caracteres tiene un hash MD5?**  
32

**¿Qué caracteres puede contener?**
Todos los números del 0 al 9 y letras desde la a hasta la f, tanto mayúsculas como minúsculas.