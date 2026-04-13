Es el equivalente al phishing pero a través de mensajes de texto (SMS) o aplicaciones de mensajería como WhatsApp o Telegram.

### A. Perfil del Atacante

- **Quién:** Grupos cibercriminales que buscan ataques rápidos y de bajo coste.
    
- **Por qué:** Los usuarios suelen confiar más en un SMS que en un correo electrónico, y las tasas de apertura son mucho más altas.
    

### B. Vector de Ataque (Paso a paso)

1. **Envío masivo:** Envío de miles de SMS con enlaces acortados.
    
2. **Cebo:** Suele ser una alerta de un servicio de mensajería ("Paquete retenido en aduanas") o un banco ("Nueva actualización de seguridad obligatoria").
    
3. **Acción:** La víctima hace clic desde su smartphone, un dispositivo que suele tener menos protecciones que un PC corporativo.
    
4. **Infección/Captura:** Descarga de un APK malicioso (en Android) o robo de credenciales en web móvil.
    

### C. Funcionamiento Técnico Interno

Utilizan **Gateways de SMS** comerciales para envíos masivos. En el caso de Android, el ataque suele derivar en la instalación de un **Troyano Bancario** que solicita permisos de "Accesibilidad" para leer todo lo que ocurre en la pantalla y capturar las claves del banco.

### D. Ciclo de Vida (Kill Chain)

- **Distribución:** Envío a bases de datos de números móviles.
    
- **Engaño:** Mensaje corto con enlace.
    
- **Ejecución:** Apertura del enlace en el navegador móvil.
    
- **Impacto:** Robo de datos o suscripción a servicios premium.
    

### E. Impacto y Consecuencias

- Robo de credenciales.
    
- Instalación de spyware en el dispositivo personal/corporativo.
    

### F. Mitigación, Detección y Respuesta

- **Mitigación:** Desactivar la instalación de aplicaciones de "Fuentes desconocidas" en móviles corporativos.
    
- **Detección:** Filtros de operadores de telefonía y soluciones MTM (_Mobile Threat Defense_).
    
- **Respuesta:** Bloqueo de la tarjeta SIM si se sospecha de _SIM Swapping_.
    

---
