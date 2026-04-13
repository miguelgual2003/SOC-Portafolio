El Baiting utiliza la curiosidad o la codicia de la víctima como cebo. A menudo incluye un componente físico.

### A. Perfil del Atacante

- **Quién:** Atacantes locales o internos que tienen acceso físico a las cercanías de la empresa.
    
- **Por qué:** Saltar el "perímetro" de red infectando un equipo desde dentro.
    

### B. Vector de Ataque (Paso a paso)

1. **Preparación del cebo:** El atacante carga un malware en un pendrive USB. A veces pone una etiqueta sugerente como "Salarios 2024" o "Fotos de la fiesta".
    
2. **Abandono:** Deja el USB en un lugar estratégico (parking de la empresa, cafetería, recepción).
    
3. **Curiosidad:** Un empleado lo encuentra y, por curiosidad o querer "devolverlo", lo conecta a su ordenador corporativo.
    
4. **Ejecución:** El malware se ejecuta automáticamente o el usuario abre un archivo que contiene el exploit.
    

### C. Funcionamiento Técnico Interno

Suele usar dispositivos **HID (Human Interface Device)** maliciosos como el "Rubber Ducky". Al conectarse, el ordenador lo reconoce como un **teclado** (no como un disco), lo que le permite "teclear" comandos de PowerShell a velocidad sobrehumana para descargar un backdoor sin que el antivirus bloquee el puerto USB.

### D. Ciclo de Vida (Kill Chain)

- **Siembra:** Colocación física del dispositivo.
    
- **Interacción:** El usuario conecta el dispositivo.
    
- **Infección:** Salto del _Air-gap_ o de las defensas perimetrales.
    

### E. Impacto y Consecuencias

- Compromiso de la red interna desde un nodo confiable.
    
- Robo de datos locales.
    

### F. Mitigación, Detección y Respuesta

- **Mitigación:** Desactivar puertos USB mediante GPO (Group Policy) o software de control de dispositivos. Concienciación sobre "no conectar dispositivos desconocidos".
    
- **Detección:** EDR que bloquee comportamientos sospechosos de dispositivos de entrada (teclados virtuales).
    
- **Respuesta:** Análisis del hardware del USB en un entorno aislado para ingeniería inversa.

