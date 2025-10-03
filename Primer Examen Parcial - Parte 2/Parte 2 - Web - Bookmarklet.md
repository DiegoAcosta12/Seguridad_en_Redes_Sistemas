**RETO:**  
Bookmarklet

**DESCRIPCIÓN:**  
Why search for the flag when I can make a bookmarklet to print it for me? Browse here, and find the flag!  
[http://titan.picoctf.net:52739/](http://titan.picoctf.net:52739/)

**SOLUCIÓN:**

1. **Análisis inicial del sitio web**:
    
    - Accedí al sitio web proporcionado: `http://titan.picoctf.net:52739/`
        
    - Inspeccioné el código fuente de la página (Ctrl+U)
        
    - Identifiqué un área de texto con código JavaScript que contenía un bookmarklet predefinido
        
2. **Identificación del mecanismo de flag**:
    
    - El código contenía una flag encriptada: `"àÒÆÞ¦È¬ëÙ£ÖÓÚåÛÑ¢ÕÓÉÕËÆÒÇÚËí"`
        
    - Utilizaba una clave de descifrado: `"picoctf"`
        
    - Implementaba un algoritmo de descifrado que realizaba operaciones aritméticas con los caracteres
        
3. **Ejecución del algoritmo de descifrado**:
    
    - Copié el código JavaScript directamente desde el área de texto en la página
        
    - Ejecuté el código en la consola del navegador (F12 → Console)
        
    - El algoritmo realizó el siguiente proceso:
        
        javascript
        
        for (var i = 0; i < encryptedFlag.length; i++) {
            decryptedFlag += String.fromCharCode(
                (encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256
            );
        }
        
4. **Obtención de la flag**:
    
    - El código ejecutado mostró una alerta con la flag descifrada
        
    - La flag fue revelada exitosamente
        

**FLAG OBTENIDA:**  
`picoCTF{p@g3_turn3r_cebccdfe}`

**NOTAS ADICIONALES:**

- La flag `p@g3_turn3r` hace referencia a Grace Hopper, pionera en programación que popularizó el término "debugging"
    
- Este reto demuestra cómo el código JavaScript en el cliente puede contener información ofuscada
    
- El algoritmo utilizaba una técnica simple de cifrado por sustracción con wraparound
    
- El bookmarklet proporcionado era funcional, pero ejecutar el código directamente en consola resultó más eficiente
    
- La solución no requirió crear un bookmarklet físico, solo entender y ejecutar el algoritmo de descifrado
    

**CÓDIGO UTILIZADO:**

javascript

var encryptedFlag = "àÒÆÞ¦È¬ëÙ£ÖÓÚåÛÑ¢ÕÓÉÕËÆÒÇÚËí";
var key = "picoctf";
var decryptedFlag = "";
for (var i = 0; i < encryptedFlag.length; i++) {
    decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);
}
alert(decryptedFlag);