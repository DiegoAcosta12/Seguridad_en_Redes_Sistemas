**RETO:** vault-door-3

**DESCRIPCION:**  
This vault uses for-loops and byte arrays. The source code for this vault is here: VaultDoor3.java

**SOLUCION:**

- Descargué el archivo VaultDoor3.java que contenía el código fuente del sistema de seguridad
    
- Analicé el método `checkPassword` que reorganizaba los caracteres de la password usando bucles for
    
- El código tomaba la password de entrada, la reorganizaba en un buffer, y comparaba el resultado con `"jU5t_a_sna_3lpm16g041_u_4_m2r547"`
    
- Revertí las transformaciones aplicando el proceso inverso de cada bucle for
    
- Reconstruí la password original carácter por carácter
    

**Transformaciones revertidas:**

1. **Primer bucle (i=0-7):** `buffer[i] = password[i]`
    
    - Reversa: `password[i] = buffer[i]`
        
2. **Segundo bucle (i=8-15):** `buffer[i] = password[23-i]`
    
    - Reversa: `password[23-i] = buffer[i]`
        
3. **Tercer bucle (i=16-31, paso 2):** `buffer[i] = password[46-i]`
    
    - Reversa: `password[46-i] = buffer[i]`
        
4. **Cuarto bucle (i=31-17, paso -2):** `buffer[i] = password[i]`
    
    - Reversa: `password[i] = buffer[i]`
        

**Código de solución:**

python

target = "jU5t_a_sna_3lpm16g041_u_4_m2r547"
password = [''] * 32

for i in range(8):
    password[i] = target[i]
for i in range(8, 16):
    password[23 - i] = target[i]
for i in range(16, 32, 2):
    password[46 - i] = target[i]
for i in range(31, 16, -2):
    password[i] = target[i]

**Flag:** `picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_120567}`

**NOTAS:**

- El reto demostró cómo las transformaciones simples de caracteres pueden ser revertidas
    
- La password "jU5t_a_s1mpl3_an4gr4m_4_u_120567" significa "just a simple anagram for you"
    
- Aunque el código reorganizaba los caracteres, el patrón era reversible
    
- Las transformaciones lineales de este tipo son inseguras para proteger contraseñas