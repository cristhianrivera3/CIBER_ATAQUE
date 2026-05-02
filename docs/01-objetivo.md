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