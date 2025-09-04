RETO: 
Super SSH.

DESCRIPCION:
Using a Secure Shell (SSH) is going to be pretty important.
Additional details will be available after launching your challenge instance.

SOLUCION:
En este reto tenía que conectarme a un servidor usando **SSH** para obtener la flag. Me dieron el usuario `ctf-player`, la contraseña `6abf4a82`, el host `titan.picoctf.net` y el puerto `64056`. 

- Abrí mi terminal (o el WebShell de picoCTF) y ejecuté:

`ssh ctf-player@titan.picoctf.net -p 64056`

- Acepté la huella digital escribiendo `yes` cuando me lo pidió.
- Ingresé la contraseña `6abf4a82`.
- Al conectarme, el servidor me mostró directamente la flag en el mensaje de bienvenida.

**SOLUCIÓN:** `picoCTF{s3cur3_c0nn3ct10n_65a7a106}`.

NOTAS ADICIONALES:
- Aprendí que a veces SSH puede mostrar la flag directamente al conectarse, sin necesidad de buscar archivos.
- El parámetro `-p` sirve para conectarse a un puerto distinto del 22 por defecto.
- Las contraseñas no se muestran al escribirlas, así que hay que teclear con cuidado.

REFERENCIAS:
https://linux.die.net/man/1/ssh
