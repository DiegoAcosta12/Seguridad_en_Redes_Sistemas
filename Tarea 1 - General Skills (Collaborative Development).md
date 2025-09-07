RETO:
Collaborative Development.

DESCRIPCION:
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/178/challenge.zip)

SOLUCION:
1. Descargué el archivo `challenge.zip` y lo descomprimí.
    
2. Navegué al directorio `drop-in` y examiné las ramas del repositorio Git.
    
3. Usé `git log --oneline --all` para ver los commits en todas las ramas.
    
4. Inspeccioné los commits en las ramas `feature/part-1`, `feature/part-2` y `feature/part-3` con `git show <commit-hash>`.
    
5. Encontré las tres partes de la flag en los cambios realizados en el archivo `flag.py`.
    

**SOLUCION:`picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_6c06cec1}`

NOTAS ADICIONALES:
- Las flags estaban divididas en tres ramas de características (`feature/part-1`, `feature/part-2`, `feature/part-3`).
    
- Cada rama agregaba una parte de la flag al archivo `flag.py`.
    
- La flag completa se forma concatenando las tres partes.

REFERENCIAS
- [Git Branching](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)