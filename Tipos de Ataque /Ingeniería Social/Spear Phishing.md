A diferencia del phishing genérico, este es un ataque **dirigido** y altamente personalizado contra un individuo o departamento específico.

### A. Perfil del Atacante

- **Quién:** Grupos de ciberespionaje, APTs o competidores desleales.
    
- **Por qué:** Acceso inicial a redes corporativas protegidas.
    

### B. Vector de Ataque (Paso a paso)

1. **OSINT (Open Source Intelligence):** El atacante investiga a la víctima en LinkedIn, redes sociales o webs corporativas para conocer su puesto, proyectos actuales y quién es su jefe.
    
2. **Creación de Contexto:** El correo es extremadamente creíble ("Hola Juan, adjunto el presupuesto para el Proyecto X que comentamos ayer").
    
3. **Payload Específico:** El archivo adjunto suele ser un documento con un exploit diseñado para evadir el antivirus de esa empresa específica.
    

### C. Funcionamiento Técnico Interno

A menudo utiliza **Typosquatting** (dominios muy parecidos al de la propia empresa). Técnicamente, suelen emplear macros maliciosas en documentos de Office o archivos PDF con scripts que ejecutan comandos de PowerShell en memoria (fileless) para evitar dejar rastro en el disco.

### D. Ciclo de Vida (Kill Chain)

- **Reconocimiento profundo:** Análisis de la cadena de mando de la víctima.
    
- **Armamento:** Creación de un exploit a medida.
    
- **Entrega:** Correo directo y personalizado.
    
- **Instalación:** El usuario confía y ejecuta el malware.
    

### E. Impacto y Consecuencias

- Exfiltración de secretos industriales.
    
- Instalación de persistencia (backdoors) dentro de la red interna.
    

### F. Mitigación, Detección y Respuesta

- **Mitigación:** Concienciación específica (Security Awareness Training) y sandboxing de correos.
    
- **Detección:** Herramientas de análisis de comportamiento que detecten macros sospechosas o conexiones inusuales.
    
- **Respuesta:** Análisis forense del equipo para determinar qué otros sistemas han sido comprometidos lateralmente.
    

---
