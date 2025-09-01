RETO:
Repetitions.

DESCRIPCION:
Unzip this archive and find the flag.
- [Download zip file](https://artifacts.picoctf.net/c/505/big-zip-files.zip)

SOLUCION:
- Descargamos el archivo comprimido `big-zip-files.zip`.

- Lo descomprimimos:

    `unzip big-zip-files.zip`

- Ahora tenemos un conjunto muy grande de archivos y carpetas. Buscar manualmente sería imposible, así que usamos `grep` de forma recursiva:

    `grep -R "picoCTF" .`

- `grep` revisará todos los archivos dentro de la carpeta y mostrará dónde aparece la flag.

- El comando devuelve la flag:

**SOLUCIÓN:** `picoCTF{gr3p_15_m4g1c_ef8790dc}`

NOTAS ADICIONALES:
- La opción `-R` de `grep` permite buscar de manera **recursiva** en todos los subdirectorios.

- Esto es muy útil en CTFs donde hay miles de archivos.

- Otra opción sería usar `strings` junto con `grep` en binarios.

REFERENCIAS:
No use paginas externas a excepción del shell de picoCTF.
