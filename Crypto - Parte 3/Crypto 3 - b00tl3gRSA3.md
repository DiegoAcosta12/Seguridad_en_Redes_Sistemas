**RETO:** b00tl3gRSA3

**DESCRIPCION:**  
RSA con múltiples factores primos en lugar de solo p y q.

**SOLUCION:**

- Obtuve c, n, e del servicio
    
- n estaba compuesto por 224 primos consecutivos (157-9973)
    
- Calculé φ(n) como producto de (pᵢ-1)
    
- Obtuve d = e⁻¹ mod φ(n)
    
- Descifré m = cᵈ mod n
    

**Flag:** `picoCTF{too_many_fact0rs_4025135}`

**NOTAS:**

- Múltiples factores pequeños hacen que φ(n) sea fácil de calcular
    
- La seguridad de RSA se rompe si n es fácil de factorizar
    
- No se necesitaron algoritmos complejos de factorización