Es una variante del spear phishing dirigida exclusivamente a la **alta dirección** (CEOs, CFOs, Directores).

### A. Perfil del Atacante

- **Quién:** Delincuentes profesionales especializados en fraude financiero (BEC - Business Email Compromise).
    
- **Por qué:** Autorizar transferencias millonarias o acceder a información estratégica de la junta directiva.
    

### B. Vector de Ataque (Paso a paso)

1. **Suplantación de autoridad:** El atacante se hace pasar por un socio legal, un regulador gubernamental o el CEO (si el objetivo es el CFO).
    
2. **Urgencia crítica:** "Estamos en medio de una adquisición secreta, necesito que autorices este pago de 2 millones de euros antes de que cierre el mercado hoy".
    
3. **Cierre de la operación:** La víctima, bajo presión y ante una figura de autoridad, se salta los procesos de verificación habituales.
    

### C. Funcionamiento Técnico Interno

No siempre requiere malware. A menudo es puramente psicológico, aunque técnicamente puede implicar el compromiso previo del correo de un socio de confianza (Supply Chain Attack) para que el mensaje provenga de una cuenta real y legítima, lo que hace que los filtros técnicos no lo detecten.

### D. Ciclo de Vida (Kill Chain)

- **Identificación del "C-Level":** Localización de ejecutivos con poder de firma.
    
- **Vigilancia:** Entender el lenguaje y tono del ejecutivo suplantado.
    
- **Acción:** Solicitud de transferencia o datos sensibles.
    

### E. Impacto y Consecuencias

- Pérdidas financieras masivas.
    
- Caída del valor de las acciones de la empresa si se filtra información confidencial.
    

### F. Mitigación, Detección y Respuesta

- **Mitigación:** Implementación de **políticas de doble autorización** para transferencias (una firma digital y una llamada telefónica fuera de banda).
    
- **Detección:** Monitorización de correos externos que intentan imitar nombres de ejecutivos internos (Display Name Spoofing).
    
- **Respuesta:** Notificación a las autoridades bancarias y departamentos legales para intentar bloquear fondos.
