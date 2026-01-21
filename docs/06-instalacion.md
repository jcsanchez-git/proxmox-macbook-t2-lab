# 06. Instalación

Este capítulo describe el proceso de instalación de Proxmox VE 8.x sobre Debian 12 Bookworm, adaptado a hardware Apple con chip T2. Se mantiene un enfoque técnico, reproducible y seguro.

## 6.1 Preparación previa (Secure Boot y firmware)

Antes de iniciar, es obligatorio ajustar la configuración de seguridad del MacBook Pro 2018:

- Iniciar en macOS Recovery (⌘ + R).
- Acceder a Startup Security Utility.
- Configurar:
    - Secure Boot → No Security
    - Allow booting from external media → Enabled

⚠️ Nota: estas modificaciones reducen la seguridad del sistema 
y son recomendadas únicamente en entornos de laboratorio.

## 6.2 Descarga y verificación de la ISO

 1. Descargar la ISO oficial de Debian 12 (Bookworm).
 2. Descargar el archivo de checksum correspondiente (SHA256 o SHA512).
 3. Verificar la ISO desde Windows utilizando herramientas nativas:

# Verificación de ISO en Windows
CertUtil -hashfile debian-12.x.x-amd64-netinst.iso SHA256

    
Comparar el hash con el oficial para garantizar integridad y autenticidad.

## 6.3 Creación del medio de instalación

- Utilizar una memoria USB de al menos 8 GB.
- Crear el medio de instalación con Rufus (Windows):
    - Seleccionar esquema de partición GPT
    - Modo de arranque UEFI
    - Modo ISO o DD recomendado para MacBook T2
- Expulsar el USB de forma segura tras la creación

⚠️ Advertencia: seleccionar el dispositivo incorrecto puede borrar datos importantes.

## 6.4 Instalación de Proxmox VE

1. Arrancar desde el USB creado.
2. Instalar Debian 12 bare-metal siguiendo configuraciones recomendadas:
   - Particionado simple (LVM o EXT4)
   - Configuración de red inicial
   - Usuario, contraseña y hostname
   - Post-instalación de Debian: instalar Proxmox VE usando repositorios oficiales

# Agregar repositorio Proxmox y instalar
echo "deb http://download.proxmox.com/debian/pve bookworm pve-no-subscription" > /etc/apt/sources.list.d/pve-install-repo.list
apt update
apt install proxmox-ve -y


Nota sobre particionado mínimo LVM o EXT4, indicando que ZFS no es recomendable en T2 por RAM limitada.

Esto convierte el host Debian en un nodo Proxmox VE funcional.

## 6.5 Post-instalación (drivers Apple T2)

- Verificación del T2 con comandos como lspci o dmesg | grep -i t2.
- Instalar firmware y módulos necesarios para compatibilidad con chip T2:

# Instalar firmware T2
apt install linux-firmware firmware-misc-nonfree -y

- Reiniciar el sistema.
- Verificar que CPU, memoria y almacenamiento son reconocidos correctamente.

Nota: algunos dispositivos (audio, cámara) pueden no funcionar; 
el foco del laboratorio es virtualización.

## 6.6 Configuración inicial de red

- Configurar bridge vmbr0 para VMs y contenedores.

# Configuración de bridge en /etc/network/interfaces
auto vmbr0
iface vmbr0 inet static
    address 192.168.1.100/24
    gateway 192.168.1.1
    bridge_ports enp0s20f0u1
    bridge_stp off
    bridge_fd 0



- Probar conectividad con ping y acceso a interfaz web:

      https://IP_DEL_HOST:8006
  
- Revisar logs básicos para asegurar funcionamiento.

## 6.7 Validación del sistema

Checklist post-instalación:


# Verificar versión de Proxmox VE
pveversion -v

# Verificar T2
lspci | grep -i t2

- Acceso a la interfaz web de Proxmox VE.
- Nodo sin errores críticos.
- CPU y RAM reconocidas correctamente.
- Red funcional y bridge operativo.
- Posibilidad de crear VM o contenedor de prueba.
- Documentación de cualquier incidencia encontrada.

Una vez validado, el nodo está listo para iniciar los laboratorios de virtualización 
y redes.

