# 03. Hardware

## 3.1 Equipo base

El hardware utilizado como base para este proyecto es un MacBook Pro 2018,
plataforma portátil diseñada originalmente para uso profesional, pero reutilizada
en este contexto como nodo de laboratorio Proxmox VE.

Se trata de un equipo con arquitectura Intel x86_64, lo que permite ejecutar
Proxmox VE de forma nativa, aunque con consideraciones particulares derivadas
de su diseño y del uso del chip de seguridad Apple T2.

Este documento describe el equipo como plataforma, sin entrar aún en 
limitaciones profundas ni en detalles especificos del chip T2, los cuales se
abordaran en capitulos posteriores.

## 3.2 Especificaciones técnicas

Las especificaciones relevantes del equipo son las siguientes:

- Modelo: Macbook Pro 2018
- Arquitectura: Intel x86_64
- CPU: Intel Core (VT-x y VT-d soportados)
- Memoria RAM: 16 GB
- Almacenamiento: SSD NVMe propietario (gestionado por Apple T2)
- Red: Adaptador USB-C a Ethernet
- Firmware: UEFI propietario de Apple

## 3.3 Implicaciones para virtualización

Desde el punto de vista de virtualización, el equipo las siguientes
implicaciones:

 - Soporte completo para virtualización por hardware (VT-X).
 - Soporte limitado y condicionado para ciertas funciones avanzadas (VT-D / passthrough).
 - Capacidad de memoria suficiente para múltiples máquinas virtuales ligeras o contenedores.
 - Almacenamiento rápido, aunque no diseñado para cargas intensivas sostenidas.

El equipo es adecuado para laboratorios de aprendizaje, pruebas de arquitectura y
entornos controlados, pero no para escenarios de alta demanda o criticidad.

## 3.4 Comparación vs hardware de servidor

Comparado con hardware de servidor tradicional, el Macbook Pro 2018 presenta diferencias claras:

 - No dispone de memorias ECC.
 - Carece de interfaces de gestión remota (IPMI, iDRAC, iLO).
 - No ofrece RAID por hardware.
 - La refrigeración está diseñada para cargas intermitentes, no continuas.

Esta comparación permite entender por qué no debe tratarse como un servidor,
sino como una plataforma de experimentación.

## 3.5 Justificación de uso en laboratorio

La elección de este hardware se justifica en un contexto de laboratorio por los siguientes motivos:

 - Permite practicar Proxmox VE en hardware real.
 - Facilita el aprendizaje de virtualización, redes y segmentación.
 - Obliga a aplicar criterio arquitectónico frente a limitaciones reales.
 - Favorece la documentación y el diseño consistente del laboratorio.

El valor principal de este equipo no reside en su potencia, sino en su capacidad para enseñar
decisiones técnicas reales en un entorno controlado.
