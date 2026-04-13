Es una técnica avanzada de DDoS que permite a un atacante con poco ancho de banda generar un ataque masivo, utilizando servidores de terceros como "lupas".

### A. Perfil del atacante

- **Quién:** Atacantes que buscan maximizar el daño con recursos mínimos.
    
- **Por qué:** Permite ocultar la IP real (usa IP Spoofing) y multiplicar la potencia del ataque por factores de hasta 50,000x.
    

### B. Vector de ataque (Paso a paso)

1. **Suplantación (Spoofing):** El atacante envía una solicitud a un servidor vulnerable (DNS, NTP, Memcached) falsificando la IP de origen: pone la IP de la **víctima**.
    
2. **Solicitud Pequeña:** Envía una consulta que requiere una respuesta muy grande (ej. "dame todos los registros de esta zona DNS").
    
3. **Reflexión y Amplificación:** El servidor responde a la IP de la víctima con un paquete enorme.
    
4. **Saturación:** La víctima recibe gigabits de datos que nunca solicitó.
    

### C. Funcionamiento técnico interno

Este ataque explota protocolos basados en **UDP**, ya que no requieren un apretón de manos (handshake) y permiten el spoofing de IP de forma sencilla.

- **Factor de Amplificación (BAF):** Es la relación entre el tamaño de la solicitud del atacante y la respuesta del servidor.
    
    - **DNS:** ~50x amplificación.
        
    - **Memcached:** ¡Hasta 51,000x! (Un ataque de 1MB se convierte en 51GB sobre la víctima).
        

### D. Ciclo de vida del ataque (Kill Chain)

- **Reconocimiento:** Búsqueda de servidores "Open Resolvers" (DNS configurados incorrectamente).
    
- **Explotación:** Envío masivo de consultas UDP suplantadas.
    
- **Acciones:** Colapso instantáneo del enlace de red de la víctima debido al volumen de datos entrantes.
    

### E. Impacto y consecuencias

- **Saturación de ISP:** A menudo el ataque es tan grande que no solo cae la víctima, sino también el proveedor de servicios de internet (ISP) local.
    

### F. Mitigación, detección y respuesta

- **Mitigación:** Deshabilitar servicios UDP innecesarios en la red. Configurar servidores DNS/NTP para que no respondan a solicitudes externas de forma abierta.
    
- **Detección:** Observar grandes volúmenes de tráfico UDP entrante desde puertos conocidos (53 para DNS, 123 para NTP).
    
- **Respuesta:** Implementación de filtrado en el borde del ISP (Source Address Validation) para evitar que paquetes suplantados salgan de sus redes.

