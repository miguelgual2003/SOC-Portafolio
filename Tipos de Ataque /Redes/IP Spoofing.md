Consiste en la creación de paquetes IP con una dirección de origen falsa para ocultar la identidad del remitente o suplantar a otro sistema informático.

### A. Perfil del atacante

- **Quién:** Atacantes remotos que buscan realizar ataques de denegación de servicio o saltar controles de acceso basados en IP.
    
- **Por qué:** Anonimato en ataques de fuerza bruta o bypass de firewalls que confían en IPs específicas.
    

### B. Vector de ataque (Paso a paso)

1. **Selección de objetivo:** Identificación de un sistema que confía en una IP específica (ej. un servidor que permite RSH o conexiones de confianza desde una IP interna).
    
2. **Construcción de Paquetes:** Uso de librerías como `Scapy` para modificar el encabezado IP del paquete.
    
3. **Inyección:** Envío del paquete al objetivo.
    

### C. Funcionamiento técnico interno

En el IP Spoofing, el atacante no recibe las respuestas (ya que estas van a la IP real suplantada). Por ello, es una técnica "ciega" a menos que el atacante esté en la ruta de retorno. Es fundamental en ataques de **Amplificación DNS o NTP**, donde se envía una pequeña consulta con IP suplantada (la de la víctima) y el servidor responde con un paquete gigante a la víctima, saturando su ancho de banda.

### D. Impacto y consecuencias

- **DDoS (Denegación de Servicio Distribuida):** Es el motor de los ataques de reflexión.
    
- **Bypass de ACLs:** Acceso a servicios restringidos si el firewall solo valida la IP de origen sin inspección de estado profunda.
    

### E. Mitigación, detección y respuesta

- **Mitigación:** Implementación de **Filtros de Entrada/Salida (BCP 38)** en routers de borde para descartar paquetes que salen de una red con una IP de origen que no pertenece a ese rango.
    
- **Detección:** Análisis de flujos de red que muestran tráfico unidireccional masivo.
    
- **Respuesta:** Reglas de filtrado dinámicas en firewalls perimetrales.

