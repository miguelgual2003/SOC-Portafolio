El problema del IoT es que son dispositivos con "poca seguridad y mucha conexión".

### 1. Perfil del Atacante

- **Quién:** Operadores de Botnets (ej. Mirai) o actores estatales (ataques a infraestructuras críticas).
    
- **Por qué:** Crear redes de "zombis" para ataques DDoS masivos o espiar a través de cámaras y micrófonos.
    

### 2. Vector de Ataque (Paso a Paso)

1. **Escaneo:** Búsqueda de dispositivos con puertos Telnet o SSH abiertos (usando Shodan).
    
2. **Fuerza Bruta:** Intento de acceso con contraseñas por defecto (admin/admin, 1234, etc.).
    
3. **Compromiso de Firmware:** Subida de un firmware malicioso que convierte al dispositivo en un nodo de ataque.
    

### 3. Funcionamiento Técnico Interno

Muchos dispositivos IoT carecen de **ASLR** o **DEP** (protecciones de memoria básicas), lo que facilita desbordamientos de búfer (_Buffer Overflow_). Además, sus actualizaciones suelen viajar por HTTP sin cifrar, permitiendo ataques de _Man-in-the-Middle_ (MitM) para inyectar código malicioso.

### 4. Impacto y Consecuencias

- **Ataques de Reflexión:** Usar millones de cámaras para tumbar servicios nacionales (DDoS).
    
- **Privacidad:** Filtración de video/audio de entornos privados o industriales.
    

### 5. Mitigación, Detección y Respuesta

- **Mitigación:** Cambiar credenciales por defecto, usar redes VLAN aisladas para IoT y deshabilitar UPnP.
    
- **Detección:** IDS/IPS que detecten tráfico anómalo desde dispositivos que solo deberían enviar datos mínimos.