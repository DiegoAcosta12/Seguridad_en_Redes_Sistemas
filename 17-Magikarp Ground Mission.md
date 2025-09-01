RETO:
Magikarp Ground Mission.

DESCRIPCION:
Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `6d448c9c`

Additional details will be available after launching your challenge instance.

SOLUCION:
1. Conectamos por SSH al servidor del reto:

`ssh ctf-player@venus.picoctf.net -p 55128`

2. Al entrar, listamos los archivos en el directorio inicial:

`ls -l`

Encontramos:

- `1of3.flag.txt`

- `instructions-to-2of3.txt`

3. Leemos la primera parte de la flag:

`cat 1of3.flag.txt`

Salida:

`picoCTF{xxsh_`

4. Leemos las instrucciones para la segunda parte:

`cat instructions-to-2of3.txt`

Salida:

`` Next, go to the root of all things, more succinctly `/` ``

5. Vamos al directorio raíz `/` y listamos:

`cd / ls`

Encontramos `2of3.flag.txt` y `instructions-to-3of3.txt`.

6. Leemos la segunda parte de la flag:

`cat 2of3.flag.txt`

Salida:

`0ut_0f_\/\/4t3r_`

7. Revisamos las instrucciones finales:

`cat instructions-to-3of3.txt`

Salida:

`` Lastly, ctf-player, go home... more succinctly `~` ``

8. Vamos al home `~` y listamos:

`cd ~ ls`

Encontramos `3of3.flag.txt`.

9. Leemos la última parte de la flag:

`cat 3of3.flag.txt`

Salida:

`5190b070}`

10. Unimos todas las partes:

**SOLUCION:**`picoCTF{xxsh_0ut_0f_\/\/4t3r_5190b070}`

NOTAS ADICIONALES:
- Este reto enseña lo básico de navegar en el sistema de archivos de Linux (`cd`, `ls`, `cat`, `pwd`).
- `~` es un alias para el directorio **home** del usuario.

REFERENCIAS:
No use ninguna pagina externa a la terminal de CTF.