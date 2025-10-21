**RETO:**  
rsa-pop-quiz

**DESCRIPCIÓN:**  
Class, take your seats! It's PRIME-time for a quiz...

**SOLUCIÓN:**

1. **Conexión al servicio y estructura del quiz**:
    
    - Se estableció conexión con `nc jupiter.challenges.picoctf.org 18821`
        
    - El servicio presentó un quiz interactivo sobre conceptos fundamentales de RSA
        
    - Cada problema requería determinar si era posible y factible producir un valor específico dados ciertos parámetros
        
2. **Problema 1: Cálculo de n**:
    
    - **Datos**: p = 76753, q = 60413
        
    - **Solicitado**: n
        
    - **Solución**: n = p × q = 4636878989
        
    - **Respuesta**: Y (Sí es posible y factible)
        
3. **Problema 2: Cálculo de q**:
    
    - **Datos**: p = 54269, n = 5051846941
        
    - **Solicitado**: q
        
    - **Solución**: q = n ÷ p = 93089
        
    - **Respuesta**: Y (Sí es posible y factible)
        
4. **Problema 3: Factorización de n grande**:
    
    - **Datos**: e = 3, n de 2048 bits
        
    - **Solicitado**: p y q
        
    - **Solución**: No es factible factorizar n de 2048 bits con tecnología actual
        
    - **Respuesta**: N (No es factible)
        
5. **Problema 4: Cálculo de φ(n)**:
    
    - **Datos**: p = 12611, q = 66347
        
    - **Solicitado**: φ(n)
        
    - **Solución**: φ(n) = (p-1)(q-1) = 836623060
        
    - **Respuesta**: Y (Sí es posible y factible)
        
6. **Problema 5: Cifrado RSA**:
    
    - **Datos**: plaintext, e = 3, n grande
        
    - **Solicitado**: ciphertext
        
    - **Solución**: c = mᵉ mod n = 256931246631782714357241556582441991993437399854161372646318659020994329843524306570818293602492485385337029697819837182169818816821461486018802894936801257629375428544752970630870631166355711254848465862207765051226282541748174535990314552471546936536330397892907207943448897073772015986097770443616540466471245438117157152783246654401668267323136450122287983612851171545784168132230208726238881861407976917850248110805724300421712827401063963117423718797887144760360749619552577176382615108244813
        
    - **Respuesta**: Y (Sí es posible y factible)
        
7. **Problema 6: Ataque de raíz cúbica**:
    
    - **Datos**: ciphertext, e = 3, n grande
        
    - **Solicitado**: plaintext
        
    - **Solución**: No es posible descifrar directamente con raíz cúbica (m³ > n o hay padding)
        
    - **Respuesta**: N (No es factible)
        
8. **Problema 7: Cálculo de clave privada d**:
    
    - **Datos**: p, q, e = 65537
        
    - **Solicitado**: d
        
    - **Solución**:
        
        - φ(n) = (p-1)(q-1)
            
        - d = e⁻¹ mod φ(n) = 1405046269503207469140791548403639533127416416214210694972085079171787580463776820425965898174272870486015739516125786182821637006600742140682552321645503743280670839819078749092730110549881891271317396450158021688253989767145578723458252769465545504142139663476747479225923933192421405464414574786272963741656223941750084051228611576708609346787101088759062724389874160693008783334605903142528824559223515203978707969795087506678894006628296743079886244349469131831225757926844843554897638786146036869572653204735650843186722732736888918789379054050122205253165705085538743651258400390580971043144644984654914856729
            
    - **Respuesta**: Y (Sí es posible y factible)
        
9. **Problema 8: Descifrado completo RSA**:
    
    - **Datos**: p, ciphertext, e = 65537, n
        
    - **Solicitado**: plaintext
        
    - **Solución**:
        
        - q = n ÷ p
            
        - φ(n) = (p-1)(q-1)
            
        - d = e⁻¹ mod φ(n)
            
        - m = cᵈ mod n = 14311663942709674867122208214901970650496788151239520971623411712977120527163003942343369341
            
    - **Respuesta**: Y (Sí es posible y factible)
        
10. **Obtención de la flag**:
    
    - El plaintext final se convirtió a hexadecimal y luego a ASCII
        
    - **Conversión**:
        
        - Plaintext: 14311663942709674867122208214901970650496788151239520971623411712977120527163003942343369341
            
        - Hexadecimal: 7069636f4354467b7741385f74683474245f696c6c336147616c2e2e6f61326432323339627d
            
        - ASCII: picoCTF{wA8_th4t$_ill3aGal..oa2d2239b}
            

**FLAG OBTENIDA:**  
`picoCTF{wA8_th4t$_ill3aGal..oa2d2239b}`

**NOTAS ADICIONALES:**

- La flag `wA8_th4t$_ill3aGal..oa2d2239b` parece ser "wait that's illegal" en formato leet con algún sufijo adicional
    
- Este reto demostró comprensión completa del flujo de trabajo de RSA: generación de claves, cifrado y descifrado
    
- Se cubrieron tanto escenarios factibles como no factibles, mostrando entendimiento de las limitaciones prácticas de RSA
    
- El quiz evaluó habilidades en aritmética modular, teoría de números y complejidad computacional
    
- El problema de factorización de n grande reforzó el principio fundamental de seguridad de RSA
    
- El uso de e=3 en múltiples problemas ilustró tanto sus ventajas (cálculos eficientes) como sus vulnerabilidades (ataque de raíz cúbica)
    
- La conversión final de números a texto demostró la aplicación práctica de RSA en protección de información
    
- Este reto sirvió como excelente evaluación formativa de conceptos criptográficos esenciales
    
- La progresión de problemas desde cálculos básicos hasta descifrado completo mostró un diseño pedagógico efectivo
    
- La flag obtenida confirma el dominio de los principios fundamentales de criptografía de clave pública
