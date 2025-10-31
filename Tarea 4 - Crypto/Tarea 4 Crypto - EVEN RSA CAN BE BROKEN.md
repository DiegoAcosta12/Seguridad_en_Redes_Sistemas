**RETO:** EVEN RSA CAN BE BROKEN???

**DESCRIPCION:**  
This service provides you an encrypted flag. Can you decrypt it with just N & e? Connect to the program with netcat.

**SOLUCION:**

- Conecté múltiples veces al servicio para obtener diferentes pares (N, e, c)
    
- Comparé los valores de N entre diferentes conexiones
    
- Encontré que algunos valores de N compartían un factor primo común
    
- Usé el algoritmo de Euclides (GCD) para encontrar el factor común entre pares de N
    
- Una vez encontrado un factor p, calculé q = N/p
    
- Calculé φ(N) = (p-1)(q-1) y d = e⁻¹ mod φ(N)
    
- Descifré el mensaje con m = cᵈ mod N
    

**Código:**

python

import socket
import math

def get_params():
    s = socket.socket()
    s.connect(('verbal-sleep.picoctf.net', 59318))
    data = s.recv(4096).decode()
    s.close()
    
    lines = data.strip().split('\n')
    n = int([line for line in lines if line.startswith('N:')][0].split(':')[1].strip())
    e = int([line for line in lines if line.startswith('e:')][0].split(':')[1].strip())
    c = int([line for line in lines if line.startswith('cyphertext:')][0].split(':')[1].strip())
    
    return n, e, c

# Obtener múltiples pares (N, c)
n_values, c_values = [], []
for i in range(10):
    n, e, c = get_params()
    n_values.append(n)
    c_values.append(c)

# Buscar factores comunes
for i in range(len(n_values)):
    for j in range(i+1, len(n_values)):
        gcd_val = math.gcd(n_values[i], n_values[j])
        if gcd_val > 1:
            p = gcd_val
            q = n_values[i] // p
            phi = (p-1) * (q-1)
            d = pow(e, -1, phi)
            m = pow(c_values[i], d, n_values[i])
            flag = m.to_bytes((m.bit_length() + 7) // 8, 'big')

**Flag:** `picoCTF{tw0_1$_pr!m3de643ad5}`

**NOTAS:**

- El ataque funciona cuando diferentes módulos N comparten un factor primo
    
- Esto puede pasar si el generador de números primos tiene poca entropía
    
- GCD es eficiente para encontrar factores comunes
    
- No fue necesario factorizar N completamente, solo encontrar un factor común
    
- La flag indica "two is prime" refiriéndose al factor común