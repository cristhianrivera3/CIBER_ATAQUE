### **2
# Objetivo del Laboratorio

## Propósito General
Demostrar cómo un atacante puede comprometer un sistema Windows con una contraseña débil mediante un ataque de fuerza bruta al protocolo RDP (Escritorio Remoto), y cómo ejecutar código malicioso educativo una vez dentro del sistema.

## Objetivos Específicos
1. **Infraestructura**: Configurar un entorno virtualizado con VirtualBox con 3 máquinas (Kali, Windows, Ubuntu)
2. **Red**: Configurar todas las máquinas en modo puente para que se comuniquen
3. **Ataque**: Ejecutar Hydra contra el puerto 3389 de Windows
4. **Acceso**: Conectarse remotamente a Windows usando RDP
5. **Post-explotación**: Ejecutar un script Python personalizado ("ventana rebelde")
6. **Documentación**: Registrar todo el proceso para portafolio profesional

## Alcance del Proyecto
- **No es malicioso**: Es un entorno educativo controlado
- **Solo fines académicos**: Demuestra vulnerabilidades comunes
- **Aprendizaje práctico**: Aplicación de conceptos de ciberseguridad

## Resultados Esperados
- Obtener la contraseña del usuario `victima` mediante Hydra
- Acceder al escritorio de Windows desde Kali
- Ejecutar código en el sistema víctima
- Dejar documentado el proceso para futuros proyectos