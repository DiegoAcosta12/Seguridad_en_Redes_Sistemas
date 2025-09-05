RETO:
Runme.py.

DESCRIPCION:
Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.[Download runme.py Python script](https://artifacts.picoctf.net/c/34/runme.py)

SOLUCION:
- Descargué el archivo usando `wget` en el WebShell:

`wget https://artifacts.picoctf.net/c/XXX/runme.py`

- Abrí el archivo con `cat` para revisar su contenido:
`cat runme.py`

- Al inspeccionar el código, noté que la flag estaba escrita directamente dentro del script, por lo que no fue necesario ejecutarlo.

**SOLUCIÓN:** `picoCTF{run_s4n1ty_run}`.

NOTAS ADICIONALES:
- Revisar el código de un script antes de ejecutarlo puede ahorrar tiempo si la flag ya está allí.
- `wget` es útil para descargar archivos desde enlaces cuando no se puede usar el navegador.
- `cat` permite inspeccionar rápidamente el contenido de un archivo de texto.

REFERENCIAS:
No use paginas externas a excepción del shell de picoCTF.
