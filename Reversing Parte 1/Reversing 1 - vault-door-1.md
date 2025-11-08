**RETO:** vault-door-1

**DESCRIPCION:**  
This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: VaultDoor1.java

**SOLUCION:**

- Descargué el archivo VaultDoor1.java que contenía el código fuente del sistema de seguridad
    
- Analicé el método `checkPassword` que verificaba cada carácter individualmente usando `charAt()`
    
- El método contenía 32 condiciones que verificaban caracteres específicos en posiciones específicas
    
- Reconstruí la password ordenando los caracteres según sus posiciones (0-31)
    
- La password tenía 32 caracteres y estaba dentro del formato picoCTF{}
    

**Proceso de reconstrucción:**

- Extraje todas las condiciones `password.charAt(pos) == 'char'`
    
- Creé un array de 32 posiciones vacías
    
- Coloqué cada carácter en su posición correspondiente
    
- Uní los caracteres para formar la password completa
    

**Código de solución:**

python

conditions = [
    (0, 'd'), (29, '9'), (4, 'r'), (2, '5'), (23, 'r'), (3, 'c'), (17, '4'), 
    (1, '3'), (7, 'b'), (10, '_'), (5, '4'), (9, '3'), (11, 't'), (15, 'c'), 
    (8, 'l'), (12, 'H'), (20, 'c'), (14, '_'), (6, 'm'), (24, '5'), (18, 'r'), 
    (13, '3'), (19, '4'), (21, 'T'), (16, 'H'), (27, '5'), (30, '2'), (25, '_'), 
    (22, '3'), (28, '0'), (26, '7'), (31, 'e')
]

password = [''] * 32
for pos, char in conditions:
    password[pos] = char
password_str = ''.join(password)

**Flag:** `picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_75092e}`

**NOTAS:**

- El reto demuestra cómo la verificación carácter por carácter puede ser reversada fácilmente
    
- La password "d35cr4mbl3_tH3_cH4r4cT3r5_75092e" significa "descramble the characters"
    
- Aunque el código no contenía la password directamente, el patrón de verificación permitió reconstruirla
    
- Es importante usar métodos más seguros para verificar contraseñas en aplicaciones reales