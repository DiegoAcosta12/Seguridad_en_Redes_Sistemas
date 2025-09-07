RETO:
Blame game.

DESCRIPCION:
Someone's commits seems to be preventing the program from working. Who is it?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/73/challenge.zip)

SOLUCION:
1. Descargué el archivo `challenge.zip` desde el enlace proporcionado:  
    `wget https://artifacts.picoctf.net/c_titan/73/challenge.zip`
    
2. Descomprimí el archivo y navegué al directorio `blob-game/drop-in` donde se encontraba el repositorio Git.
    
3. Utilicé el comando `git log --oneline --pretty=format:"%h %an %s"` para revisar el historial de commits con detalles de autores y mensajes.
    
4. Identifiqué el commit problemático (posiblemente con un mensaje que indicaba un cambio dañino o error).
    
5. La flag era el nombre de usuario del autor de ese commit, en formato `picoCTF{username}`.
    
 
**SOLUCION:**`picoCTF{@sk_th3_1nt3rn_e9957ce1}`

NOTAS ADICIONALES:
- El comando `git blame` también puede ser útil para rastrear cambios línea por línea en archivos específicos.
    
- La flag encontrada sugiere que el autor del commit problemático era `@sk_th3_1nt3rn` (posiblemente un usuario interno o simulado).

REFERENCIAS:
- [Git Blame Documentation](https://git-scm.com/docs/git-blame)
    
- [PicoCTF Git Challenges](https://play.picoctf.org/practice?category=1&page=1)