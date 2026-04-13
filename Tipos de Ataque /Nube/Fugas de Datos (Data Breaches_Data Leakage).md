A diferencia de la misconfiguración (que es la causa), la fuga de datos es el evento de compromiso del activo más crítico. En la nube, esto suele implicar la exposición de grandes volúmenes de información estructurada y no estructurada.

### 1. Perfil del Atacante

- **Quién:** Actores de amenazas persistentes (APT), competidores corporativos o ciberdelincuentes especializados en el mercado de la _Dark Web_.
    
- **Por qué:** Monetización directa (venta de datos PII/tarjetas de crédito), espionaje industrial o extorsión doble (amenazar con publicar los datos si no se paga un rescate).
    

### 2. Vector de Ataque (Paso a Paso)

1. **Identificación de la Fuente:** El atacante busca puntos de salida de datos, como almacenes de objetos (S3, Azure Blobs), bases de datos RDS expuestas o snapshots de discos (EBS) que han sido marcados como públicos por error.
    
2. **Explotación de Credenciales:** Uso de claves de acceso (`Access Keys`) filtradas en repositorios públicos de código (como GitHub).
    
3. **Descubrimiento de Datos:** Una vez dentro, el atacante utiliza herramientas como `Amazon Macie` (si logra comprometer una cuenta con permisos suficientes) o scripts propios para clasificar dónde están los datos más valiosos.
    
4. **Exfiltración:** Movimiento de los datos desde el entorno de nube de la víctima hacia un entorno controlado por el atacante.
    

### 3. Funcionamiento Técnico Interno

La fuga a menudo aprovecha la **Sincronización de Datos** y las **Snapshots**:

- **Snapshots Públicos:** Un administrador crea un respaldo de un volumen de disco y, para "facilitar" una migración, lo marca como público. El atacante simplemente monta ese snapshot en su propia instancia y tiene una copia idéntica del disco duro, incluyendo archivos de configuración y bases de datos.
    
- **Shadow IT:** Empleados que utilizan servicios de nube no autorizados para mover datos corporativos, saltándose los controles de seguridad perimetrales de la empresa.
    

### 4. Ciclo de Vida del Ataque (Kill Chain)

- **Reconocimiento:** Búsqueda de credenciales en .env, archivos de configuración o logs.
    
- **Explotación:** Uso de credenciales comprometidas para listar recursos de almacenamiento.
    
- **Acciones sobre objetivos:** Transferencia masiva de datos mediante protocolos como HTTPS, DNS tunneling o incluso utilizando las herramientas nativas del proveedor (ej. `aws s3 sync`).
    

### 5. Impacto y Consecuencias

- **Legales:** Litigios masivos y sanciones por incumplimiento de normativas de privacidad.
    
- **Operativos:** Si el atacante borra los datos tras la fuga, se produce una interrupción total del negocio.
    
- **Intelectuales:** Pérdida de ventajas competitivas al filtrarse planos, fórmulas o estrategias.
    

### 6. Mitigación, Detección y Respuesta

- **Mitigación:**
    
    - **Cifrado en Reposo y en Tránsito:** Utilizar KMS (Key Management Service) con rotación automática. Incluso si los datos se filtran, son ilegibles sin las claves.
        
    - **Data Loss Prevention (DLP):** Implementar herramientas que escaneen automáticamente los buckets en busca de patrones (DNI, tarjetas de crédito).
        
- **Detección:**
    
    - Monitoreo de anomalías en el tráfico de red de salida (VPC Flow Logs). Un pico repentino de GBs saliendo hacia una IP desconocida es una alerta crítica.
        
- **Respuesta:**
    
    - Aislamiento de la red y revocación de permisos de las claves comprometidas.
        

---
