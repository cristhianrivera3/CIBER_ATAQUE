```markdown
# Instalación y Configuración de Windows 10 (Víctima)

## Descarga
- **ISO oficial**: Windows 10 Pro (64-bit)
- **Descarga desde**: Microsoft.com
- **Tamaño**: ~5 GB

## Configuración en VirtualBox
- **RAM**: 4096 MB (recomendado)
- **CPUs**: 2
- **Disco**: 50 GB (VDI, dinámico)
- **Red**: Adaptador puente

## Instalación de Windows
1. Montar la ISO en almacenamiento
2. Iniciar máquina
3. Seleccionar idioma y teclado
4. **Instalación personalizada** (no actualización)
5. **Usuario**: `victima`
6. **Contraseña**: `22675439` (débil a propósito)

## Configuración Post-Instalación

### Habilitar Escritorio Remoto (RDP)
### Desactivar Firewall
### Desactivar para redes privadas y públicas
### Verificar IP
```cmd
ipconfig
# IP esperada: 192.168.1.106
Probar RDP desde Kali
nmap -p 3389 192.168.1.106
# Debe mostrar "open"

xfreerdp3 /v:192.168.1.106 /u:victima /p:22675439 /cert:ignore
##Nota de Seguridad: Este Windows está vulnerable a propósito para el laboratorio.