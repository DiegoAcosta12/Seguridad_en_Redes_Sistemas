**RETO:** Secret of the Polyglot

**DESCRIPCION:** The Network Operations Center (NOC) picked up a suspicious file that gives conflicting information about its file type. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?

**SOLUCION:**

- Descargué el archivo `flag2of2-final.pdf`
    
- Identifiqué que era un archivo polyglot (válido como PNG y PDF simultáneamente)
    
- Usé **`file`** para verificar los tipos: `PNG image data, 50 x 50, 8-bit/color RGBA` y `PDF document`
    
- Extraje la parte PDF del archivo usando **`dd`**
    
- Encontré un stream comprimido con FlateDecode en el PDF
    
- Descomprimí el stream usando Python con **`zlib.decompress()`**
    
- El stream descomprimido contenía la flag completa
    

Comandos usados:

bash

wget https://artifacts.picoctf.net/c_titan/7/flag2of2-final.pdf
file flag2of2-final.pdf
dd if=flag2of2-final.pdf of=extracted.pdf bs=1 skip=914
sed -n '/stream/,/endstream/p' extracted.pdf | head -n -1 | tail -n +2 > stream.bin
python3 -c "import zlib; print(zlib.decompress(open('stream.bin','rb').read()).decode())"

**Flag:** `picoCTF{f1u3n7_1n_pn9_&_pdf_53b741d6}`

**NOTAS ADICIONALES:**

- Un archivo polyglot es válido en múltiples formatos de archivo simultáneamente
    
- La flag estaba oculta en un stream comprimido del PDF (FlateDecode)
    
- El nombre "flag2of2" era engañoso - la flag completa estaba en este archivo
    
- Se necesitó análisis forense tanto del componente PNG como del PDF
    

**REFERENCIAS:**

- [https://en.wikipedia.org/wiki/Polyglot_(computing)](https://en.wikipedia.org/wiki/Polyglot_\(computing\))
    
- [https://en.wikipedia.org/wiki/FlateDecode](https://en.wikipedia.org/wiki/FlateDecode)
    
- [https://linux.die.net/man/1/file](https://linux.die.net/man/1/file)