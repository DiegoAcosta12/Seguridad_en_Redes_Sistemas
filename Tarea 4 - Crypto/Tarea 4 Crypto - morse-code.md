**RETO:** morse-code

**DESCRIPCION:**  
Morse code is well known. Can you decrypt this?

**SOLUCION:**

- Descargué el archivo morse_chal.wav
    
- Analicé el código Morse del archivo de audio
    
- El mensaje decodificado fue: `WH47 H47H 90D W20 U9H7`
    
- Convertí el texto a minúsculas: `wh47 h47h 90d w20 u9h7`
    
- Reemplacé espacios con guiones bajos: `wh47_h47h_90d_w20_u9h7`
    
- Envolví en formato picoCTF{}
    

**Comandos:**

bash

wget https://artifacts.picoctf.net/c/79/morse_chal.wav

**Flag:** `picoCTF{wh47_h47h_90d_w20_u9h7}`

**NOTAS:**

- El código Morse usa puntos (cortos) y rayas (largos) para representar caracteres
    
- Los números en Morse siguen un patrón específico de 5 símbolos
    
- El formato requería minúsculas y guiones bajos en lugar de espacios
    
- No se necesitaron herramientas especializadas, solo conocimiento del código Morse y el formato requerido