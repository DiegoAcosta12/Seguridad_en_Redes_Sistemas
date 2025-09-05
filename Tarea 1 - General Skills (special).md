RETO:
Special

DESCRIPCION:
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)Start your instance to see connection details.`ssh -p 62804 ctf-player@saturn.picoctf.net`The password is `483e80d4`

SOLUCION:
- Me conecté a la instancia mediante SSH usando los datos proporcionados:

`ssh -p 51062 ctf-player@saturn.picoctf.net Password: 483e80d4`

- Al intentar ejecutar comandos normales como `ls`, `cat` o `/bin/cat`, el shell devolvía mensajes como:

`sh: 1: Is: not found Absolutely not paths like that, please!`

- Inspeccionando el directorio encontré la ruta de la flag: `./blargh/flag.txt`.

- Debido a la interfaz “spell-checked”, escribí el comando combinado:

`clear & cat ./blargh/flag.txt`

- Esto permitió ejecutar correctamente la acción y mostrar la flag.

**SOLUCION:** `picoCTF{5p311ch3ck_15_7h3_w0r57_b741d1b1}`

NOTAS ADICIONALES:
- El shell Special no acepta mayúsculas o rutas completas de forma tradicional.
- Combinar comandos con `&` y usar nombres de archivos en minúscula funcionó para ejecutar `cat`.
- Aprendí que algunos retos de terminal modifican la interpretación de comandos para agregar dificultad.

REFERENCIAS:
https://www.ssh.com/academy
