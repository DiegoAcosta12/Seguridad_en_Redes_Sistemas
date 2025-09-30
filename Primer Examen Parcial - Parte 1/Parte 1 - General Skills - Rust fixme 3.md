**RETO:**  
Rust fixme 3

**DESCRIPCIÓN:**  
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag! Download the Rust code here.

**SOLUCIÓN:**

1. **Descarga del archivo Rust**:
    
    - Descargué el archivo `rust-fixme3.rs` usando el comando:
        
        bash
        
        wget https://artifacts.picoctf.net/c/156/rust-fixme3.rs
        
2. **Análisis inicial del código**:
    
    - Examiné el archivo para identificar los errores de sintaxis
        
    - El código contenía una función que construye la flag caracter por caracter usando un vector
        
3. **Proceso de corrección paso a paso**:
    
    - **Paso 1**: Compilar para ver errores
        
        bash
        
        rustc rust-fixme3.rs
        
    - **Paso 2**: Leer los mensajes de error del compilador que indicaban líneas específicas con problemas
        
    - **Paso 3**: Corregir errores de sintaxis identificados
        
    - **Paso 4**: Re-compilar después de cada corrección hasta que no hubiera errores
        
4. **Compilación final y ejecución**:
    
    - Compilé el código corregido:
        
        bash
        
        rustc rust-fixme3.rs
        
    - Ejecuté el programa:
        
        bash
        
        ./rust-fixme3
        

**FLAG OBTENIDA:**  
`picoCTF{n0w_y0uv3_f1x3d_1h3m_411}`

**NOTAS ADICIONALES:**

- Este reto completó la serie de tres ejercicios de corrección de sintaxis en Rust
    
- La flag celebra que el usuario ha "arreglado todos" los problemas de Rust
    
- Los mensajes de error del compilador de Rust son muy descriptivos y facilitan la corrección de errores
    
- La práctica con estos retos ayuda a familiarizarse con la sintaxis específica de Rust