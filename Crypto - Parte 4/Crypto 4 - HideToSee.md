**RETO:** HideToSee

**DESCRIPCION:**  
How about some hide and seek heh? Look at this image here.

**SOLUCION:**

- Descargué atbash.jpg
    
- Usé steghide (sin contraseña) para extraer datos ocultos
    
- Obtuve el archivo encrypted.txt con texto cifrado
    
- Apliqué cifrado Atbash al texto (A↔Z, B↔Y, etc.)
    
- Obtuve la flag descifrada
    

**Código:**

python

def atbash(text):
    result = ""
    for char in text:
        if char.isalpha():
            if char.islower():
                result += chr(219 - ord(char))
            else:
                result += chr(155 - ord(char))
        else:
            result += char
    return result

encrypted = "krxlXGU{zgyzhs_xizxp_zx751vx6}"
decrypted = atbash(encrypted)

**Comandos:**

bash

steghide extract -sf atbash.jpg

**Flag:** `picoCTF{atbash_crack_ac751ec6}`

**NOTAS:**

- Esteganografía con steghide para ocultar datos
    
- Cifrado Atbash para ofuscar el mensaje
    
- No se necesitó contraseña para extraer con steghide