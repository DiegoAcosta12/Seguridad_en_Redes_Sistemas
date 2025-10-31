**RETO:** ReadMyCert

**DESCRIPCION:**  
How about we take you on an adventure on exploring certificate signing requests. Take a look at this CSR file here.

**SOLUCION:**

- Descargué el archivo readmycert.csr
    
- Usé OpenSSL para decodificar y leer el Certificate Signing Request
    
- El comando `openssl req -in readmycert.csr -noout -text` mostró toda la información del CSR
    
- La flag estaba visible en el campo Subject (CN) del certificado
    
- También se podía ver directamente con `openssl req -in readmycert.csr -noout -subject`
    

**Comandos usados:**

bash

wget https://artifacts.picoctf.net/c/423/readmycert.csr
openssl req -in readmycert.csr -noout -text
openssl req -in readmycert.csr -noout -subject

**Flag:** `picoCTF{read_mycert_57f58832}`

**NOTAS:**

- Los CSR (Certificate Signing Requests) contienen información sobre la entidad que solicita el certificado
    
- El campo Subject (Sujeto) contiene detalles como Common Name (CN), Organization (O), etc.
    
- La flag estaba oculta en el Common Name del certificado
    
- OpenSSL es la herramienta estándar para trabajar con certificados y CSR
    

**REFERENCIAS:**

- [https://www.openssl.org/](https://www.openssl.org/)
    
- [https://en.wikipedia.org/wiki/Certificate_signing_request](https://en.wikipedia.org/wiki/Certificate_signing_request)