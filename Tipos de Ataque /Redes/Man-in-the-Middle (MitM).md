El ataque de **Man-in-the-Middle** es una de las amenazas más críticas en la capa de red, ya que rompe el principio de confidencialidad e integridad de la comunicación sin que ninguna de las partes legítimas lo note.

### A. Perfil del atacante

- **Quién:** Generalmente es un actor con acceso a la red local (LAN), un administrador de red malintencionado, o un atacante remoto que ha comprometido un nodo de tránsito (como un router).
    
- **Por qué:** El objetivo principal es el espionaje industrial, el robo de credenciales, la interceptación de tokens de sesión o la inyección de datos falsos en una comunicación activa.
    

### B. Vector de ataque (Paso a paso)

1. **Posicionamiento:** El atacante se sitúa físicamente o lógicamente entre la víctima y el recurso al que intenta acceder (ej. una pasarela de enlace o un servidor web).
    
2. **Interceptación:** Utiliza técnicas como el envenenamiento de tablas (ARP/DNS) para forzar que el tráfico pase por su dispositivo.
    
3. **Desencriptación (Opcional):** Si el tráfico es HTTPS, el atacante puede intentar un _SSL Stripping_ para degradar la conexión a HTTP y leer los datos en claro.
    
4. **Manipulación/Reenvío:** El atacante lee los paquetes y los reenvía al destino original para no levantar sospechas (actuando como un relé).
    

### C. Funcionamiento técnico interno

A nivel técnico, el MitM altera el flujo lógico del modelo OSI, específicamente en las Capas 2 (Enlace) o 3 (Red). El atacante convence a la **Máquina A** de que él es la **Máquina B**, y viceversa.

Para que esto ocurra sin interrumpir la conexión, el atacante debe habilitar el **IP Forwarding** en su kernel. De lo contrario, los paquetes morirían en su máquina y la víctima perdería la conexión (denegación de servicio), revelando el ataque.

### D. Ciclo de vida del ataque (Cyber Kill Chain)

1. **Reconocimiento:** Escaneo de la red para identificar objetivos y su puerta de enlace.
    
2. **Preparación:** Configuración de herramientas como `Bettercap`, `Ettercap` o `Mitmproxy`.
    
3. **Distribución/Explotación:** Lanzamiento del envenenamiento (spoofing) para desviar el tráfico.
    
4. **Instalación:** El atacante se establece como el nodo central de la comunicación.
    
5. **Acciones sobre objetivos:** Captura de hashes de contraseñas o cookies de sesión en tiempo real.
    

### E. Impacto y consecuencias

- **Pérdida de Confidencialidad:** Exposición de datos sensibles (bancarios, médicos, corporativos).
    
- **Pérdida de Integridad:** El atacante puede modificar el contenido del tráfico (ej. cambiar un número de cuenta en una transferencia).
    
- **Secuestro de cuentas:** Robo de identidades digitales mediante la captura de credenciales.
    

### F. Mitigación, detección y respuesta

- **Mitigación:** Implementación de **HSTS** (HTTP Strict Transport Security) para forzar conexiones seguras, uso de VPNs en redes no confiables y despliegue de certificados digitales robustos.
    
- **Detección:** Monitorización de latencias inusuales en la red y uso de sistemas **IDS/IPS** que detecten cambios anómalos en las tablas de enrutamiento.
    
- **Respuesta:** Aislamiento del dispositivo atacante y revocación inmediata de todas las sesiones activas interceptadas.
    

---
