A diferencia del MitM activo, el **Sniffing** puede ser puramente pasivo, lo que lo hace extremadamente difícil de detectar.

### A. Perfil del atacante

- **Quién:** Un usuario interno curioso o un atacante que ya ha logrado persistencia en un sistema dentro de la red.
    
- **Por qué:** Recolección de información masiva (recolección de inteligencia) para preparar ataques posteriores más dirigidos.
    

### B. Vector de ataque (Paso a paso)

1. **Acceso:** Obtención de acceso a un segmento de red (físico o mediante compromiso de un host).
    
2. **Modo Promiscuo:** El atacante pone su tarjeta de red (NIC) en **modo promiscuo**. Normalmente, una NIC solo procesa paquetes dirigidos a su propia MAC; en este modo, procesa _todo_ lo que circula por el medio físico.
    
3. **Captura:** Uso de un analizador de protocolos para volcar el tráfico a un archivo `.pcap`.
    
4. **Análisis:** Filtrado del tráfico capturado para extraer protocolos inseguros (Telnet, FTP, HTTP, SNMP v1/v2).
    

### C. Funcionamiento técnico interno

En redes con **hubs** (concentradores), el sniffing es trivial porque el hub replica el tráfico a todos los puertos. En redes modernas con **switches**, el sniffing requiere técnicas adicionales (como el _MAC Flooding_) para forzar al switch a comportarse como un hub (entrar en modo _fail-open_) o el uso de un puerto **SPAN/TAP** si el atacante tiene privilegios de administrador.

### D. Ciclo de vida del ataque (Cyber Kill Chain)

1. **Reconocimiento:** Identificar si la red es conmutada (switched) o compartida.
    
2. **Explotación:** Activar el modo promiscuo y, si es necesario, saturar la tabla CAM del switch.
    
3. **Acciones sobre objetivos:** Análisis de protocolos de capa de aplicación para extraer datos en texto plano.
    

### E. Impacto y consecuencias

- **Divulgación de información:** Exposición de topología de red, versiones de software y políticas internas.
    
- **Compromiso de credenciales:** Captura de usuarios y contraseñas enviados sin cifrar.
    

### F. Mitigación, detección y respuesta

- **Mitigación:** **Cifrado de extremo a extremo** (TLS, IPsec). Desactivar protocolos inseguros. Implementar Seguridad de Puerto (Port Security) en switches para limitar las direcciones MAC por puerto.
    
- **Detección:** Herramientas que buscan interfaces en modo promiscuo enviando paquetes de prueba (ej. herramientas como `nmap` con scripts de detección de sniffing).
    
- **Respuesta:** Identificación del puerto físico en el switch y desconexión inmediata del host sospechoso.

