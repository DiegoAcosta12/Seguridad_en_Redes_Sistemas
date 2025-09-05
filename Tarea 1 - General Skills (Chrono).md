RETO:
Chrono

DESCRIPCION:
How to automate tasks to run at intervals on linux servers?Use ssh to connect to this server:

```
Server: saturn.picoctf.net
Port: 52948
Username: picoplayer 
Password: 5wf1w1hVxt
```

SOLUCION:
- **Conectarse al servidor con SSH**
    
    `ssh -p 52948 picoplayer@saturn.picoctf.net`
    
    Luego, ingresar la contraseña:
    
    `5wf1w1hVxt`
    
- **Revisar los cron jobs configurados**  
    Se listaron las tareas automáticas con:
    
    `crontab -l`
    
    Allí se observó un script que se ejecutaba periódicamente y contenía la flag.
    
- **Leer el archivo indicado en el cron job**  
    El archivo ejecutado incluía el contenido de la flag, por lo que bastó con inspeccionarlo para obtenerla.

**SOLUCION:** `picoCTF{Sch3DUL7NG_T45K3_L1NUX_9d5cb744}`

NOTAS ADICIONALES:
- Aprendí que en Linux se pueden programar tareas automáticas usando `cron` y que la configuración de cada usuario puede verse con `crontab -l`.

- Muchas veces los CTF esconden pistas en scripts que se ejecutan automáticamente, por lo que revisar las tareas programadas es clave.

REFERENCIAS:
https://man7.org/linux/man-pages/man5/crontab.5.html  
https://www.redhat.com/sysadmin/automate-cron-jobs