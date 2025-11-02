**RETO:** credstuff

**DESCRIPCION:**  
We found a leak of a blackmarket website's login credentials. Can you find the password of the user cultiris and successfully decrypt it?

**SOLUCION:**

- Descargué y extraje leak.tar obteniendo usernames.txt y passwords.txt
    
- Encontré que cada línea en usernames.txt corresponde a la misma línea en passwords.txt
    
- Busqué el usuario "cultiris" en usernames.txt y obtuve su índice
    
- Obtuve la contraseña correspondiente del mismo índice en passwords.txt
    
- La contraseña estaba en formato ROT13
    
- Apliqué descifrado ROT13 para obtener la flag
    

**Código:**

python

with open('usernames.txt', 'r') as f:
    usernames = [line.strip() for line in f.readlines()]

with open('passwords.txt', 'r') as f:
    passwords = [line.strip() for line in f.readlines()]

index = usernames.index('cultiris')
password = passwords[index]

# Descifrar ROT13
import codecs
flag = codecs.encode(password, 'rot13')

**Comandos:**

bash

wget https://artifacts.picoctf.net/c/151/leak.tar
tar -xf leak.tar
cd leak

**Flag:** `picoCTF{C7r1F_54V35_71M3}`

**NOTAS:**

- El leak contenía credenciales de un sitio blackmarket
    
- Las contraseñas estaban ofuscadas usando ROT13
    
- ROT13 es un cifrado de sustitución simple donde cada letra se desplaza 13 posiciones
    
- No se necesitaron herramientas criptográficas complejas