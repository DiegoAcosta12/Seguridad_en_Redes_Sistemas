**RETO:** miniRSA

**DESCRIPCION:**  
RSA con un exponente público `e` muy pequeño.

**SOLUCION:**

- Descargué el ciphertext que contenía N, e=3, y c
    
- Como e=3 es muy pequeño y m³ < N, pude calcular la raíz cúbica directamente
    
- Calcular la raíz cúbica de c dio el mensaje original m
    
- Convertí m de hexadecimal a texto para obtener la flag
    

**Código:**

python

c = 2205316413931134031074603746928247799030155221252519872649649212867614751848436763801274360463406171277838056821437115883619169702963504606017565783537203207707757768473109845162808575425972525116337319108047893250549462147185741761825125
e = 3

def integer_cube_root(n):
    low, high = 0, n
    while low <= high:
        mid = (low + high) // 2
        mid_cubed = mid ** 3
        if mid_cubed == n:
            return mid, True
        elif mid_cubed < n:
            low = mid + 1
        else:
            high = mid - 1
    return high, False

m, exact = integer_cube_root(c)
hex_str = hex(m)[2:]
flag = bytes.fromhex(hex_str)

**Flag:** `picoCTF{n33d_a_lArg3r_e_606ce004}`

**NOTAS:**

- Un e pequeño permite ataques de raíz cuando m^e < N
    
- No fue necesario factorizar N ni calcular claves privadas
    
- La flag sugiere que se necesita un exponente e más grande para mayor seguridad