**RETO:**  
Insp3ct0r

**DESCRIPCIÓN:**  
Kishor Balan tipped us off that the following code may need inspection:  
[http://jupiter.challenges.picoctf.org:44924](http://jupiter.challenges.picoctf.org:44924/)

**SOLUCIÓN:**

1. Accedí al sitio web y revisé el código fuente HTML, donde encontré la primera parte de la flag en un comentario: `picoCTF{tru3_d3`.
    
2. Inspeccioné el archivo CSS (`style.css`) y encontré la segunda parte en un comentario: `t3ct1ve_0r_ju5t`.
    
3. Inspeccioné el archivo JavaScript (`script.js`) y encontré la tercera parte en un comentario: `_lucky?f10be399}`.
    
4. Uní las tres partes para formar la flag completa.
    

**FLAG OBTENIDA:**  
`picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?f10be399}`

**NOTAS ADICIONALES:**

- Las flags a menudo se dividen en múltiples partes y se ocultan en diferentes recursos (HTML, CSS, JS).
    
- Las herramientas de desarrollador del navegador (F12) son esenciales para inspeccionar el código fuente y los archivos vinculados.
    

**REFERENCIAS:**

- [Herramientas de desarrollador de Chrome](https://developer.chrome.com/docs/devtools/)