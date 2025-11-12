**RETO:** Picker IV

**DESCRIPCION:**  
Can you figure out how this program works to get the flag? Connect to the program with netcat. The program's source code can be downloaded here. The binary can be downloaded here.

**SOLUCION:**

- Descargué el binario `picker-IV` que era un ejecutable ELF de 64 bits
    
- Analicé el binario usando herramientas de reverse engineering (`objdump`, `nm`)
    
- Identifiqué la dirección de memoria de la función `win` usando `objdump -t picker-IV | grep win`
    
- La dirección encontrada fue `0x000000000040129e`
    
- Me conecté al servicio y cuando solicitó una dirección hexadecimal, ingresé `40129e` (excluyendo el `0x`)
    
- El programa saltó a la función `win` y mostró la flag
    

**Proceso de solución:**

1. **Descargar y analizar el binario:**
    
    bash
    
    wget https://artifacts.picoctf.net/c/528/picker-IV
    chmod +x picker-IV
    file picker-IV
    
2. **Encontrar la dirección de la función win:**
    
    bash
    
    objdump -t picker-IV | grep win
    
    Resultado: `000000000040129e g F .text 0000000000000096 win`
    
3. **Conectar al servicio y proporcionar la dirección:**
    
    bash
    
    nc saturn.picoctf.net 49775
    
    text
    
    Enter the address in hex to jump to, excluding '0x': 40129e
    
4. **Obtener la flag directamente:**
    
    text
    
    picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_14bc5444}
    

**Flag:** `picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_14bc5444}`

**NOTAS:**

- El reto demostró los peligros de permitir que usuarios proporcionen direcciones de memoria para saltar
    
- La vulnerabilidad era un **arbitrary jump** donde el programa ejecutaba cualquier dirección proporcionada por el usuario
    
- En binarios compilados, las funciones tienen direcciones fijas que pueden ser descubiertas con herramientas de análisis
    
- La flag "n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_14bc5444" significa "never jump to user supplied addresses" en leet speak
    
- Este tipo de vulnerabilidad puede llevar a la ejecución de código arbitrario
    
- Las aplicaciones nunca deben permitir que usuarios controlen direcciones de salto o punteros de función
    
- El binario no estaba "stripped", lo que facilitó encontrar los símbolos de las funciones