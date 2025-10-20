**RETO:**  
la cifra de

**DESCRIPCIÓN:**  
I found this cipher in an old book. Can you figure out what it says? Connect with nc jupiter.[challenges.picoctf.org](https://challenges.picoctf.org/) 5726.

**SOLUCIÓN:**

1. **Conexión y obtención del texto cifrado**:
    
    - Se estableció conexión con el servicio usando `nc jupiter.challenges.picoctf.org 5726`
        
    - Se obtuvo un texto cifrado extenso que contenía referencias históricas y una flag en formato `CZK{m311a50_0x_a1rn3x3_h1ah3x6kp60egf}`
        
2. **Análisis inicial del cifrado**:
    
    - El texto contenía acentos (`è`) y nombres que sugerían un contexto histórico criptográfico
        
    - Las referencias a "Bnretèwp Cousex", "Volpnèxj", y fechas como 1553, 1467 indicaban relación con cifrados históricos
        
    - La presencia de `CZK{...}` en lugar de `picoCTF{...}` confirmó que todo el texto estaba cifrado
        
3. **Identificación del método de cifrado**:
    
    - Las pistas "looking at history" y "there are tools that make this easy" sugirieron el cifrado Vigenère
        
    - Se probaron múltiples claves históricas relacionadas con el cifrado Vigenère
        
    - **La clave "FLAG"** resultó ser la correcta para descifrar el texto principal
        
4. **Proceso de descifrado**:
    
    - Se aplicó el descifrado Vigenère con clave "FLAG" al texto completo
        
    - El texto principal se descifró correctamente, revelando un ensayo histórico sobre el cifrado Vigenère
        
    - Sin embargo, la flag interna `CZK{m311a50_0x_a1rn3x3_h1ah3x6kp60egf}` no producía resultados coherentes con la misma clave
        
5. **Uso de herramientas especializadas**:
    
    - Se utilizó **CyberChef** ([https://gchq.github.io/CyberChef/](https://gchq.github.io/CyberChef/)) para verificar el descifrado
        
    - Al aplicar "Vigenère Decode" con clave "FLAG" en CyberChef, se obtuvo la flag correcta
        
    - La discrepancia se debió probablemente a diferencias en la implementación del algoritmo
        
6. **Verificación del resultado**:
    
    - El texto descifrado hablaba sobre la historia del cifrado Vigenère y su atribución incorrecta
        
    - La flag contenía una referencia al cifrado en formato leet: "b311a50_0r_v1gn3r3_c1ph3r" = "bellaso or vigenere cipher"
        

**FLAG OBTENIDA:**  
`picoCTF{b311a50_0r_v1gn3r3_c1ph3r6fe60eaa}`

**NOTAS ADICIONALES:**

- La flag `b311a50_0r_v1gn3r3_c1ph3r6fe60eaa` hace referencia al debate histórico sobre la invención del cifrado Vigenère
    
- Giovan Battista Bellaso describió originalmente el cifrado en 1553, pero fue incorrectamente atribuido a Blaise de Vigenère
    
- Este reto demostró la importancia de verificar resultados con múltiples herramientas cuando hay discrepancias
    
- El uso de CyberChef fue crucial para resolver la discrepancia entre la implementación de Python y el resultado esperado
    
- El reto enfatizó el valor de las herramientas de criptografía online para verificación y debugging
    
- La presencia de acentos y caracteres especiales en el texto cifrado añadió complejidad al desafío
    
- El contexto histórico proporcionado en el texto descifrado fue educacionalmente valioso sobre los orígenes de la criptografía
    
- La flag final en formato leet (b311a50 = bellaso, v1gn3r3 = vigenere, c1ph3r = cipher) fue coherente con el tema del reto
    
- Este ejercicio ilustró cómo problemas aparentemente simples pueden tener complejidades inesperadas en implementación
    
- La importancia de la perseverancia y el uso de múltiples enfoques en la resolución de desafíos criptográficos
    
- El reto combinó habilidades técnicas (criptoanálisis) con conocimiento histórico (orígenes del cifrado Vigenère)
    
- La lección final: cuando un método no produce resultados esperados, es valioso probar herramientas alternativas para verificación