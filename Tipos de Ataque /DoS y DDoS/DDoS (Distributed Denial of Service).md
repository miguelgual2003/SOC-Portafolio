

El **DDoS** es la evolución del DoS. La inundación de tráfico proviene de **miles de fuentes distintas** (Botnets), lo que hace que el bloqueo por IP sea inefectivo.

### A. Perfil del atacante

- **Quién:** Grupos de ciberdelincuencia organizada, estados-nación (hacktivismo) o servicios de "DDoS-for-hire" (booters).
    
- **Por qué:** Extorsión económica, sabotaje político o guerra cibernética.
    

### B. Vector de ataque (Paso a paso)

1. **Infección (Botnet):** El atacante infecta miles de dispositivos (IoT, cámaras, servidores) con malware para convertirlos en "zombis".
    
2. **C&C (Command & Control):** El atacante envía una orden centralizada a todos los bots.
    
3. **Ataque Coordinado:** Todas las máquinas infectadas atacan simultáneamente al mismo objetivo.
    
4. **Saturación Multicapa:** El ataque puede ser volumétrico (capa 3/4) o de aplicación (capa 7).
    

### C. Funcionamiento técnico interno

El DDoS abruma las infraestructuras mediante:

- **Ataques de agotamiento de estado TCP:** Como el **SYN Flood**, donde se dejan miles de conexiones "medio abiertas", agotando la tabla de conexiones del servidor.
    
- **Ataques de Capa 7 (HTTP Flood):** Simulan tráfico humano legítimo (ej. recargar una página de búsqueda miles de veces), lo que consume RAM y base de datos, siendo muy difíciles de filtrar.
    

### D. Ciclo de vida del ataque (Kill Chain)

- **Instalación:** Creación y mantenimiento de la Botnet.
    
- **Comando:** Instrucción de ataque vía C&C.
    
- **Explotación:** Inundación masiva de tráfico desde múltiples zonas geográficas.
    
- **Acciones:** Caída total de la infraestructura (servidores, firewalls y balanceadores).
    

### E. Impacto y consecuencias

- **Impacto Financiero:** Pérdidas millonarias por cada hora de inactividad.
    
- **Efecto Cascada:** La caída de un servicio puede afectar a proveedores y socios vinculados.
    

### F. Mitigación, detección y respuesta

- **Mitigación:** Uso de servicios de limpieza de tráfico (Scrubbing Centers) como Cloudflare o Akamai. Implementación de **Anycast** para distribuir el ataque.
    
- **Detección:** Análisis de anomalías de tráfico mediante protocolos NetFlow o IPFIX.
    
- **Respuesta:** Desviar el tráfico a través de un servicio de mitigación DDoS y aplicar reglas de desafío (como CAPTCHAs) para separar bots de humanos.
    

---
