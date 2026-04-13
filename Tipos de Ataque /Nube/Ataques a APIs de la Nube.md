Las APIs son el "pegamento" de la nube. Todo lo que haces en la consola web es, en realidad, una llamada a una API. Atacar la API es atacar el plano de control de toda la infraestructura.

### 1. Perfil del Atacante

- **Quién:** Atacantes técnicos avanzados que comprenden la arquitectura de microservicios y el desarrollo de software.
    
- **Por qué:** Para manipular la infraestructura de forma programática, automatizar la destrucción de recursos o realizar ataques de denegación de servicio (DoS) a nivel de aplicación.
    

### 2. Vector de Ataque (Paso a Paso)

1. **Inyección de Parámetros:** El atacante manipula las llamadas a la API para intentar acceder a recursos de otros usuarios (BOLA - Broken Object Level Authorization).
    
2. **Ataque de Replay:** Captura de tokens de autenticación (JWT) para repetirlos y ganar acceso.
    
3. **Abuso de Lógica de Negocio:** Explotar cómo los diferentes servicios de nube interactúan entre sí a través de sus APIs para saltarse validaciones.
    

### 3. Funcionamiento Técnico Interno

- **Exposición de Endpoints:** A menudo, las APIs de gestión interna o de desarrollo quedan expuestas a internet sin los niveles de autenticación adecuados.
    
- **Inseguridad en los Tokens:** Uso de tokens JWT (JSON Web Tokens) con algoritmos de firma débiles o sin fecha de expiración, lo que permite al atacante realizar ataques de "hijacking" de sesión persistentes.
    
- **Shadow APIs:** APIs que no están documentadas ni bajo el control del equipo de seguridad, pero que tienen acceso a la base de datos de producción.
    

### 4. Ciclo de Vida del Ataque (Kill Chain)

- **Reconocimiento:** Fuzzing de endpoints (ej. `/api/v1/user/123` -> `/api/v1/user/124`).
    
- **Explotación:** Descubrimiento de una vulnerabilidad de autorización.
    
- **Acciones sobre objetivos:** Modificación de registros, robo de tokens de sesión de otros usuarios o ejecución de código remoto (RCE) si la API procesa entradas sin desinfectar.
    

### 5. Impacto y Consecuencias

- **Integridad de Datos:** Alteración de información crítica (precios, balances de cuentas, configuraciones de seguridad).
    
- **Indisponibilidad:** Un ataque de saturación a la API puede dejar a todos los usuarios legítimos sin servicio.
    

### 6. Mitigación, Detección y Respuesta

- **Mitigación:**
    
    - Implementar un **API Gateway** con límites de tasa (_Rate Limiting_) y autenticación fuerte (OAuth2 / OIDC).
        
    - Validación estricta de esquemas de entrada.
        
- **Detección:**
    
    - Análisis de logs de API (ej. AWS CloudTrail para APIs de infraestructura, logs de Nginx/Envoy para APIs de aplicación).
        
    - Búsqueda de patrones de escaneo (muchos errores 401 o 403 en poco tiempo).
        
- **Respuesta:**
    
    - Bloqueo de IPs de origen y rotación de secretos de la API.
