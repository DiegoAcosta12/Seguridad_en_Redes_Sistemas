RETO:
Commitment Issues

DESCRIPCION:
I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/77/challenge.zip)


SOLUCION:
- Descargué y descomprimí el archivo `challenge.zip`:
    `unzip challenge.zip -d challenge cd challenge/drop-in`
- Revisé que existiera un repositorio de Git oculto con:
    `ls -a`
    
    Allí estaba la carpeta `.git`.
- Exploré el historial de commits con:
    `git log --oneline`
    
    Encontré un commit inicial que parecía contener el archivo con la flag.
- Inspeccioné ese commit usando:
    `git show <ID_DEL_COMMIT>`
    
    Dentro del archivo `message.txt` se revelaba la flag.

 
**SOLUCION:**`picoCTF{s@n1t1z3_30e86d36}`

NOTAS ADICIONALES:
- El archivo `message.txt` había sido borrado en un commit posterior, pero Git conserva el historial, lo que permitió recuperarlo.
- Esta técnica de revisar commits antiguos es muy útil en auditorías de seguridad y pruebas forenses.

REFERENCIAS:
- [Git documentation](https://git-scm.com/doc)
- [Git log command](https://git-scm.com/docs/git-log)
