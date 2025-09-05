RETO:
PW Crack 3

DESCRIPCION:
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/17/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/17/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/17/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

SOLUCION:
- Descargué todos los archivos y los puse en la misma carpeta:

`C:\Users\Diego\Downloads\TAREAS`

- Para encontrar la contraseña correcta, usé un pequeño script en Python que probaba las 7 opciones posibles comparando el hash MD5 de cada una con `level3.hash.bin`:

`import hashlib  def hash_pw(pw_str):     pw_bytes = bytearray()     pw_bytes.extend(pw_str.encode())     m = hashlib.md5()     m.update(pw_bytes)     return m.digest()  correct_pw_hash = open(r'C:\Users\Diego\Downloads\TAREAS\level3.hash.bin','rb').read() pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]  for pw in pos_pw_list:     if hash_pw(pw) == correct_pw_hash:         print("La contraseña correcta es:", pw)`

- Esto me permitió determinar rápidamente que la contraseña correcta era: **`f159`**.
- Finalmente, ejecuté `level3.py` con Python 3 e ingresé la contraseña, lo que descifró el archivo y mostró la flag.


NOTAS ADICIONALES:
- Las contraseñas estaban validadas mediante su hash MD5, por lo que no se podía adivinar directamente la correcta sin comparar hashes.
- Usar un pequeño script para probar todas las opciones de manera automatizada fue más rápido que fuerza bruta manual.
- Usar rutas completas garantiza que Python encuentre todos los archivos necesarios.

REFERENCIAS:
https://docs.python.org/3/library/hashlib.html
