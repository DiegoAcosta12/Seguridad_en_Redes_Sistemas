RETO:
Time Machine

DESCRIPCION:
What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/161/challenge.zip)

SOLUCION:
1. Descargué el archivo `challenge.zip` desde el enlace proporcionado:  
    `wget https://artifacts.picoctf.net/c_titan/161/challenge.zip`
    
2. Descomprimí el archivo:  
    `unzip challenge.zip`  
    Esto creó un directorio `drop-in` con un repositorio Git.
    
3. Navegué al directorio y examiné el historial de commits:
    
    bash
    
    Copy
    
    Download
    
    cd drop-in
    git log --oneline
    
4. Identifiqué un commit relevante (con hash `3d5ec8a`) que contenía cambios sospechosos. Usé `git show` para inspeccionarlo:  
    `git show 3d5ec8a`
    
5. En el mensaje del commit y los cambios realizados, encontré la flag:  
    `picoCTF{t1m3m@ch1n3_8defe16a}`
    
  
**SOLUCION:** `picoCTF{t1m3m@ch1n3_8defe16a}`

NOTAS ADICIONALES:
- Los retos que involucran Git suelen esconder flags en el historial de commits, ya sea en mensajes o en cambios de archivos.
    
- Comandos útiles: `git log`, `git show <hash>`, `git diff`, `git checkout` para explorar versiones anteriores.
    
- Asegurarse de que el repositorio se haya descomprimido correctamente y de que el directorio `.git` esté presente.

REFERENCIAS:
- [Git Documentation](https://git-scm.com/doc)
- [PicoCTF Git Challenges](https://play.picoctf.org/practice?category=1&page=1)