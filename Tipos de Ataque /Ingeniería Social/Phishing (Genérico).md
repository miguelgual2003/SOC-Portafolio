Es la técnica de ingeniería social más extendida. Consiste en el envío masivo de comunicaciones fraudulentas para engañar a los usuarios y lograr que revelen información sensible o instalen malware.

### A. Perfil del Atacante

- **Quién:** Ciberdelincuentes de nivel bajo a medio (aunque las plantillas pueden ser creadas por profesionales).
    
- **Por qué:** Recolección masiva de credenciales, datos de tarjetas de crédito o despliegue inicial de botnets. Es un juego de volumen: con que caiga el **1%**, el ataque es rentable.
    

### B. Vector de Ataque (Paso a paso)

1. **Suplantación de Identidad (Spoofing):** El atacante crea un correo que imita a una entidad legítima (bancos, Microsoft, servicios de logística).
    
2. **Cebo (Lure):** El mensaje utiliza un tono de **urgencia** o **miedo** ("Su cuenta será bloqueada", "Factura pendiente").
    
3. **Acción del usuario:** El usuario hace clic en un enlace que parece legítimo pero redirige a un servidor controlado por el atacante.
    
4. **Captura:** El usuario introduce sus datos en una web clónica y estos se envían al atacante.
    

### C. Funcionamiento Técnico Interno

Se basa en el uso de **Homograph attacks** (usar caracteres visualmente similares en el dominio, como `g0ogle.com`) y el uso de **acortadores de URL** para ocultar el destino real. A nivel técnico, el atacante configura un servidor con un script (PHP/Python) que captura los datos del formulario POST y los redirige al servidor original para no levantar sospechas tras el robo.

### D. Ciclo de Vida (Kill Chain)

- **Reconocimiento:** Obtención de listas de correos en la Dark Web.
    
- **Preparación:** Creación de la página web clónica y el correo.
    
- **Lanzamiento:** Envío masivo vía SMTP.
    
- **Explotación:** El usuario entrega sus datos voluntariamente bajo engaño.
    

### E. Impacto y Consecuencias

- Robo de identidad y fraude financiero.
    
- Pérdida de acceso a cuentas personales y corporativas.
    

### F. Mitigación, Detección y Respuesta

- **Mitigación:** Implementación de protocolos **DMARC, SPF y DKIM** para evitar la suplantación de dominios.
    
- **Detección:** Filtros antispam con análisis heurístico de URLs y adjuntos.
    
- **Respuesta:** Resetear credenciales inmediatamente y reportar el dominio malicioso a servicios de navegación segura (Google Safe Browsing).
    

---
