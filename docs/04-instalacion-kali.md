# Instalación y Configuración de Kali Linux

## Descarga
- **Versión**: Kali Linux 2025.4 VirtualBox (pre-instalada)
- **Formato**: Archivo .7z (descomprimir con 7-Zip)
- **Tamaño**: ~3.5 GB

## Importación en VirtualBox
1. Archivo → Importar servicio virtualizado
2. Seleccionar el archivo `.vbox` descomprimido
3. Verificar que el controlador sea SATA
4. RAM: 2048 MB
5. CPUs: 2

## Configuración Inicial
```bash
# Verificar red
ip a

# Cambiar contraseña (opcional)
passwd

# Actualizar sistema
sudo apt update && sudo apt upgrade -y


#Problema Resuelto: Archivo corrupto .zsh_history
# Solución
rm ~/.zsh_history
sudo reboot

##Herramientas Instaladas
Hydra: Ataque de fuerza bruta

nmap: Escaneo de puertos

rdesktop / xfreerdp: Cliente RDP

python3: Para scripts personalizados