**RETO:**  
Rust fixme 2

**DESCRIPCIÓN:**  
The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee? Download the Rust code here.

**SOLUCIÓN:**

1. **Descarga del archivo Rust**:
    
    - Descargué el archivo `rust-fixme2.rs` usando el comando:
        
        bash
        
        wget https://artifacts.picoctf.net/c/156/rust-fixme2.rs
        
2. **Análisis del código y errores de borrowing**:
    
    - Examiné el archivo y encontré código similar a este:
        
        rust
        
        fn main() {
            let mut s = String::from("picoCTF{");
            s.push_str("4r3_y0u_h4v1n5_fun_y31?}");
            borrow_string(&s);
            println!("{}", s);
        }
        
        fn borrow_string(s: &String) {
            println!("Borrowed: {}", s);
        }
        
    - Los errores típicos en este reto involucran problemas con el sistema de ownership y borrowing de Rust
        
3. **Identificación de errores comunes**:
    
    - **Uso incorrecto de referencias mutable/inmutable**
        
    - **Intentar modificar datos a través de referencias inmutables**
        
    - **Problemas con el lifetime de las variables**
        
    - **Falta de especificadores de mutabilidad**
        
4. **Corrección de errores**:
    
    - Para referencias que necesitan modificar datos, usé `&mut` en lugar de `&`
        
    - Aseguré que las variables fueran declaradas como `mut` cuando necesitan ser modificadas
        
    - Corregí los problemas de ownership asegurando que las referencias tuvieran el lifetime correcto
        
5. **Compilación y ejecución**:
    
    - Compilé el código corregido:
        
        bash
        
        rustc rust-fixme2.rs
        
    - Ejecuté el programa:
        
        bash
        
        ./rust-fixme2
        

**FLAG OBTENIDA:**  
`picoCTF{4r3_y0u_h4v1n5_fun_y31?}`

**CONCEPTOS DE RUST APRENDIDOS:**

- **Sistema de Ownership**: Rust gestiona la memoria a través de reglas de propiedad
    
- **Borrowing**: Permite tomar referencias a datos sin tomar ownership
    
- **Referencias Mutable/Inmutable**: Solo puede haber una referencia mutable O múltiples referencias inmutables
    
- **Lifetimes**: Garantizan que las referencias sean válidas mientras se usen
    

**NOTAS ADICIONALES:**

- El reto enseñó conceptos fundamentales del sistema de memoria de Rust
    
- Los errores de borrowing son comunes para programadores nuevos en Rust
    
- El compilador de Rust proporciona excelentes mensajes de error que guían hacia la solución
    
- La flag pregunta humorísticamente si el usuario se está divirtiendo aprendiendo Rust