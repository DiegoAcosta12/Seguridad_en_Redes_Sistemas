**RETO:** Vigenere

**DESCRIPCION:**  
Can you decrypt this message? Decrypt this message using this key "CYLAB".

**SOLUCION:**

- Descargué el archivo cipher.txt que contenía el mensaje cifrado: `rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_2951c89f}`
    
- Usé el cifrado Vigenère con la clave "CYLAB" para descifrar
    
- El cifrado Vigenère es polialfabético, donde cada letra del texto se desplaza según la letra correspondiente de la clave
    
- Fórmula de descifrado: `texto_plano = (texto_cifrado - clave + 26) % 26`
    
- La clave "CYLAB" se repite a lo largo del mensaje para el descifrado
    

**Código:**

python

def vigenere_decrypt(ciphertext, key):
    result = []
    key = key.upper()
    for i, char in enumerate(ciphertext):
        if char.isalpha():
            key_char = key[i % len(key)]
            key_shift = ord(key_char) - ord('A')
            if char.isupper():
                decrypted_char = chr((ord(char) - ord('A') - key_shift + 26) % 26 + ord('A'))
            else:
                decrypted_char = chr((ord(char) - ord('a') - key_shift + 26) % 26 + ord('a'))
            result.append(decrypted_char)
        else:
            result.append(char)
    return ''.join(result)

**Flag:** `picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_2951a89h}`

**NOTAS:**

- El cifrado Vigenère es más seguro que los cifrados por sustitución simples porque usa múltiples alfabetos
    
- Sin embargo, sigue siendo vulnerable si la clave es corta o se repite frecuentemente
    
- La flag advierte "DON'T USE VIGENERE CIPHER"
    
- La clave "CYLAB" podría ser una referencia a un laboratorio cibernético (Cyber Lab)