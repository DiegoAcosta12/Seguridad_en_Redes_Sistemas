**RETO:** substitution2

**DESCRIPCION:**  
It seems that another encrypted message has been intercepted. The encryptor seems to have learned their lesson though and now there isn't any punctuation! Can you still crack the cipher?

**SOLUCION:**

- Descargué el archivo message.txt que contenía un cifrado por sustitución sin puntuación
    
- Usé análisis de frecuencia avanzado de letras individuales, bigramas y trigramas
    
- Identifiqué que los trigramas más comunes eran "naf", "zqg", "nfy" que corresponden a patrones comunes en inglés
    
- El texto sin puntuación hizo más difícil el análisis pero los grupos de letras fueron clave
    
- Ajusté iterativamente el mapeo basado en palabras reconocibles en el texto descifrado parcial
    
- La flag se reveló al final del mensaje descifrado
    

**Técnicas utilizadas:**

- Análisis de frecuencia de monogramas (letras individuales)
    
- Análisis de bigramas (pares de letras más comunes)
    
- Análisis de trigramas (grupos de 3 letras más comunes)
    
- Identificación de patrones sin la ayuda de puntuación
    
- Ajuste manual basado en palabras inglesas reconocibles
    

**Flag:** `picoCTF{N6R4M_4N41Y515_15_73D10U5_8E1BF808}`

**NOTAS:**

- La falta de puntuación hizo el cifrado más desafiante pero no imposible
    
- Los n-gramas (bigramas y trigramas) fueron esenciales para el descifrado
    
- La flag hace referencia a "NGRAM ANALYSIS IS TEDIOUS BUT EFFECTIVE"
    
- Demuestra la importancia del análisis lingüístico en criptografía clásica
    
- Los cifrados por sustitución monoalfabéticos son inherentemente inseguros contra análisis de frecuencia