# 02. Alcance del documento 

## 2.1 Qué incluye el proyecto

Este proyecto incluye y documenta de forma explícita los siguientes elementos:
    
- Instalación bare-metal de Proxmox VE 8.x sobre un MacBook Pro 2018 (Intel +
    Chip T2).

- Consideraciones técnicas derivadas del uso de hardware Apple con Apple T2
  Security Chip.

- Diseño de un laboratorio reproducible orientado a aprendizaje avanzado en:

  - Virtualización con KVM

  - Contenedores LXC

  - Redes virtuales y bridges

  - Firewalls y routers virtuales

  - Buenas prácticas en entornos datacenter-style, adaptadas a un 
    entorno homelab.

  - Documentación técnica estructurada y versionable para GitHub.

El contenido está pensado para ser reproducido, analizado y extendido por el lector.


## 2.2 Qué NO incluye el proyecto

Este proyecto no está diseñado para cubrir ni garantizar:

- Uso en entornos de producción.

- Alta disponibilidad (HA) real o certificada.

- Soporte oficial por parte de Apple, Proxmox o Debian.

- Configuraciones avanzadas de PCI Passthrough con garantías de estabilidad.

- Rendimiento sostenido 24/7 bajo cargas intensivas.

- Cumplimiento de normativas empresariales, auditorías o certificaciones.

Cualquier uso fuera de estos límites quedan bajo responsabilidad exclusiva del lector.

## 2.3 Supuestos técnicos

Este documento asume que el lector:
  
- Posee conocimientos intermedios o avanzados de linux.

- Comprende los conceptos básicos de virtualización y redes.

- Está familiarizado con el uso de la línea de comandos.

- Entiende los riesgos asociados a instalaciones bare-metal.

No se incluyen explicaciones introductorias sobre Linux o virtualización básica.

## 2.4 Perfil del lector

El contenido está orientado a:

- Estudiantes de redes, sistemas o ciberseguridad.

- Administradores de sistemas en formación.

- Ingenieros que desean practicar Proxmox VE sin hardware de servidor
  dedicado.

- Entusiastas de homelab con enfoque técnico y disciplinado.

No es un proyecto orientado a usuarios principiantes.

## 2.5 Advertencias clave

Antes de continuar, es importante tener en cuenta:

- El hardware descrito no sustituye un servidor.

- El chip T2 introduce limitaciones reales en compatibilidad y recuperación.

- No existe soporte oficial para est escenario.

- El laboratorio está pensado para aprendizaje y experimentación, no para cargas críticas.

Continuar implica aceptar estas condiciones y entender el entendimiento experimental del proyecto.
