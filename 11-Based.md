RETO:
Based.

DESCRIPCION:
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29221`.

SOLUCION:
- Se reciben distintos valores codificados (binario, decimal, hexadecimal).

- Se convierten a texto usando Python o manualmente:
    
    - Binario → ASCII
    
    - Decimal → ASCII
    
    - Hexadecimal → ASCII
    
- Se ingresan las palabras convertidas en el prompt del servidor.

- Tras completar todas las conversiones, el servidor entrega la flag.

**SOLUCION:** `picoCTF{learning_about_converting_values_00a975ff}

NOTAS ADICIONALES:
- Es importante reconocer el tipo de codificación antes de convertir.

- Python puede ayudar con conversiones rápidas:

REFERENCIAS:
- https://www.asciitable.com/

- https://www.rapidtables.com/convert/number/binary-to-ascii.html

- https://www.rapidtables.com/convert/number/hex-to-ascii.html