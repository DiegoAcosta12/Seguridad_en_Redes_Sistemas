RETO:
fixme1.py

DESCRIPCION:
Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/27/fixme1.py)

SOLUCION:
- Abrí el archivo `fixme1.py` y noté que la línea:

  `print('That is correct! Here\'s your flag: ' + flag)`

tenía un espacio de más al inicio. Esto provocaba un `IndentationError`.

- Corregí la indentación para que quede así:

`flag = str_xor(flag_enc, 'enkidu') print('That is correct! Here\'s your flag: ' + flag)`
- Guardé el archivo y lo ejecuté con Python 3:
- El script imprimió directamente la flag.

**SOLUCION:** `picoCTF{1nd3nt1ty_cr1515_182342f7}`

NOTAS ADICIONALES:
- En Python, la indentación es crítica y cualquier espacio extra puede causar errores de sintaxis.

- Revisar el código antes de ejecutarlo ayuda a identificar errores simples de indentación.

- Ejecutar con `python3` asegura compatibilidad con la versión correcta de Python.

REFERENCIAS:
https://docs.python.org/3/reference/lexical_analysis.html?utm_source=chatgpt.com#indentation
