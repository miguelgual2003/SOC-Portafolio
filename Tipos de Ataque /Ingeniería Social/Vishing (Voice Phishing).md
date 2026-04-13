Es el uso de la telefonía para realizar ataques de ingeniería social. El atacante utiliza la voz para manipular a la víctima, aprovechando que la comunicación verbal genera una falsa sensación de cercanía y confianza.

### A. Perfil del Atacante

- **Quién:** Estafadores organizados que suelen operar desde "call centers" clandestinos.
    
- **Por qué:** Obtener códigos de verificación (MFA), datos bancarios o acceso a sistemas corporativos mediante el restablecimiento de contraseñas por teléfono.
    

### B. Vector de Ataque (Paso a paso)

1. **Suplantación de identidad (Caller ID Spoofing):** El atacante manipula el identificador de llamadas para que en la pantalla de la víctima aparezca un número legítimo (ej. el soporte técnico de su empresa o su banco).
    
2. **Ganar confianza:** El atacante utiliza datos previos (obtenidos de redes sociales) para demostrar que "conoce" a la víctima.
    
3. **El Incidente:** Se informa de un problema urgente (ej. "Detectamos un acceso sospechoso en su cuenta").
    
4. **Extracción:** Se solicita el dato crítico ("Por seguridad, dígame el código que acaba de recibir por SMS").
    

### C. Funcionamiento Técnico Interno

Se apoya en tecnologías **VoIP (Voz sobre IP)** que permiten automatizar llamadas masivas (robocalls) y modificar los metadatos de la llamada (Caller ID) mediante protocolos SIP. Algunos atacantes utilizan **Deepfakes de voz** (IA) para imitar la voz exacta de un directivo o familiar.

### D. Ciclo de Vida (Kill Chain)

- **Recolección de datos:** Listas de teléfonos y nombres.
    
- **Llamada inicial:** Establecimiento del pretexto.
    
- **Manipulación:** Presión psicológica para evitar que la víctima piense racionalmente.
    
- **Exfiltración:** El usuario dicta la información sensible.
    

### E. Impacto y Consecuencias

- Compromiso de cuentas protegidas por doble factor (MFA).
    
- Transferencias bancarias fraudulentas.
    

### F. Mitigación, Detección y Respuesta

- **Mitigación:** Políticas internas que prohíban compartir secretos por teléfono. Educación sobre "nunca dar el código de SMS".
    
- **Detección:** Sistemas de protección de llamadas en móviles que identifiquen números sospechosos.
    
- **Respuesta:** Colgar y llamar de vuelta a un número oficial conocido.
    

---
