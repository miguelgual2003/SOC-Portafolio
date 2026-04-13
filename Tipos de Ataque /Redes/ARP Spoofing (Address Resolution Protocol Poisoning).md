Este es un ataque de Capa 2 (Enlace de datos) que explota la falta de autenticación en el protocolo ARP, diseñado para mapear direcciones IP a direcciones MAC.

### A. Perfil del atacante

- **Quién:** Un atacante con acceso a la red local (Ethernet o Wi-Fi). No requiere privilegios de administrador en la red, solo la capacidad de enviar paquetes crudos (_raw packets_).
    
- **Por qué:** Su objetivo es interceptar, modificar o detener el tráfico entre dos hosts (generalmente un usuario y su puerta de enlace).
    

### B. Vector de ataque (Paso a paso)

1. **Escaneo de Red:** El atacante identifica la dirección IP y MAC de la víctima y del router (Gateway).
    
2. **Envío de Respuestas Gratuitas:** El atacante envía paquetes `ARP Reply` no solicitados a la víctima diciendo: _"Yo soy el Router (IP del router), mi MAC es [MAC del atacante]"_.
    
3. **Envenenamiento Dual:** Simultáneamente, envía un paquete al router diciendo: _"Yo soy la víctima (IP de la víctima), mi MAC es [MAC del atacante]"_.
    
4. **Persistencia:** El atacante debe enviar estos paquetes continuamente para evitar que las entradas legítimas actualicen la tabla ARP (cache).
    

### C. Funcionamiento técnico interno

El protocolo ARP es "stateless" (sin estado). Los dispositivos aceptan respuestas ARP incluso si no han enviado una solicitud previa. Al recibir la respuesta falsa, el switch o el host actualizan su **Tabla ARP**. A partir de ese momento, toda la trama Ethernet dirigida a la IP de la víctima llegará físicamente a la interfaz del atacante.

### D. Ciclo de vida del ataque (Kill Chain)

- **Reconocimiento:** Mapeo de la LAN mediante `arp-scan` o `nmap`.
    
- **Explotación:** Inyección de paquetes mediante herramientas como `arpspoof` o `Ettercap`.
    
- **Instalación/Ejecución:** El atacante se sitúa en medio del flujo de datos.
    
- **Acciones:** Sniffing de tráfico o denegación de servicio (si el atacante decide no reenviar los paquetes).
    

### E. Impacto y consecuencias

- **Interrupción de servicio:** Si el atacante no reenvía el tráfico correctamente.
    
- **Facilitación de MitM:** Es el precursor necesario para leer tráfico cifrado mediante SSL Stripping.
    

### F. Mitigación, detección y respuesta

- **Mitigación:** Configuración de **DAI (Dynamic ARP Inspection)** en switches gestionables, que valida los paquetes ARP contra una base de datos de confianza (DHCP Snooping). Uso de tablas ARP estáticas en servidores críticos.
    
- **Detección:** Monitorización con herramientas como `Arpwatch` que alertan cuando una IP cambia de dirección MAC (flip-flop).
    
- **Respuesta:** Bloqueo del puerto del switch asociado a la MAC del atacante.
    

---
