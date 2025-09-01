RETO:
First Find.

DESCRIPCION:
Unzip this archive and find the file named 'uber-secret.txt'

- [Download zip file](https://artifacts.picoctf.net/c/501/files.zip)

SOLUCION:
- Descargamos el archivo comprimido `first-find.zip`.

- Lo descomprimimos con:

    `unzip first-find.zip`

- Una vez descomprimido, buscamos el archivo llamado `uber-secret.txt` usando el comando `find`:

    `find . -name "uber-secret.txt"`

- El comando muestra la ruta exacta del archivo dentro de los directorios.

- Mostramos el contenido del archivo con:

    `cat ./ruta/uber-secret.txt`

- En el archivo encontramos la flag:

**SOLUCIÓN:** `picoCTF{f1nd_15_f457_ab443fd1}`

NOTAS ADICIONALES:
- `find` es muy útil para ubicar archivos rápidamente en estructuras de directorios grandes.
- También puede usarse con `grep` para buscar contenido dentro de varios archivos.

REFERENCIAS:
No use paginas externas a excepción del shell de picoCTF.
