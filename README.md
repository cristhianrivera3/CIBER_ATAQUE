# 🛡️ Ciber Batalla: Laboratorio de Ataque
# AUTOR : CRISTHIAN SAMUEL ZAMBRANO RIVERA

## 📋 Descripción General
Laboratorio educativo que simula un entorno real de ciberseguridad donde un atacante (Kali Linux) compromete una máquina víctima (Windows 10) mediante un ataque de fuerza bruta RDP, ejecuta un script personalizado ("ventana rebelde") y demuestra el impacto de contraseñas débiles.

## 🏗️ Arquitectura del Laboratorio

| Máquina | Rol | IP | Usuario/Contraseña |
|---------|-----|-----|-------------------|
| Kali Linux | Atacante | 192.168.1.104 | kali / kali |
| Windows 10 Pro | Víctima | 192.168.1.106 | victima / 22675439 |
| Ubuntu Server | Defensor (futuro) | 192.168.1.105 | defensor / 123456 |

## 🎯 Objetivos Alcanzados
- ✅ Configurar entorno virtualizado con VirtualBox
- ✅ Configurar red en modo puente entre las 3 máquinas
- ✅ Ejecutar ataque de fuerza bruta con Hydra contra RDP
- ✅ Obtener acceso remoto a Windows desde Kali
- ✅ Ejecutar script propio (ventana_rebelde.py) en el sistema víctima
- ✅ Documentar todo el proceso para portafolio profesional

## 🛠️ Tecnologías Utilizadas
- **VirtualBox 7.x** - Hipervisor
- **Kali Linux 2025.4** - Máquina atacante
- **Windows 10 Pro** - Máquina víctima
- **Ubuntu Server 22.04** - Máquina defensora (próximamente)
- **Hydra 9.6** - Ataque de fuerza bruta
- **Python 3** - Script de post-explotación

## 📷 Capturas de Pantalla
![Arquitectura](imagenes/arquitectura.png)
![Kali IP](imagenes/kali-ip.png)
![Windows IP](imagenes/windows-ip.png)
![Ping exitoso](imagenes/ping-exitoso.png)
![Conexión RDP](imagenes/conexion-rdp.png)
![Ventana Rebelde](imagenes/ventana-rebelde.png)
![Ataque Hydra](imagenes/hydra-ataque.png)

## 📁 Estructura del Repositorio
Ciber-Batalla-Laboratorio/
├── README.md
├── docs/ # Documentación detallada
│ ├── 01-objetivo.md
│ ├── 02-arquitectura.md
│ ├── 03-configuracion-virtualbox.md
│ ├── 04-instalacion-kali.md
│ ├── 05-instalacion-windows.md
│ ├── 06-ataque-hydra.md
│ └── 07-ventana-rebelde.md
├── imagenes/ # Capturas de pantalla
├── scripts/ # Código desarrollado
│ └── ventana_rebelde.py
└── configuraciones/ # Comandos útiles
└── comandos-utiles.txt
## 🔧 Pasos Realizados

### 1. Configuración de VirtualBox
- Creación de 3 máquinas virtuales
- Configuración de red en modo puente
- Asignación de recursos (RAM, CPUs, disco)

### 2. Instalación de Sistemas
- Kali Linux: máquina atacante
- Windows 10 Pro: máquina víctima (RDP habilitado)
- Ubuntu Server: máquina defensora

### 3. Ataque Hydra
hydra -l victima -P /usr/share/wordlists/rockyou.txt rdp://192.168.1.106
4. Conexión RDP
bash
xfreerdp3 /v:192.168.1.106 /u:victima /p:22675439 /cert:ignore
##5. Ejecución del Script

python3 ventana_rebelde.py
