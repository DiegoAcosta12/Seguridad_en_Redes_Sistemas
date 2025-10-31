**RETO:** basic-mod1

**DESCRIPCION:**  
Descifrar un mensaje aplicando módulo 37 a cada número y mapeando a caracteres según: 0-25=A-Z, 26-35=0-9, 36=_

**SOLUCION:**

- Descargué message.txt con los números
    
- Apliqué módulo 37 a cada número
    
- Mapeé los resultados: 0-25 → A-Z, 26-35 → 0-9, 36 → _
    
- Uní los caracteres y los envolví en formato picoCTF{}
    

**Código:**

python

numbers = [128, 322, 353, 235, 336, 73, 198, 332, 202, 285, 57, 87, 262, 221, 218, 405, 335, 101, 256, 227, 112, 140]

result = []
for num in numbers:
    mod_val = num % 37
    if 0 <= mod_val <= 25:
        result.append(chr(mod_val + 65))
    elif 26 <= mod_val <= 35:
        result.append(chr(mod_val - 26 + 48))
    elif mod_val == 36:
        result.append('_')

flag = 'picoCTF{' + ''.join(result) + '}'

**Flag:** `picoCTF{R0UND_N_R0UND_79C18FB3}`

**NOTAS:**

- Operación modular simple para cifrado/descifrado
    
- Mapeo directo de valores a caracteres
    
- No se necesitaron algoritmos criptográficos complejos