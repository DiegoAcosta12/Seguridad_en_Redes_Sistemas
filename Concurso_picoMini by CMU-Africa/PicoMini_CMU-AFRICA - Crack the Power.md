### **RETO:** Crack the Power

**DESCRIPCIÓN:**  
We received an encrypted message. The modulus is built from primes large enough that factoring them isn't an option, at least not today. See if you can make sense of the numbers and reveal the flag.

**SOLUCIÓN:**

1. **Análisis inicial**:
    
    - Cifrado RSA con parámetros: n (módulo grande), e=20, c (texto cifrado)
        
    - Módulo n demasiado grande para factorizar
        
    - Exponente público e inusualmente pequeño (e=20)
        
2. **Proceso de resolución**:
    
    - Se identificó que e=20 es muy pequeño para RSA estándar
        
    - Se aplicó Low Exponent Attack (ataque de exponente bajo)
        
    - Se calculó directamente m = c^(1/e) usando raíz e-ésima
        
    - Como m^e < n, no se necesitó el módulo n para descifrar
        
    - El mensaje se convirtió de número a texto
        
3. **Descubrimiento clave**:
    
    - Cuando e es pequeño y m^e < n, se puede calcular m directamente
        
    - No se necesitó factorizar n ni calcular claves privadas
        
    - gmpy2.iroot(c, e) devolvió la raíz exacta
        
    - La conversión a bytes reveló la flag
        

**FLAG OBTENIDA:**  
`picoCTF{t1ny_e_46e014ec}`

**REFERENCIAS:**

- Técnica: Low Exponent Attack (RSA con e pequeño)
    
- Herramientas: Python, gmpy2
    
- Script:
    
    python
    
    import gmpy2
    from Crypto.Util.number import long_to_bytes
    m, exact = gmpy2.iroot(c, e)
    flag = long_to_bytes(int(m))
    
- Parámetros: e=20, n y c del archivo message.txt