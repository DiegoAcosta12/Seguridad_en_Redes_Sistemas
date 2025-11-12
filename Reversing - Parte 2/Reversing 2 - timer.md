**RETO:** timer

**DESCRIPCION:**  
You will find the flag after analysing this apk. Download here.

**SOLUCION:**

- Descargué el archivo timer.apk que contenía una aplicación Android compilada
    
- Extraje el contenido del APK usando `unzip` para acceder a los archivos internos
    
- Identifiqué que el APK contenía múltiples archivos DEX (classes.dex, classes2.dex, classes3.dex)
    
- Usé el comando `strings` para buscar strings legibles en los archivos DEX
    
- Encontré la flag en el archivo `classes3.dex` usando `strings timer_extracted/classes3.dex | grep -i pico`
    
- La flag estaba visible como un string hardcodeado en el código compilado
    

**Proceso de solución:**

1. **Descargar el archivo:**
    
    bash
    
    wget https://artifacts.picoctf.net/c/449/timer.apk
    
2. **Extraer el APK:**
    
    bash
    
    unzip timer.apk -d timer_extracted
    
3. **Buscar la flag en los archivos DEX:**
    
    bash
    
    strings timer_extracted/classes3.dex | grep -i pico
    
4. **Resultado encontrado:**
    
    text
    
    *picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}
    

**Flag:** `picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}`

**NOTAS:**

- El reto demostró que las aplicaciones Android pueden contener información sensible en archivos DEX
    
- Los strings hardcodeados en aplicaciones compiladas son fácilmente accesibles con herramientas simples como `strings`
    
- La flag "t1m3r_r3v3rs3d_succ355fully_17496" significa "timer reversed successfully" en leet speak
    
- Aunque las aplicaciones Android están compiladas, los strings literales permanecen legibles en los archivos DEX
    
- No fue necesario usar decompiladores complejos como JADX o MobSF para este reto
    
- El análisis estático simple con `strings` fue suficiente para encontrar la flag
    
- Las aplicaciones móviles nunca deben contener información sensible hardcodeada