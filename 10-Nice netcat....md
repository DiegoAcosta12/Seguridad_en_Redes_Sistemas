RETO:
Nice netcat...

DESCRIPCION:
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 7449`, but it doesn't speak English...

SOLUCION:
Use la terminal de la pagina, puse el comando que me otorgo el reto y me arrojo una serie de números.
En lugar de leer los números uno por uno, podemos usar **Python** para convertir todos los códigos ASCII a caracteres de forma rápida:

nums [112,105,99,111,67,84,70,123,103,48,48,100,95,107,49,116,116,121,33,95,110,49,99,51,95,107,49,116,116,121,33,95,102,50,100,55,99,97,102,97,125]
flag = ''.join([chr(n) for n in nums]) 
print(flag)


Esto imprimirá la flag directamente.

**SOLUCION:** `picoCTF{g00d_k1tty!_n1c3_k1tty!_f2d7cafa}

NOTAS ADICIONALES:
- Cada número recibido del programa representa un carácter en ASCII.

- Usar Python para mapear `chr(numero)` es una forma rápida y confiable de reconstruir el texto.

- Este método se puede usar para cualquier reto que convierta ASCII a texto.

REFERENCIAS:
https://linux.die.net/man/1/nc
https://docs.python.org/3/library/functions.html?utm_source=chatgpt.com#chr
https://www.asciitable.com/?utm_source=chatgpt.com