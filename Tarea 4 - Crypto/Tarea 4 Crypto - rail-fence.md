**RETO:** rail-fence

**DESCRIPCION:**  
A type of transposition cipher is the rail fence cipher, which is described here. Here is one such cipher encrypted using the rail fence with 4 rails. Can you decrypt it?

**SOLUCION:**

- Descargué el archivo message.txt que contenía números
    
- Primero apliqué módulo 37 a cada número para convertirlos a caracteres (0-25=A-Z, 26-35=0-9, 36=_)
    
- Luego apliqué el descifrado Rail Fence con 4 rieles al texto resultante
    
- El Rail Fence reorganiza los caracteres siguiendo un patrón de zig-zag a través de 4 rieles
    

**Código:**

python

def mod37_decode(numbers):
    result = []
    for num in numbers:
        mod_val = num % 37
        if 0 <= mod_val <= 25:
            result.append(chr(mod_val + 65))
        elif 26 <= mod_val <= 35:
            result.append(chr(mod_val - 26 + 48))
        elif mod_val == 36:
            result.append('_')
    return ''.join(result)

def decrypt_rail_fence(ciphertext, rails):
    fence = [[] for _ in range(rails)]
    rail, direction = 0, 1
    for i in range(len(ciphertext)):
        fence[rail].append(i)
        if rail == 0: direction = 1
        elif rail == rails - 1: direction = -1
        rail += direction
    order = []
    for rail in fence:
        order.extend(rail)
    plaintext = [''] * len(ciphertext)
    for i, pos in enumerate(order):
        plaintext[pos] = ciphertext[i]
    return ''.join(plaintext)

**Flag:** `picoCTF{WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_4A76B997}`

**NOTAS:**

- Combinación de cifrado por sustitución (módulo 37) y transposición (Rail Fence)
    
- El Rail Fence escribe el texto en forma de zig-zag a través de múltiples rieles
    
- Para descifrar, se reconstruye el patrón de zig-zag y se reordenan los caracteres
    
- El mensaje pregunta "WHERE DOES THE FENCE BEGIN AND END" con leet speak