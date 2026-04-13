El cryptojacking ha evolucionado de simples scripts en webs a ataques masivos a infraestructuras de orquestación (Kubernetes).

### 1. Perfil del Atacante

- **Quién:** Ciberdelincuentes financieros y grupos de crimen organizado.
    
- **Por qué:** Generar ingresos pasivos con riesgo mínimo. A diferencia del ransomware, el cryptojacking prefiere el **sigilo**; si la víctima no nota que su factura eléctrica o de nube sube, el atacante sigue ganando dinero.
    

### 2. Vector de Ataque (Paso a Paso)

1. **Infiltración:** Aprovechan una vulnerabilidad RCE (ej. Log4Shell) o credenciales de nube débiles.
    
2. **Persistencia:** Despliegan un "dropper" (un script pequeño) que descarga el minero de criptomonedas (usualmente Monero/XMRig por su anonimato).
    
3. **Optimización:** El script detiene otros mineros competidores y limita su propio uso de CPU al 30-50% para no activar alarmas de ventiladores o latencia.
    

### 3. Funcionamiento Técnico Interno

- **Escapismo de Contenedores:** El minero se ejecuta dentro de un contenedor Docker mal configurado, pero intenta saltar al host para usar todos los núcleos del servidor.
    
- **Fileless Execution:** El minero se carga directamente en la memoria RAM, sin dejar archivos en el disco duro, lo que lo hace invisible para antivirus tradicionales.
    

### 4. Ciclo de Vida del Ataque (Kill Chain)

- **Explotación:** Acceso inicial.
    
- **Instalación:** Despliegue del binario minero.
    
- **Comando y Control (C2):** Conexión a un _Mining Pool_ a través de protocolos como _Stratum_.
    
- **Acciones:** Consumo de recursos de procesamiento 24/7.
    

### 5. Impacto y Consecuencias

- **Económico:** Aumento masivo en facturas de AWS/Azure.
    
- **Vida Útil:** Degradación acelerada del hardware físico.
    
- **DoS Indirecto:** El servidor se vuelve tan lento que no puede atender peticiones legítimas.
    

### 6. Mitigación, Detección y Respuesta

- **Mitigación:** Segmentación de red para bloquear protocolos de minería y uso de políticas de ejecución de binarios.
    
- **Detección:** Monitorización de métricas de CPU y tráfico hacia IPs conocidas de pools de minería.
    

---
