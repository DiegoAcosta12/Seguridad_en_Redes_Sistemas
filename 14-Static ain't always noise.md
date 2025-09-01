RETO:
Static ain't always noise.

DESCRIPCION:
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/static)? This [BASH script](https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/ltdis.sh) might help!

SOLUCION:
- Descargamos los archivos:
`wget https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/static wget https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/ltdis.sh`

- Le damos permisos de ejecución al script:

`chmod +x ltdis.sh`

- Ejecutamos el script sobre el archivo `static`:

`./ltdis.sh static`

- Alternativamente, podemos usar `strings` directamente sobre el binario para buscar la flag:

`strings static | grep picoCTF`

- El comando mostrará la flag:

**SOLUCION:** `picoCTF{d15a5m_t34s3r_98d35619}`

NOTAS ADICIONALES:
- `strings` es útil para extraer texto legible de archivos binarios o ejecutables.

- Este tipo de retos enseña a examinar binarios y encontrar información escondida.

REFERENCIAS:
- [https://linux.die.net/man/1/strings](https://linux.die.net/man/1/strings?utm_source=chatgpt.com)

- https://www.geeksforgeeks.org/how-to-read-binary-files-in-linux/