RETO:
Repetitions.

DESCRIPCION:
Can you make sense of this file?Download the file [here](https://artifacts.picoctf.net/c/472/enc_flag).

SOLUCION:
La cadena dentro del archivo está codificada en **Base64 varias veces anidadas**. La estrategia fue decodificar repetidamente Base64 hasta que la salida dejó de ser Base64 y apareció la flag legible.

Decodificar automáticamente en un bucle (Python, funciona sin instalar paquetes extra):
`python3 - <<'PY' import base64 s = open('repetitions.txt','rb').read() while True:     try:         s2 = base64.b64decode(s)         # si la decodificación no cambia, salimos         if s2 == s:             break         s = s2     except Exception:         break print(s.decode(errors='ignore')) PY`

**SOLUCION:** `picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_73494190}`

NOTAS ADICIONALES:
- Cuando veas cadenas compuestas por caracteres A–Z, a–z, 0–9, `+`, `/` y `=` al final, sospecha **Base64**.
- “Multiple decoding is always good” indica anidamiento: decodifica varias veces.
- Si no sabes cuántas capas hay, usar un pequeño script (Python o shell) para intentar decodificar en bucle es la forma más fiable.

REFERENCIAS:
- Python `base64` module: https://docs.python.org/3/library/base64.html