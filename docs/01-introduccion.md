# 01. Introducción

## 1.1 Contexto del proyecto

Este proyecto documenta la reutilización de un MacBook Pro 2018 (Intel, chip T2)
como nodo Proxmox VE bare-metal, con un enfoque técnico, reproducible y alineado 
a buenas prácticas de infraestructura. 

La inciativa nace como un laboratorio serio (homelab profesional) orientado al 
aprendizaje práctico de virtualización, redes y diseño de sistemas, utilizando
hardware no tradicional pero disponible. El objetivo no es "forzar" el equipo
más allá de sus límites, sino entenderlo, documentarlo y trabajar conscientemente
dentro de ello.

Toda la documentación está pensada para vivir en un repositorio GitHub, versionada,
clara y útil tanto para el autor como para terceros que deseen replicar o estudiar 
el enfoque.

## 1.2 Problema a resolver
El acceso a hardware de servidor para prácticas reales de virtualización no siempre
es posible. Muchos entornos de aprendizaje quedan limitados a simuladores o 
configuraciones poco realistas.

El problema concreto que este proyecto aborda es:

- ¿Cómo practicar Proxmox VE de forma realista sin hardware de datacenter?

- ¿Qué tan viable es reutilizar hardware Apple con chip T2 para virtualización?

- ¿Cuáles son las limitaciones reales y cómo afectan el diseño del laboratorio?

Este documento busca responder esas preguntas de manera honesta, técnica y 
verificable.

## 1.3 ¿Por qué Proxmox VE?

Proxmox VE se elige como plataforma base por las siguientes razones:
    
- Es una solución open-source y ampliamente utilizada en entornos profesionales.

- Integra virtualización con KVM y contenedores LXC de forma nativa.

- Permite trabajar conceptos reales de:

  - Networking

  - Almacenamiento

  - Firewalls

  - Clustering (a nivel teórico/práctico)
    
- Facilita la adopción de criterio de arquitectura tipo datacenter, incluso en un solo nodo.
  
  El objetivo no es simplemente "levantar VMs", sino aprender cómo se diseña, opera y documenta
  infraestructura real.

## 1.4 ¿Por qué reutilizar hardware Apple?

El uso de un Macbook Pro 2018 responde a una decisión pragmática:

- Es hardware disponible, robusto y bien construido.

- Cuenta con CPU Intel compatible con virtualización.

- Presenta desafíos reales (chip T2, firmware, drivers) que obligan a entender 
  el sistema en profundidad.

Lejos de ser una desventaja, estas restricciones convierten al proyecto
en un ejercicio técnico valioso, donde cada decisión debe ser justificada
y documentada.

Este proyecto no recomienda hardware Apple como plataforma estándar para Proxmox,
sino que explora conscientemente sus límites con fines educativos.

## 1.5 Filosofía del laboratorio

La filosofía que guía este laboratorio se basa en los siguientes principios:
  
- 📐 Aquitectura antes que automatización: entender el diseño es prioritario.

- 🧪 Experimentación controlada: cambios documentados, impactos medidos.

- 📜 Documentación como parte del sistema: lo no documentado no existe.

- ⚠️ Expectativas realistas: no es producción, no es alta disponibilidad.

- 🔁 Reproducibilidad: cualquier lector debe poder replicar el entorno.

 Un laboratorio bien diseñado y documentado aporta más valor técnico que 
 hardware costoso mal utilizado.
