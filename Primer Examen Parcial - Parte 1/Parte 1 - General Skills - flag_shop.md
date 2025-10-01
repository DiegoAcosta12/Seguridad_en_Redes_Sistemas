**RETO:**  
flag_shop

**DESCRIPCIÓN:**  
There's a flag shop selling stuff, can you buy a flag? Source. Connect with nc jupiter.challenges.picoctf.org 44566.

**SOLUCIÓN:**

1. **Análisis inicial del servicio**:
    
    - Me conecté al servicio en `jupiter.challenges.picoctf.org 44566`
        
    - Verifiqué el saldo inicial: **1100 unidades monetarias**
        
    - Identifiqué dos productos disponibles:
        
        - **Flag barata**: "Definitely not the flag" por 900 unidades cada una
            
        - **Flag cara**: "1337 Flag" por 100,000 unidades (solo 1 en stock)
            
2. **Identificación de la vulnerabilidad**:
    
    - El servicio presentaba una vulnerabilidad de **integer overflow** en el cálculo del costo total
        
    - Al comprar una cantidad grande de flags baratas, la operación `900 * cantidad` excedía el límite máximo de enteros con signo (2,147,483,647)
        
    - Esto causaba que el costo total se volviera **negativo** debido al desbordamiento
        
3. **Explotación del integer overflow**:
    
    - Compré **3,000,000** flags baratas:
        
        text
        
        Costo calculado: 900 * 3000000 = -1594967296 (integer overflow)
        Balance resultante: 1100 - (-1594967296) = 1594968396
        
    - El balance se infló a **1,594,968,396** unidades
        
4. **Obtención de la flag**:
    
    - Con el balance inflado, compré la "1337 Flag" por 100,000 unidades
        
    - El servicio entregó la flag auténtica
        

**FLAG OBTENIDA:**  
`picoCTF{m0n3y_bag5_68d16363}`

**NOTAS ADICIONALES:**

- La flag `m0n3y_bag5` hace referencia a las "bolsas de dinero" obtenidas mediante la explotación
    
- Este reto demuestra un patrón común en vulnerabilidades de aplicaciones financieras
    
- El código fuente hubiera revelado el uso de variables `int` para almacenar valores monetarios, lo que permitió el desbordamiento