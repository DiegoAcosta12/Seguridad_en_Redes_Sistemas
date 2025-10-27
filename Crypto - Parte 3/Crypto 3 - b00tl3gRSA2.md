**RETO:** b00tl3gRSA2

**DESCRIPCION:**  
In RSA d is a lot bigger than e, why don't we use d to encrypt instead of e? Connect with nc [jupiter.challenges.picoctf.org](https://jupiter.challenges.picoctf.org/) 57464.

**SOLUCION:**

- Me conecté al servicio y obtuve c, n, e (con e muy grande)
    
- Reconocí que estaban usando d pequeño para cifrar y e grande era la clave privada
    
- Probé valores comunes de d (3, 5, 17, 257, 65537) para descifrar
    
- Encontré que d = 65537 funcionaba y producía la flag
    

Comandos/código usados:

bash

nc jupiter.challenges.picoctf.org 57464

python

c = 71030245308446578037617303738597150288418254673554603680991173179537399137936527643123982219729611648719953202457844770725653240263281763254943540927366665905288014001682345666253271798326018608847061098025374947136729002988157464695476924896084354486679351249293484278952084603616967884892034360447725427933
n = 86343160696713099323090591784677346207636458836212420292856229852217291650441931216387703537655780011549773389723933658651524386648577552658406069243735724343268841499652237901374824363710240065370962614693867286139702217574583833455999052435394467648769097503258203269564499635356195115364798712720049898809

for d in [3, 5, 17, 257, 65537]:
    m = pow(c, d, n)
    hex_str = hex(m)[2:]
    if len(hex_str) % 2:
        hex_str = '0' + hex_str
    try:
        bytes_data = bytes.fromhex(hex_str)
        if b'pico' in bytes_data:
            print(f"Found with d={d}: {bytes_data}")
            break
    except:
        pass

**Flag:** `picoCTF{bad_1d3a5_2152720}`

**NOTAS ADICIONALES:**

- El reto demostró que intercambiar e y d en RSA es peligroso cuando d es pequeño
    
- Un valor pequeño de d (65537) permitió descifrar fácilmente sin necesidad de factorizar n
    
- e enorme indicaba que d era pequeño en el esquema original
    
- No fue necesario calcular φ(n) ni usar ataques complejos como Wiener
    

**REFERENCIAS:**

- [https://en.wikipedia.org/wiki/RSA_(cryptosystem)](https://en.wikipedia.org/wiki/RSA_\(cryptosystem\))
    
- [https://en.wikipedia.org/wiki/Wiener%27s_attack](https://en.wikipedia.org/wiki/Wiener%2527s_attack)