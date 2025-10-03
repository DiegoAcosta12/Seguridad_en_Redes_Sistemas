**RETO:**  
SQL Direct

**DESCRIPCIÓN:**  
Connect to this PostgreSQL server and find the flag!  
`psql -h saturn.picoctf.net -p 58288 -U postgres pico`  
Password is `postgres`

**SOLUCIÓN:**

1. **Conexión a la base de datos**:
    
    - Me conecté al servidor PostgreSQL usando el comando proporcionado
        
    - Utilicé la contraseña `postgres` para autenticarme
        
    - Accedí a la base de datos `pico`
        
2. **Enumeración de la base de datos**:
    
    - Listé las bases de datos disponibles usando `\l`
        
    - Me conecté a la base de datos `pico` usando `\c pico`
        
    - Listé las tablas en la base de datos usando `\dt`
        
    - Identifiqué una tabla llamada `flags`
        
3. **Obtención de la flag**:
    
    - Consulté el contenido de la tabla `flags` usando `SELECT * FROM flags;`
        
    - La flag estaba en el campo `address` del primer registro
        

**FLAG OBTENIDA:**  
`picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}`

**NOTAS ADICIONALES:**

- La flag `L3arN_S0m3_5qL_t0d4Y` refleja el propósito educativo del reto sobre SQL básico
    
- Este reto demostró comandos fundamentales de PostgreSQL para explorar bases de datos
    
- La tabla contenía datos de ejemplo con personajes de Star Wars junto con la flag
    
- El reto enfatizó la importancia de saber navegar y consultar bases de datos relacionales