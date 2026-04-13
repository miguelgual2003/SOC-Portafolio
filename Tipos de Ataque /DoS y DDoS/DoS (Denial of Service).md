Un ataque de **DoS** es una ofensiva lanzada desde una única fuente que busca agotar los recursos de un sistema para que los usuarios legítimos no puedan acceder a él.

### A. Perfil del atacante

- **Quién:** Individuos con motivaciones personales (venganza), competidores directos o atacantes que buscan probar una vulnerabilidad específica.
    
- **Por qué:** Interrumpir servicios específicos, causar daño reputacional o como distracción para otros ataques (cortina de humo).
    

### B. Vector de ataque (Paso a paso)

1. **Identificación de punto débil:** El atacante analiza si el objetivo es vulnerable a nivel de red (ancho de banda) o de aplicación (recursos de CPU/RAM).
    
2. **Saturación:** Envío masivo de solicitudes diseñadas para consumir un recurso finito.
    
3. **Mantenimiento:** El flujo de datos continúa hasta que el servicio colapsa o el atacante es bloqueado.
    

### C. Funcionamiento técnico interno

Existen dos tipos principales de DoS:

- **Basados en inundación (Flood):** Saturar la capacidad de procesamiento o ancho de banda (ej. ICMP Flood).
    
- **Basados en vulnerabilidad (Logic Attacks):** Enviar un paquete malformado que explota un error en el software para que el sistema se bloquee (ej. el histórico _Ping of Death_ o ataques de fragmentación IP).
    

### D. Ciclo de vida del ataque (Kill Chain)

- **Reconocimiento:** Escaneo de puertos para identificar servicios expuestos.
    
- **Armamentismo:** Configuración de scripts para inundación de tráfico.
    
- **Ejecución:** Lanzamiento del ataque desde la IP del atacante (fácil de identificar).
    
- **Acciones:** El servicio queda fuera de línea (Down).
    

### E. Impacto y consecuencias

- **Indisponibilidad:** Cese de operaciones comerciales.
    
- **Daño de hardware:** En casos extremos, el estrés térmico puede dañar componentes si no hay refrigeración adecuada (poco común pero posible en infraestructuras críticas).
    

### F. Mitigación, detección y respuesta

- **Mitigación:** Configurar límites de conexión por IP (Rate Limiting) y endurecimiento (Hardening) de la pila TCP/IP.
    
- **Detección:** Alertas por consumo inusual de CPU o saturación de ancho de banda.
    
- **Respuesta:** Bloqueo de la IP de origen en el firewall perimetral.
    

---
