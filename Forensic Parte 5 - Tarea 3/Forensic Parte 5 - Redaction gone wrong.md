**RETO:** Redaction gone wrong

**DESCRIPCION:**  
Now you DON’T see me. This report has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly? Download the PDF: Financial_Report_for_ABC_Labs.pdf. The challenge involves finding hidden text in a poorly redacted PDF document.

**SOLUCION:**

- Descargué el archivo PDF usando wget
    
- Usé **`pdftotext`** para extraer todo el texto del PDF, incluyendo el contenido "redactado"
    
- También probé seleccionar manualmente el texto debajo de los recuadros negros en un visor de PDF
    
- Encontré una clave privada RSA que contenía la flag oculta
    
- La flag estaba visible al copiar el texto de las áreas supuestamente redactadas
    

Comandos usados:

bash

wget https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
pdftotext Financial_Report_for_ABC_Labs.pdf output.txt
cat output.txt

**Flag:** `picoCTF{C4n_Y0u_S33_m3_fully}`

**NOTAS ADICIONALES:**

- La redacción se hizo incorrectamente usando solo capas negras superpuestas sin eliminar el texto subyacente
    
- El texto "redactado" permaneció completamente accesible y seleccionable
    
- La flag estaba oculta dentro de una clave privada RSA en la página 2 del documento
    
- Este es un error común en la redacción de documentos PDF que compromete la seguridad
    

**REFERENCIAS:**

- [https://www.pdf-insecurity.org/redaction/redaction.html](https://www.pdf-insecurity.org/redaction/redaction.html)
    
- [https://en.wikipedia.org/wiki/PDF](https://en.wikipedia.org/wiki/PDF)