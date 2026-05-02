### **4. `docs/03-configuracion-virtualbox.md`**

```markdown
# Configuración de VirtualBox

## Requisitos Previos
- **VirtualBox 7.x** instalado
- **16 GB de RAM** en tu PC real (recomendado)
- **100 GB de espacio libre** en disco

## Creación de Máquinas Virtuales

### Configuración General para las 3 máquinas
- **Tipo**: Linux (para Kali/Ubuntu) / Microsoft Windows (para Windows)
- **Arquitectura**: 64-bit
- **Memoria**: 2048-4096 MB según disponibilidad
- **Disco**: VDI (VirtualBox Disk Image), asignación dinámica

### Configuración de Red (CRUCIAL)
1. Seleccionar la máquina → Configuración → Red
2. **Adaptador 1**: Conectado a → **Adaptador puente (Bridged Adapter)**
3. **Nombre**: Seleccionar tu tarjeta de red real (WiFi o Ethernet)

### Pasos Realizados
1. Crear máquina Kali Linux (importada desde imagen .vbox)
2. Crear máquina Windows 10 (instalación manual con ISO)
3. Crear máquina Ubuntu Server (instalación manual con ISO)
4. Configurar red en modo puente en las 3
5. Verificar comunicación con ping

## Errores Comunes y Soluciones

| Error | Causa | Solución |
|-------|-------|----------|
| No bootable medium | ISO no montada | Montar la ISO en almacenamiento |
| Ping 100% loss | Firewall de Windows | Desactivar firewall para el laboratorio |
| IP 10.0.2.x | Modo NAT activo | Cambiar a Adaptador puente |
