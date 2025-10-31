**RETO:** Pixelated

**DESCRIPCION:**  
I have these 2 images, can you make a flag out of them? scrambled1.png scrambled2.png

**SOLUCION:**

- Descargué scrambled1.png y scrambled2.png
    
- Usé Python con PIL para procesar las imágenes
    
- Apliqué operación XOR entre los píxeles de ambas imágenes
    
- La imagen resultante (xor_result.png) mostró claramente la flag
    
- No fue necesario usar otras operaciones (AND, OR) o combinaciones de canales
    

**Código:**

python

from PIL import Image

img1 = Image.open('scrambled1.png').convert('RGB')
img2 = Image.open('scrambled2.png').convert('RGB')

width, height = img1.size
result = Image.new('RGB', (width, height))

pixels1 = img1.load()
pixels2 = img2.load()
result_pixels = result.load()

for x in range(width):
    for y in range(height):
        r1, g1, b1 = pixels1[x, y]
        r2, g2, b2 = pixels2[x, y]
        result_pixels[x, y] = (r1 ^ r2, g1 ^ g2, b1 ^ b2)

result.save('xor_result.png')

**Flag:** `picoCTF{0542dc1d}`

**NOTAS:**

- XOR fue la operación correcta para revelar la flag
    
- Las imágenes estaban cifradas usando operación XOR
    
- La propiedad de XOR (A ⊕ B ⊕ B = A) permitió recuperar la imagen original
    
- No se necesitaron herramientas complejas de esteganografía