**RETO:** substitution0

**DESCRIPCION:**  
A message has come in but it seems to be all scrambled. Luckily it seems to have the key at the beginning. Can you crack this substitution cipher?

**SOLUCION:**

- Descargué el archivo message.txt que contenía un cifrado por sustitución
    
- La clave estaba al principio del mensaje: `OHNFUMWSVZLXEGCPTAJDYIRKQB`
    
- Esta clave define el mapeo de sustitución (A→O, B→H, C→N, etc.)
    
- Apliqué el mapeo inverso para descifrar todo el texto
    
- El texto descifrado contenía la flag al final
    

**Código:**

python

key = "OHNFUMWSVZLXEGCPTAJDYIRKQB"
alphabet = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"

decrypt_map = {}
for i, cipher_char in enumerate(key):
    decrypt_map[cipher_char] = alphabet[i]

def decrypt_text(text, mapping):
    result = []
    for char in text:
        if char.upper() in mapping:
            if char.isupper():
                result.append(mapping[char])
            else:
                result.append(mapping[char.upper()].lower())
        else:
            result.append(char)
    return ''.join(result)

**Flag:** `picoCTF{5UB5717U710N_3V0LU710N_03055505}`

**NOTAS:**

- Cifrado por sustitución monoalfabético donde cada letra se reemplaza consistentemente
    
- La clave proporcionaba el mapeo directo del alfabeto cifrado
    
- El mensaje habla sobre "substitution evolution" (evolución de la sustitución)
    
- La flag usa leet speak: SUBSTITUTION_EVOLUTION