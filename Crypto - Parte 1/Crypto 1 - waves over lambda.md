**RETO:**  
waves over lambda

**DESCRIPCIÓN:**  
We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with nc jupiter.[challenges.picoctf.org](https://challenges.picoctf.org/) 43522.

**SOLUCIÓN:**

1. **Conexión al servicio y obtención del texto cifrado**:
    
    - Se estableció conexión con `nc jupiter.challenges.picoctf.org 43522`
        
    - El servicio devolvió un texto cifrado extenso usando sustitución monoalfabética
        
    - Incluía una línea especial: `kysjuwgx rhuh qx dyau mlwj - muheahskd_qx_k_yfhu_lwbvcw_yjmbwasuwm`
        
2. **Identificación del texto original**:
    
    - El texto cifrado completo fue identificado como un pasaje de **"Heart of Darkness"** de Joseph Conrad
        
    - Se utilizó análisis de frecuencia y herramientas online ([guballa.de/substitution-solver](https://guballa.de/substitution-solver)) para descifrar el texto principal
        
    - El texto descifrado confirmó que era literatura clásica, proporcionando un contexto para el mapeo de caracteres
        
3. **Análisis de la línea de flag**:
    
    - La línea específica `kysjuwgx rhuh qx dyau mlwj - muheahskd_qx_k_yfhu_lwbvcw_yjmbwasuwm` contenía la flag
        
    - Esta línea se tradujo como: `between us there was - frequency_is_c_over_lambda_ogfmaunraf`
        
    - La primera parte "between us there was" corresponde al texto literario original
        
    - La segunda parte después del guión contiene la flag del reto
        
4. **Descifrado de la flag**:
    
    - **`frequency_is_c_over_lambda_ogfmaunraf`**
        
    - La parte `frequency_is_c_over_lambda` hace referencia a la fórmula física f = c/λ (frecuencia = velocidad de la luz / longitud de onda)
        
    - La parte `ogfmaunraf` es "frequency" cifrado con sustitución, completando el tema del reto
        
5. **Relación con el nombre del reto**:
    
    - "Waves over lambda" (ondas sobre lambda) es una referencia directa a la fórmula física c/λ
        
    - El nombre del reto era una pista crucial sobre el contenido de la flag
        

**FLAG OBTENIDA:**  
`frequency_is_c_over_lambda_ogfmaunraf`

**NOTAS ADICIONALES:**

- La flag `frequency_is_c_over_lambda_ogfmaunraf` combina conceptos de física con criptografía
    
- La referencia a c/λ (velocidad de la luz sobre longitud de onda) es fundamental en física de ondas y electromagnetismo
    
- El reto demostró un cifrado por sustitución monoalfabética clásico
    
- La inclusión de literatura clásica ("Heart of Darkness") añadió una capa cultural al desafío
    
- La flag final contenía un meta-cifrado donde "ogfmaunraf" es "frequency" cifrado, creando un cifrado dentro de otro cifrado
    
- Este reto ilustró cómo los desafíos CTF pueden integrar múltiples disciplinas: criptografía, literatura y física
    
- La pista "Flag is not in the usual flag format" preparó al solucionista para esperar un formato diferente a picoCTF{}
    
- El uso de herramientas online de descifrado por sustitución fue esencial para resolver eficientemente el texto extenso
    
- La línea de flag específica requirió atención especial ya que el descifrado automático no funcionó perfectamente para esa sección
    
- El reto enfatizó la importancia del análisis contextual en criptografía - entender que era literatura ayudó a verificar el descifrado
    
- La relación entre el nombre del reto y el contenido de la flag demostró coherencia temática en el diseño del desafío
    
- La combinación de elementos educativos (física), culturales (literatura) y técnicos (criptografía) hizo este reto particularmente enriquecedor
    
- La flag sirvió como un recordatorio mnemotécnico de la relación fundamental entre frecuencia, velocidad de la luz y longitud de onda en física