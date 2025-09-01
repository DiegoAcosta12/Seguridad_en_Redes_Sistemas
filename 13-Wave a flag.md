RETO:
Wave a flag.

DESCRIPCION:
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/a00f554b16385d9970dae424f66ee1ab/warm) has extraordinarily helpful information...

SOLUCION:
- Se usa la herramienta `strings` para extraer todos los textos legibles dentro del binario:

`strings warm`

- Esto permite ver mensajes y la flag que el programa contiene, sin necesidad de ejecutar el binario.
- En este caso, al inspeccionar con `strings`, encontramos la flag directamente.

**SOLUCION:** `picoCTF{b1scu1ts_4nd_gr4vy_18788aaa}`

NOTAS ADICIONALES:
- `strings` es útil para buscar patrones de texto dentro de archivos binarios grandes o ejecutables.

- Se puede combinar con `grep` si se quiere buscar directamente la palabra "picoCTF" que es el formato de todas las flag.

REFERENCIAS:
- [https://linux.die.net/man/1/strings](https://linux.die.net/man/1/strings?utm_source=chatgpt.com)

- https://www.geeksforgeeks.org/strings-command-in-linux-with-examples/