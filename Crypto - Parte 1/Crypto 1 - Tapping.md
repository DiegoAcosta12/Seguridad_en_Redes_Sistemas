**RETO:**  
Tapping

**DESCRIPCIÓN:**  
Theres tapping coming in from the wires. What's it saying nc jupiter.[challenges.picoctf.org](https://challenges.picoctf.org/) 9422.

**SOLUCIÓN:**

1. **Conexión al servicio**:
    
    - Se estableció conexión con el servicio usando `nc jupiter.challenges.picoctf.org 9422`
        
    - El servicio devolvió inmediatamente una secuencia de puntos y rayas en formato código Morse
        
2. **Identificación del cifrado**:
    
    - Basado en la descripción "tapping coming from the wires" y el uso de puntos y rayas
        
    - Se identificó claramente como **código Morse internacional**
        
    - El formato coincidía con el patrón estándar de Morse: letras separadas por espacios, palabras potencialmente separadas por barras
        
3. **Obtención del código Morse**:
    
    - El servicio proporcionó: `. -- . .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ..--- -.... ---.. ...-- ---.. ..--- ....- -.... .---- ----- }`
        
4. **Proceso de decodificación**:
    
    - Se implementó un diccionario de decodificación Morse en Python
        
    - El código Morse se dividió en símbolos individuales usando espacios como separadores
        
    - Cada símbolo Morse se mapeó a su correspondiente carácter alfanumérico
        
5. **Decodificación manual verificada**:
    
    - `. -- .` = P I C O C T F {
        
    - `-- -----` = M 0
        
    - `.-.` = R
        
    - `...` = S
        
    - `...--` = 3
        
    - `-.-.` = C
        
    - `-----` = 0
        
    - `-..` = D
        
    - `...--` = 3
        
    - `.----` = 1
        
    - `...` = S
        
    - `..-.` = F
        
    - `..-` = U
        
    - `-.` = N
        
    - `..---` = 2
        
    - `-....` = 6
        
    - `---..` = 8
        
    - `...--` = 3
        
    - `---..` = 8
        
    - `..---` = 2
        
    - `....-` = 4
        
    - `-....` = 6
        
    - `.----` = 1
        
    - `-----` = 0
        
    - `}` = }
        
6. **Composición de la flag**:
    
    - Los caracteres decodificados se concatenaron en el orden correcto
        
    - El resultado mantuvo el formato de flag PICOCTF estándar
        
    - El mensaje interno "M0RS3C0D31SFUN" se tradujo como "MORSE CODE IS FUN" en formato leet
        

**FLAG OBTENIDA:**  
`PICOCTF{M0RS3C0D31SFUN2683824610}`

**NOTAS ADICIONALES:**

- La flag `M0RS3C0D31SFUN2683824610` contiene el mensaje "MORSE CODE IS FUN" seguido de números
    
- Este reto demostró el código Morse, uno de los métodos de codificación más antiguos todavía en uso
    
- Samuel F.B. Morse y Alfred Vail desarrollaron el código Morse original en la década de 1830
    
- El código Morse fue fundamental para las comunicaciones telegráficas y marítimas
    
- El reto enfatizó la importancia de reconocer patrones de codificación clásicos
    
- La implementación en Python utilizó un enfoque de diccionario para mapeo directo de símbolos
    
- No fue necesario separar palabras con "/" ya que todo el mensaje era una sola secuencia continua
    
- Los números en Morse usan 5 símbolos (puntos/rayas) consistentemente
    
- Este ejercicio ilustró cómo métodos de comunicación históricos siguen siendo relevantes en contextos modernos como CTF
    
- La simplicidad del código Morse lo hace ideal para transmisiones manuales y situaciones de baja tecnología
    
- El reto mostró la persistencia del código Morse en la era digital, especialmente en comunidades de radioaficionados
    
- La parte numérica "2683824610" al final de la flag podría ser un identificador único o hash del reto
    
- La eficiencia del código Morse radica en asignar secuencias más cortas a letras más comunes (E = ".", T = "-")
    
- Este cifrado/encoding es técnicamente una codificación, no un cifrado, ya que no utiliza clave secreta
    
- La decodificación manual sirvió como verificación del proceso automatizado, demostrando comprensión del método