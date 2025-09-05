RETO:
Convertme.py.

DESCRIPCION:
Run the Python script and convert the given number from decimal to binary to get the flag.[Download Python script](https://artifacts.picoctf.net/c/24/convertme.py)

SOLUCION:
- Descargué el script y lo abrí para revisar cómo funcionaba.

- El script me daba el número **44 en decimal** y pedía convertirlo a binario.

- Convertí 44 a binario paso a paso:

`44 ÷ 2 = 22 → residuo 0 22 ÷ 2 = 11 → residuo 0 11 ÷ 2 = 5  → residuo 1 5  ÷ 2 = 2  → residuo 1 2  ÷ 2 = 1  → residuo 0 1  ÷ 2 = 0  → residuo 1`

- Leyendo los residuos de abajo hacia arriba: `101100`.

- Esto me permitió obtener la flag.

**SOLUCION:** `picoCTF{4ll_y0ur_b4535_722f6b39}`

NOTAS ADICIONALES:
- Revisar el script antes de ejecutarlo ayuda a entender qué cálculo o conversión se requiere.
- Python facilita la conversión de decimal a binario con la función `bin()`.
- Paso a paso con división sucesiva también funciona para cualquier número.

REFERENCIAS:
No use paginas externas.