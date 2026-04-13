Un ataque Zero-day explota una vulnerabilidad en software o hardware que es **desconocida para el fabricante** y para la cual no existe un parche de seguridad.

### A. Perfil del atacante

- **Quién:** Desarrolladores de exploits de alto nivel, brokers de vulnerabilidades o agencias de inteligencia.
    
- **Por qué:** Su valor en el mercado negro puede oscilar entre los **$50,000 y varios millones de dólares**, dependiendo de la ubicuidad del software (ej. un Zero-day en el kernel de iOS o Windows).
    

### B. Funcionamiento técnico interno

El término "Día Cero" se refiere a que el desarrollador tiene "cero días" para solucionar el problema porque el ataque ya ha ocurrido o la vulnerabilidad ha sido descubierta por un tercero malintencionado. El exploit aprovecha fallos de memoria (buffer overflow), errores de lógica o de desbordamiento de enteros.

### C. Ciclo de vida del ataque

1. **Descubrimiento:** El atacante encuentra un bug mediante ingeniería inversa o _fuzzing_.
    
2. **Desarrollo:** Creación del código (exploit) que aprovecha el bug de forma estable.
    
3. **Uso:** El ataque se lanza contra objetivos de alto valor.
    
4. **Divulgación:** Eventualmente, la comunidad de seguridad detecta el ataque, el fabricante recibe la notificación y se inicia la carrera por el parche.
    

### D. Mitigación

Puesto que no hay parche, la defensa se basa en **Capas de Seguridad**: sandboxing, ASLR (Address Space Layout Randomization) y DEP (Data Execution Prevention), que dificultan la ejecución del exploit aunque la vulnerabilidad exista.

---
