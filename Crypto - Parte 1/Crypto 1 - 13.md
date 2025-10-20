**RETO:**  
The numbers

**DESCRIPCIÓN:**  
Cryptography can be easy, do you know what ROT13 is? cvpbPGS{abg_gbb_onq_bs_n_ceboyrz}

**SOLUCIÓN:**

1. **Identificación del cifrado**:
    
    - El reto menciona explícitamente ROT13, que es un cifrado de sustitución simple
        
    - ROT13 desplaza cada letra 13 posiciones en el alfabeto
        
    - Es un cifrado recíproco: aplicar ROT13 dos veces devuelve el texto original
        
2. **Análisis del texto cifrado**:
    
    - Texto proporcionado: `cvpbPGS{abg_gbb_onq_bs_n_ceboyrz}`
        
    - El formato sugiere que está en el patrón típico de flags: `picoCTF{...}`
        
    - Las letras `cvpbPGS` deberían corresponder a `picoCTF` después de ROT13
        
3. **Proceso de descifrado**:
    
    - Se aplicó ROT13 carácter por carácter:
        
        - `c` → `p`
            
        - `v` → `i`
            
        - `p` → `c`
            
        - `b` → `o`
            
        - `P` → `C`
            
        - `G` → `T`
            
        - `S` → `F`
            
        - `{` → `{` (sin cambios)
            
        - `abg_gbb_onq_bs_n_ceboyrz` → `not_too_bad_of_a_problem`
            
        - `}` → `}` (sin cambios)
            
4. **Métodos de descifrado utilizados**:
    
    - **Método manual**: Aplicando ROT13 manualmente usando el alfabeto
        
    - **Método Python**: Usando la librería codecs integrada
        
    - **Método terminal**: Usando el comando `tr` en sistemas Unix
        
5. **Verificación del resultado**:
    
    - El texto descifrado mantiene el formato correcto de flag: `picoCTF{...}`
        
    - El mensaje "not_too_bad_of_a_problem" tiene sentido en el contexto del reto
        
    - Se verificó que aplicar ROT13 al resultado devuelve el texto original
        

**FLAG OBTENIDA:**  
`picoCTF{not_too_bad_of_a_problem}`

**NOTAS ADICIONALES:**

- La flag `not_too_bad_of_a_problem` refleja apropiadamente la naturaleza simple del cifrado ROT13
    
- ROT13 es más una codificación que un cifrado seguro, ya que no utiliza clave secreta
    
- Este cifrado fue popular en foros de internet para ocultar spoilers o respuestas sin proporcionar seguridad real
    
- El reto demostró un concepto fundamental en criptografía: cifrados por sustitución
    
- ROT13 preserva mayúsculas/minúsculas y caracteres no alfabéticos, lo que es útil para mantener el formato
    
- La naturaleza recíproca de ROT13 (ROT13(ROT13(text)) = text) lo hace fácil de implementar
    
- Este ejercicio sirvió como introducción a conceptos criptográficos básicos
    
- El reto enfatizó que no todos los problemas de criptografía son complejos; algunos tienen soluciones simples
    
- La herramienta `tr` en Unix/Linux es particularmente útil para este tipo de transformaciones de caracteres
    
- Python proporciona una implementación nativa de ROT13 a través del módulo codecs, demostrando la integración de herramientas criptográficas básicas en lenguajes de programación modernos
    
- El formato de la flag seguía el patrón estándar, haciendo reconocible inmediatamente cuando se había aplicado correctamente el descifrado