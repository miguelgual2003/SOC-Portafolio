Ataque de nivel superior que consiste en introducir información falsa en la caché de un servidor DNS para redirigir a los usuarios a destinos maliciosos.

### A. Perfil del atacante

- **Quién:** Puede ser un atacante local o un actor remoto que explota vulnerabilidades en servidores DNS desactualizados.
    
- **Por qué:** Phishing masivo, distribución de malware o interceptación de tráfico de servicios específicos (como servidores de correo).
    

### B. Vector de ataque (Paso a paso)

1. **Solicitud DNS:** El atacante identifica que una víctima o un servidor DNS resolverá un dominio (ej. `banco.com`).
    
2. **Suplantación de Respuesta:** El atacante envía una respuesta DNS falsa a la víctima antes de que llegue la respuesta legítima del servidor DNS real.
    
3. **Envenenamiento de Caché:** Si el servidor DNS intermedio acepta la respuesta falsa, la almacenará en su caché para todos los usuarios de esa red.
    

### C. Funcionamiento técnico interno

El atacante debe adivinar o predecir el **Transaction ID (ID de transacción)** de 16 bits y el puerto de origen de la consulta DNS. Si logra enviar el paquete falso con el ID correcto antes que el servidor legítimo, la víctima aceptará la IP maliciosa como válida.

### D. Ciclo de vida del ataque (Kill Chain)

- **Preparación:** Configuración de un servidor web falso que clone la apariencia del sitio legítimo.
    
- **Explotación:** Inundación de respuestas DNS falsas (Birthday Attack o Kaminsky Attack).
    
- **Acciones:** Captura de credenciales en el sitio clonado.
    

### E. Impacto y consecuencias

- **Phishing a gran escala:** Los usuarios entran en sitios falsos creyendo que la URL es correcta.
    
- **Evasión de seguridad:** Redirección de servidores de actualización de software hacia servidores con malware.
    

### F. Mitigación, detección y respuesta

- **Mitigación:** Implementación de **DNSSEC** (firmas digitales para registros DNS), aleatorización de puertos de origen y uso de servidores DNS públicos reputados con protecciones integradas.
    
- **Detección:** Auditoría de registros DNS y comparación de respuestas de múltiples fuentes.
    
- **Respuesta:** Limpiar la caché DNS (`flush`) y parchear vulnerabilidades en los resolutores.
    

---
