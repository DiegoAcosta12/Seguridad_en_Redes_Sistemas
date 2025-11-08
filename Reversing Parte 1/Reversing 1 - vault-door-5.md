**RETO:** vault-door-5

**DESCRIPCION:**  
This vault uses base64 encoding and URL encoding. The source code for this vault is here: VaultDoor5.java

**SOLUCION:**

- Descargué el archivo VaultDoor5.java que contenía el código fuente del sistema de seguridad
    
- Analicé el método `checkPassword` que aplicaba dos capas de codificación a la password
    
- El código tomaba la password de entrada, la convertía a URL encoding y luego aplicaba base64 encoding
    
- El resultado se comparaba con `"JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVmJTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2JTM0JTVmJTY1JTY0JTMwJTYyJTM0JTMyJTM4JTM4"`
    
- Revertí las transformaciones aplicando el proceso inverso: primero decodificación base64 y luego URL decoding
    

**Transformaciones revertidas:**

1. **Primera capa:** `base64Encoded = base64Encode(urlEncoded.getBytes())`
    
    - Reversa: `urlEncoded = base64Decode(base64Encoded)`
        
2. **Segunda capa:** `urlEncoded = urlEncode(password.getBytes())`
    
    - Reversa: `password = urlDecode(urlEncoded)`
        

**Proceso de solución:**

bash

# Decodificar base64
echo "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVmJTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2JTM0JTVmJTY1JTY0JTMwJTYyJTM0JTMyJTM4JTM4" | base64 -d

# Resultado: %63%30%6e%76%33%72%74%31%6e%67%5f%66%72%30%6d%5f%62%61%35%65%5f%36%34%5f%65%64%30%62%34%32%38%38

# Decodificar URL encoding
echo "%63%30%6e%76%33%72%74%31%6e%67%5f%66%72%30%6d%5f%62%61%35%65%5f%36%34%5f%65%64%30%62%34%32%38%38" | sed 's/+/ /g; s/%/\\x/g' | xargs -0 printf "%b"

# Resultado: c0nv3rt1ng_fr0m_ba5e_64_ed0b4288

**Flag:** `picoCTF{c0nv3rt1ng_fr0m_ba5e_64_ed0b4288}`

**NOTAS:**

- El reto demostró cómo las codificaciones múltiples pueden ser revertidas sistemáticamente
    
- La password "c0nv3rt1ng_fr0m_ba5e_64_ed0b4288" significa "converting from base 64"
    
- Aunque se aplicaron dos capas de codificación, cada una es reversible individualmente
    
- Las codificaciones como base64 y URL encoding no son métodos seguros para proteger contraseñas ya que son transformaciones reversibles