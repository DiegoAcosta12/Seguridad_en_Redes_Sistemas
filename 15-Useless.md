RETO:
Useless.

DESCRIPCION:
There's an interesting script in the user's home directory
Additional details will be available after launching your challenge instance.

SOLUCION:
- Conectarse al host vía SSH:

`ssh -p 58491 picoplayer@saturn.picoctf.net # Contraseña: password`

- Listar los archivos del directorio y revisar el script:

`ls cat useless`

- Probar el script con distintos argumentos:

`./useless add 1 2 ./useless sub 3 1 ./useless mul 2 3 ./useless div 6 3`

- Revisar el manual del script, que contiene la flag:

`man useless`

- La flag aparece dentro del manual:

**SOLUCION:** `picoCTF{us3l3ss_ch4ll3ng3_3xpl0it3d_4151}`

NOTAS ADICIONALES:
- El script realiza operaciones matemáticas básicas y también contiene información útil escondida en su manual.

- Revisar siempre el código y el manual de los scripts en retos CTF puede revelar la flag.

REFERENCIAS:
https://linux.die.net/man/1/ssh