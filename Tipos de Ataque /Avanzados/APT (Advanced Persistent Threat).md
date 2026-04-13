Una APT no es un "ataque" único, sino una **campaña de intrusión prolongada** y sofisticada dirigida a un objetivo específico.

### A. Perfil del atacante

- **Quién:** Grupos respaldados por estados-nación (ej. Lazarus, APT29, Fancy Bear).
    
- **Por qué:** Espionaje político/militar, robo de propiedad intelectual crítica o sabotaje de infraestructuras nacionales.
    

### B. Funcionamiento técnico interno

A diferencia de un ataque común que busca "entrar y salir", la APT busca **sigilo y persistencia**. Utilizan malware personalizado que no es detectado por antivirus comerciales y se mueven lateralmente por la red durante meses o años sin ser detectados.

### C. Ciclo de vida del ataque (Cyber Kill Chain Extendido)

1. **Reconocimiento:** Meses de recolección de inteligencia sobre empleados y sistemas.
    
2. **Intrusión Inicial:** Generalmente vía _Spear Phishing_ altamente dirigido.
    
3. **Establecimiento de Base:** Instalación de troyanos de acceso remoto (RATs).
    
4. **Movimiento Lateral:** Escalada de privilegios para saltar de un servidor a otro buscando el "tesoro" (datos).
    
5. **Exfiltración:** Extracción de datos de forma lenta y cifrada para no alertar a los sistemas de monitoreo de ancho de banda.
    

### D. Mitigación y Detección

- **Mitigación:** Segmentación de red extrema (Zero Trust) y cifrado de datos en reposo.
    
- **Detección:** Análisis de Comportamiento de Entidades (UEBA) y búsqueda de amenazas proactiva (_Threat Hunting_).
    

---
