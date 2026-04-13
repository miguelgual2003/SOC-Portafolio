Este ataque consiste en la explotación de un mecanismo de control de sesión válido para obtener acceso no autorizado a datos o servicios en un sistema informático. A diferencia del robo de credenciales, aquí el atacante toma el control de una sesión **ya autenticada**.

### A. Perfil del atacante

- **Quién:** Atacantes con capacidad de intercepción de red o acceso a la máquina de la víctima (vía malware o XSS).
    
- **Por qué:** Evadir mecanismos de autenticación multifactor (MFA), ya que el atacante secuestra la sesión después de que el usuario legítimo ya ha superado los retos de seguridad.
    

### B. Vector de ataque (Paso a paso)

1. **Rastreo (Sniffing):** El atacante monitorea el tráfico entre la víctima y el servidor para identificar identificadores de sesión (Session IDs) en cookies o URLs.
    
2. **Predicción/Fuerza Bruta:** Si el ID de sesión es predecible (basado en tiempo o secuencias débiles), el atacante genera IDs válidos.
    
3. **Robo de Token:** Mediante ataques como **Cross-Site Scripting (XSS)**, el atacante ejecuta un script en el navegador de la víctima que envía la cookie de sesión a un servidor controlado por él.
    
4. **Suplantación:** El atacante inyecta el token robado en su propio navegador y realiza peticiones al servidor, que lo reconoce como el usuario autenticado.
    

### C. Funcionamiento técnico interno

El ataque explota la naturaleza de los protocolos sin estado (como HTTP). Para mantener la "memoria" de quién es el usuario, los servidores generan un **Token de Sesión**. El secuestro ocurre cuando el atacante "clona" este token.

En el nivel de transporte (TCP Hijacking), el atacante debe predecir el próximo **Número de Secuencia (SEQ)** y el **Número de Reconocimiento (ACK)** de los paquetes TCP para inyectar sus propios datos en la corriente de comunicación sin romper la conexión.

### D. Ciclo de vida del ataque (Kill Chain)

- **Reconocimiento:** Identificación del método de gestión de sesiones del objetivo.
    
- **Explotación:** Ejecución de XSS, sniffing o predicción de tokens.
    
- **Instalación:** Sustitución del token de sesión propio por el de la víctima.
    
- **Acciones:** Realización de transacciones, cambio de contraseñas o exfiltración de datos sensibles.
    

### E. Impacto y consecuencias

- **Acceso Total:** El atacante actúa con los privilegios del usuario (incluso privilegios de administrador).
    
- **Persistencia:** Si el atacante cambia los datos de recuperación, el usuario legítimo pierde el acceso permanentemente.
    

### F. Mitigación, detección y respuesta

- **Mitigación:** Uso obligatorio de **TLS (HTTPS)** para cifrar tokens en tránsito. Configuración de cookies con atributos `HttpOnly` (evita acceso por JS/XSS) y `Secure` (solo envío por HTTPS). Regeneración del ID de sesión tras el login.
    
- **Detección:** Monitoreo de cambios abruptos en la huella digital del usuario (ej. cambio de IP o User-Agent a mitad de una sesión activa).
    
- **Respuesta:** Invalidación inmediata del ID de sesión afectado y cierre de todas las sesiones activas del usuario.
    

---
