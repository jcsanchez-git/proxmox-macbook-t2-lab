# 05. Limitaciones



## 5.1 Limitaciones estructurales

El hardware utilizado en este proyecto presenta limitaciones inherentes a su diseño como equipo portátil y no como servidor:

- Ausencia de memoria ECC.
- Falta de interfaces de gestión remota (IPMI, iDRAC, iLO).
- Almacenamiento interno sin soporte para RAID por hardware.
- Formato portátil con refrigeración diseñada para cargas intermitentes.
- Dependencia de firmware propietario de Apple.

Estas limitaciones no dependen del sistema operativo ni de la configuración, sino del diseño físico y arquitectónico del equipo.

## 5.2 Limitaciones operativas

En operación continua, el equipo presenta restricciones prácticas:

- No está diseñado para funcionamiento 24/7 bajo carga sostenida.
- Posible thermal throttling en escenarios de uso intensivo.
- Recuperación ante fallos menos predecible que en hardware de servidor.
- Wake-on-LAN poco confiable o inexistente.

Dependencia de periféricos externos (USB-C a Ethernet).

Estas limitaciones afectan la forma en que el laboratorio debe ser operado y mantenido.

## 5.3 Limitaciones de rendimiento

Desde el punto de vista del rendimiento, deben considerarse los siguientes aspectos:

- Rendimiento de CPU adecuado para cargas ligeras y medias, pero no sostenidas.
- Memoria RAM limitada a 16 GB sin posibilidad de expansión.
- Almacenamiento rápido, pero no optimizado para I/O intensivo prolongado.
- Contención térmica bajo cargas concurrentes elevadas.

El rendimiento es suficiente para aprendizaje y pruebas, pero no para cargas críticas.


## 5.4 Limitaciones de soporte

El uso de este hardware como nodo Proxmox implica restricciones claras en soporte:

- No existe soporte oficial por parte de Apple para Linux en equipos con chip T2.
- Proxmox VE no certifica ni recomienda este escenario.
- Dependencia de la comunidad para parches y soluciones.
- Riesgo de incompatibilidades tras actualizaciones de kernel.

Estas limitaciones deben asumirse antes de adoptar el entorno.

## 5.5 Escenarios no recomendados

Dadas las limitaciones descritas, no se recomienda utilizar este entorno para:

- Entornos de producción.
- Servicios críticos o de alta disponibilidad.
- Bases de datos sensibles o de alta carga.
- Passthrough PCI avanzado.
- Escenarios que requieran soporte empresarial o SLA.

El laboratorio está orientado exclusivamente a aprendizaje, experimentación y formación técnica.
