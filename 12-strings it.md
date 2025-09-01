RETO:
Strings it.

DESCRIPCION:
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings) without running it?

SOLUCION:
- Usé la herramienta **`strings`**, que extrae todas las cadenas de texto imprimibles de un archivo binario o grande.

- Para filtrar solo la flag, combiné `strings` con `grep`:

`strings archivo_grande | grep "picoCTF{"`

- Esto permitió localizar rápidamente la flag sin revisar manualmente todo el contenido del archivo.

**SOLUCION:** `picoCTF{5tRIng5_1T_d66c7bb7}`

NOTAS ADICIONALES:
- `strings` es útil para examinar archivos binarios y encontrar texto legible.

- También se puede usar `grep -a "picoCTF{" archivo_grande` si el archivo contiene datos binarios.

REFERENCIAS:
- [https://linux.die.net/man/1/strings](https://linux.die.net/man/1/strings?utm_source=chatgpt.com)

- https://www.geeksforgeeks.org/strings-command-in-linux-with-examples/
