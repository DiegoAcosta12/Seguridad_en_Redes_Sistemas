**RETO:** vault-door-training

**DESCRIPCION:**  
Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility.

**SOLUCION:**

- Descargué el archivo VaultDoorTraining.java que contenía el código fuente del sistema de seguridad
    
- Analicé el código Java y encontré que la contraseña estaba hardcodeada directamente en el método `checkPassword`
    
- La contraseña se revelaba en una comparación simple dentro del código
    
- No fue necesario ejecutar el programa, solo leer el código fuente
    

**Código relevante encontrado:**

java

public boolean checkPassword(String password) {
    return password.equals("picoCTF{w4rm1ng_Up_w1tH_jAv4_be8d9806f18}");
}

**Comandos utilizados:**

bash

wget https://jupiter.challenges.picoctf.org/static/a4a1ca9c54d8fac9404f9cbc50d9751a/VaultDoorTraining.java
cat VaultDoorTraining.java

**Flag:** `picoCTF{w4rm1ng_Up_w1tH_jAv4_be8d9806f18}`

**NOTAS:**

- Este reto demuestra la importancia de no hardcodear credenciales en el código fuente
    
- El código fuente puede revelar información sensible si no se protege adecuadamente
    
- La flag hace referencia a "warming up with Java"
    
- Es un ejercicio introductorio a la serie de retos "vault-door" de picoCTF