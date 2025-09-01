RETO:
Tab, Tab, AttackUseless.

DESCRIPCION:
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip)

	
SOLUCION:
- Descargar el archivo:

`wget https://<url>/Addadshashanammu.zip`

- Descomprimir el archivo:

`unzip Addadshashanammu.zip`

- Explorar el contenido del directorio usando **tab completion** para autocompletar nombres largos de archivos y carpetas.

`ls cd <Tab><Tab>  # Usa Tab para autocompletar los nombres largos`

- O simplemente da muchos clicks a cada carpeta hasta llegar al archivo .txt.
-
- Abrir el archivo correcto que contiene la flag. El archivo estaba dentro del binario `.ELF` extraído del zip, así que se puede usar `strings` o simplemente abrirlo con un editor de texto para buscar la flag:

`strings <archivo> | grep picoCTF`

- La flag encontrada es:

**SOLUCION:** `picoCTF{l3v3l_up!_t4k3_4_r35t!_a00cae70}`

NOTAS ADICIONALES:
- El reto enseña cómo la **autocompletación en la terminal (Tab)** ayuda a navegar y ejecutar comandos más rápido.

- `strings` es útil para examinar archivos binarios y extraer texto legible.

REFERENCIAS:
https://linux.die.net/man/1/strings
