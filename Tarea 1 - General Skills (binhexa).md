RETO:
Binhexa.

DESCRIPCION:
How well can you perfom basic binary operations?Start searching for the flag here `nc titan.picoctf.net 65473`


SOLUCION:
1. Me conecté al servidor utilizando netcat:  
    `nc titan.picoctf.net 65473`
    
2. El servidor presentó dos números binarios:
    
    - Binary Number 1: `10001001`
        
    - Binary Number 2: `01101101`
        
3. Resolví secuencialmente las 6 operaciones solicitadas:
    
    - **Operación 1 (OR bit a bit `|`):**  
        `10001001 | 01101101 = 11101101`
        
    - **Operación 2 (Multiplicación `*`):**  
        Convertí a decimal: `10001001` = 137, `01101101` = 109.  
        `137 * 109 = 14933` → Binario: `11101001010101`
        
    - **Operación 3 (Desplazamiento izquierda `<<` de Binary 1 por 1 bit):**  
        `10001001 << 1 = 100010010`
        
    - **Operación 4 (Desplazamiento derecha `>>` de Binary 2 por 1 bit):**  
        `01101101 >> 1 = 00110110`
        
    - **Operación 5 (Suma `+`):**  
        `137 + 109 = 246` → Binario: `11110110`
        
    - **Operación 6 (AND bit a bit `&`):**  
        `10001001 & 01101101 = 00001001`
        
4. Para la última operación, convertí el resultado binario a hexadecimal:  
    `00001001` (binario) = `9` (decimal) = `09` (hexadecimal, con padding a 2 dígitos).
    
5. Ingresé el resultado hexadecimal (`09`) y recibí la flag.
    

**SOLUCION:**`picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_6862762d}`

NOTAS ADICIONALES:
- Las conversiones entre binario, decimal y hexadecimal fueron clave para resolver el reto.
    
- Operaciones bit a bit (AND, OR, desplazamientos) requieren precisión en la manipulación de bits.
    
- La multiplicación de números binarios puede resultar en un número de más bits, por lo que es importante no truncar incorrectamente.

REFERENCIAS:
- [Bitwise Operations](https://en.wikipedia.org/wiki/Bitwise_operation)
    
- [Binary to Hexadecimal Conversion](https://www.rapidtables.com/convert/number/binary-to-hex.html)