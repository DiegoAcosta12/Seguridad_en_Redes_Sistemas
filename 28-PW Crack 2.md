RETO:
PW Crack 2

DESCRIPCION:
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/13/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/13/level2.flag.txt.enc) in the same directory too.

SOLUCION:
- Descargué ambos archivos y me aseguré de que estuvieran en la misma carpeta:
`C:\Users\Diego\Downloads\TAREAS``

- Ejecuté el script con Python.
- Ingresé la contraseña correcta: `de76`.
- El script descifró el archivo y mostró la flag.

**SOLUCION:** `picoCTF{tr45h_51ng1ng_489dea9a}`


NOTAS ADICIONALES:
- Revisar el código del verificador de contraseñas permite deducir la contraseña correcta sin usar fuerza bruta.
- Usar rutas completas asegura que Python encuentre los archivos necesarios.
- Ejecutar con `python3` garantiza compatibilidad con la versión correcta de Python.

REFERENCIAS:
https://docs.python.org