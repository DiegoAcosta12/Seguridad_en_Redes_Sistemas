RETO:
Fixme2.py

DESCRIPCION:
Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/4/fixme2.py)

SOLUCION:
- Abrí el archivo `fixme2.py` y noté que la línea:

`if flag = "":     print('String XOR encountered a problem, quitting.')`

usaba `=` en lugar de `==`, lo que provocaba un `SyntaxError`.

- Corregí la línea para que quede así:

`if flag == "":     print('String XOR encountered a problem, quitting.')`

- Guardé el archivo y lo ejecuté con Python:
- El script imprimió directamente la flag.

**SOLUCION:** `picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}`

NOTAS ADICIONALES:
- En Python, la comparación se hace con `==`, mientras que `=` sirve para asignar valores.
- Revisar cuidadosamente las líneas con `if` ayuda a detectar errores de sintaxis.
- Ejecutar con `python3` asegura compatibilidad con la versión correcta de Python.

REFERENCIAS:
https://docs.python.org/3/reference/expressions.html?utm_source=chatgpt.com#comparisons