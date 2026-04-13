Un ataque de replay ocurre cuando un atacante intercepta una transmisión de datos válida y, posteriormente, la **retransmite** para producir un efecto malicioso (como una transacción duplicada o una autenticación).

### A. Perfil del atacante

- **Quién:** Un atacante con acceso pasivo para capturar tráfico y activo para reinyectarlo. Puede ser un actor interno o alguien en la misma red Wi-Fi.
    
- **Por qué:** Para realizar acciones sin conocer necesariamente las credenciales del usuario, simplemente "repitiendo" un mensaje que el sistema ya aceptó una vez.
    

### B. Vector de ataque (Paso a paso)

1. **Captura:** El atacante utiliza un sniffer para grabar un intercambio de red específico (ej. un comando de "abrir puerta" en un sistema IoT o una instrucción de transferencia bancaria).
    
2. **Almacenamiento:** El paquete capturado se guarda íntegramente, incluyendo los hashes o firmas digitales que contenía en ese momento.
    
3. **Inyección:** En un momento posterior, el atacante reenvía ese paquete exacto al servidor de destino.
    
4. **Ejecución:** El servidor, si no tiene protecciones, procesa el paquete como si fuera una nueva solicitud legítima.
    

### C. Funcionamiento técnico interno

El éxito de este ataque radica en la falta de **frescura** (_freshness_) de los datos. Si el protocolo no incluye un marcador temporal (timestamp) o un número de un solo uso (**Nonce**), el receptor no tiene forma de saber si el paquete fue generado hace un segundo o hace una hora.

### D. Ciclo de vida del ataque (Kill Chain)

- **Reconocimiento:** Identificación de protocolos que no implementan secuenciación o timestamps.
    
- **Preparación:** Captura de paquetes clave durante una sesión legítima.
    
- **Ejecución:** Reenvío del tráfico capturado.
    
- **Acciones:** Duplicidad de acciones financieras, acceso físico (en sistemas de radiofrecuencia) o bypass de autenticación.
    

### E. Impacto y consecuencias

- **Fraude Financiero:** Duplicación de pagos.
    
- **Acceso no autorizado:** Replay de tickets de autenticación (como en versiones antiguas de Kerberos o sistemas de llaves remotas de vehículos).
    
- **Corrupción de datos:** Reenvío de comandos de configuración que pueden desestabilizar un sistema.
    

### F. Mitigación, detección y respuesta

- **Mitigación:** * **Nonces:** Inclusión de números aleatorios que solo son válidos para una transacción.
    
    - **Timestamps:** Marcas de tiempo que limitan la validez del paquete a unos pocos milisegundos.
        
    - **Secuenciación:** Uso de números de secuencia estrictos donde el receptor descarta cualquier número menor o igual al último recibido.
        
- **Detección:** Registro de firmas de paquetes recientes para detectar duplicidad exacta en períodos cortos de tiempo.
    
- **Respuesta:** Bloqueo de la fuente de la retransmisión y auditoría de las acciones realizadas mediante el replay para revertir cambios.

