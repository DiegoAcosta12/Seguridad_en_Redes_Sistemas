**RETO:** Mind your Ps and Qs

**DESCRIPCION:**  
In RSA, a small e value can be problematic, but what about N? Can you decrypt this?

**SOLUCION:**

- Descargué el archivo values que contenía los parámetros RSA (c, n, e)
    
- Analicé que el módulo n era pequeño (≈ 100 bits), vulnerable a factorización
    
- Usé Python con sympy para factorizar n en p y q
    
- Calculé φ(n) = (p-1)(q-1)
    
- Calculé d = e⁻¹ mod φ(n) usando gmpy2
    
- Descifré el texto con m = cᵈ mod n
    
- Convertí el resultado de hex a texto para obtener la flag
    

Comandos/código usados:

bash

wget https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values

python

from sympy import factorint
import gmpy2

c = 964354128913912393938480857590969826308054462950561875638492039363373779803642185
n = 1584586296183412107468474423529992275940096154074798537916936609523894209759157543
e = 65537

factors = factorint(n)
p, q = list(factors.keys())
phi = (p - 1) * (q - 1)
d = gmpy2.invert(e, phi)
m = pow(c, d, n)
print(bytes.fromhex(hex(m)[2:]).decode())

**Flag:** `picoCTF{sma11_N_n0_g0od_55304594}`

**NOTAS ADICIONALES:**

- El reto demostró que un módulo N pequeño en RSA es vulnerable a factorización rápida
    
- n tenía solo ~100 bits, lo que permitió factorizarlo en segundos
    
- La pista "Bits are expensive" se refería al tamaño pequeño de N para ahorrar costos computacionales imaginarios
    
- Una vez factorizado n, el descifrado RSA es directo
    

**REFERENCIAS:**

- [https://en.wikipedia.org/wiki/RSA_(cryptosystem)](https://en.wikipedia.org/wiki/RSA_\(cryptosystem\))
    
- [https://www.sympy.org/](https://www.sympy.org/) (para factorización)