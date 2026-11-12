# Ficha 3 · Caso guiado 3: romper un hash con un diccionario
    Enunciado. Encuentra el texto cuyo MD5 es 54f662a095fa3d5fbbdaac72d176701b. Pásalo a mayúsculas y calcula su MD5. Envía flag{md5}.

## **1. Tipo de reto:**  
Hash.

## **2. Concepto:** 
Hay herramientas como CrackStation o Dcode que trabajan con grandes diccionarios de contraseñas y palabras conocidas y comunes; y comparan los resultados de cada hasheo con la cadena proporcionada para ver cuál coincide.  
La salt de un hash es una cadena que causa una pequeña alteración en el resultado del hasheo ya realizado para evitar precisamente estos ataques de diccionario; ya que al cambiar el resultado no se puede comparar ni identificar.

## **3. Procedimiento. Pasos y Herramientas:**
| Paso | Herramienta | Qué hace |
| --- | --- | --- |
| Introducir el hash en una herramienta de decodificación | DCode | Comparar el hash con el diccionario para encontrar la cadena original |
| Pasar a mayúsculas la cadena encontrada | Manualmente | Cambia la cadena original para alterar el hash |
| Volver a hashear en formato MD5 | Terminal de Linux (md5sum) | Vuelve a hashear la cadena para asegurarla |

## **4. Por qué lo hacemos así:**  
Las herramientas pueden encontrar este tipo de contraseñas porque son palabras o frases comunes que son fácilmente predecibles y comprobables en ataques de diccionario. Contraseñas mucho más complejas como "Xq7#mP2!vL9@" son más difícilmente descodificables porque no son secuencias comunes y requieren mucha más especificidad. 

## **5. Uso de la IA:**
Para esta ficha no hemos utilizado la IA

## **6. Flag:** 
flag{f395885371dd0ad12136d8a733e05e22}

## **7. Verificación:**
**¿Cómo podéis comprobar, sin fiaros de CrackStation, que el texto que os ha dado es el correcto?**  
Podemos tomar la cadena resultado y hashearla nosotros mismos. Si es igual, es que es correcto, si no, entonces el resultado ha sido fallido.
