# Practica

Hecho por Rubén, Hugo, Alejandro, Angela

Ficha 5 · Reto 5: otra huella distinta (SHA-1)
Enunciado. La contraseña es HashingIsOneWay2026. Calcula su hash SHA-1 y envía flag{sha1}.

1. Tipo de reto: ☐ Hash ☐ Codificación ☐ Cifrado ☐ Combinado
Hash

2. Concepto. ¿En qué se diferencia SHA-1 de MD5 en longitud de salida? ¿Se considera seguro SHA-1 hoy? ¿Por qué?
La longitud de SHA-1 genera una salida de 32 bits mas larga que MD5.

No se considera seguro hoy en dia debido a que las aplicaciones necesitan seguridad criptográfica.


3. Procedimiento. Comando exacto y explicación de cada parte:
|Parte del comando|	Qué hace|
| --- | --- |
| echo | sirve para imprimir texto |
| -n | indica que no agregue un salto de línea |
| "HashingIsOneway2026" | Es el texto o cadena de caracteres exacta que se va a procesar. |
| Sha1sum | Es la herramienta encargada de calcular el hash utilizando el algoritmo SHA-1 |
4. Por qué lo hacemos así. ¿Por qué el guion y los espacios de la salida no forman parte de la flag? Calculad también el MD5 de la misma contraseña y comparad las dos salidas.
Por que entran en el hash ya que son solo separadores y el guion informa que se a leido la entrada extandar.

|Algoritmo|	Hash obtenido|	Nº de caracteres|	Bits|
| --- | --- | --- | --- |
| MD5	|	1374cfc99a0de192a72ea8f627304d52 | 32 | 128 |
| SHA-1	|	98666584dca50be8bfc35461f4eabe0e31b887ad | 40 | 160 |		

Conclusión: 
Que SHA-1 es mas seguro debido a que este tiene mas caracteres que el MD5(aunque ambos estan obsoletos).

5. Uso de la IA
 - Diferencia entre los dos HASH.
 - Por que SHA-1 no es seguro hoy en dia.
 - Por que el guion y el espacio no forman parte del Flag.
Pregunta que le hicimos	Qué aprendimos	¿Se equivocó? ¿Cómo lo comprobamos?
No sea equivocado debido a que lo hemos comprobado antes de ponerlo.

6. Flag: flag{98666584dca50be8bfc35461f4eabe0e31b887ad}

7. Verificación
Hemos verificado que tiene una longitud de 40 caracteres
