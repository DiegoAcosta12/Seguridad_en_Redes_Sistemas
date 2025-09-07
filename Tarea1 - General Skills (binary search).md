RETO:
Binary search.

DESCRIPCION:
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/18/challenge.zip)

`ssh -p 61614 ctf-player@atlas.picoctf.net`Using the password `84b12bae`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!

SOLUCION:
1. Me conecté al servidor mediante SSH utilizando el comando proporcionado:  
    `ssh -p 61614 ctf-player@atlas.picoctf.net`  
    Contraseña: `84b12bae`
    
2. Al iniciar el juego, el programa indicó que debía adivinar un número entre 1 y 1000 con solo 10 intentos.
    
3. Apliqué el algoritmo de **búsqueda binaria** manualmente:
    
    - **Intento 1:** 500 → "Lower" (el número es menor que 500).
        
    - **Intento 2:** 250 → "Higher" (el número es mayor que 250).
        
    - **Intento 3:** 375 → "Higher" (el número es mayor que 375).
        
    - **Intento 4:** 437 → "Higher" (el número es mayor que 437).
        
    - **Intento 5:** 468 → "Lower" (el número es menor que 468).
        
    - **Intento 6:** 452 → "Higher" (el número es mayor que 452).
        
    - **Intento 7:** 460 → "Lower" (el número es menor que 460).
        
    - **Intento 8:** 456 → "Lower" (el número es menor que 456).
        
    - **Intento 9:** 454 → "Higher" (el número es mayor que 454).
        
    - **Intento 10:** 455 → ¡Correcto!
        
4. Al adivinar el número correcto (455), el programa mostró la flag.
    


**SOLUCION:**`picoCTF{g00d_gu355_2e90d29b}`

NOTAS ADICIONALES:
- La búsqueda binaria es eficiente para listas ordenadas, reduciendo el espacio de búsqueda a la mitad en cada intento.
    
- Con 10 intentos es posible encontrar un elemento entre 1000 (2^10 = 1024 > 1000).
    
- Este ejercicio simula la necesidad de analizar grandes volúmenes de datos en seguridad cibernética de manera optimizada.

REFERENCIAS:
- [Binary Search Algorithm](https://en.wikipedia.org/wiki/Binary_search_algorithm)
