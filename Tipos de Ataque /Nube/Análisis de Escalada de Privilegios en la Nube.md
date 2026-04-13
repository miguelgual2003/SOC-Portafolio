Este ataque ocurre cuando un usuario o servicio con permisos limitados logra obtener permisos de un nivel superior (ej. de un rol de solo lectura a Administrador).

### 1. Perfil del Atacante

- **Quién:** Usuarios internos malintencionados o atacantes externos que ya han comprometido una credencial inicial (phishing, robo de tokens).
    
- **Por qué:** Para obtener persistencia, desactivar logs de seguridad y realizar exfiltración de datos sin restricciones.
    

### 2. Vector de Ataque (Paso a Paso)

1. **Acceso Inicial:** El atacante compromete una instancia EC2 o una función Lambda a través de una vulnerabilidad de aplicación (ej. SSRF).
    
2. **Extracción de Metadatos:** Consulta al servicio de metadatos de la instancia (IMDS) para obtener credenciales temporales del rol asignado a esa instancia.
    
    - `curl http://169.254.169.254/latest/meta-data/iam/security-credentials/nombre-del-rol`
        
3. **Enumeración de Permisos:** Uso de herramientas como `Pacu` para identificar qué acciones puede realizar ese rol.
    
4. **Explotación de Permisos:** Si el rol tiene permisos como `iam:CreatePolicyVersion` o `iam:AttachUserPolicy`, el atacante puede auto-asignarse privilegios de administrador.
    

### 3. Funcionamiento Técnico Interno

Se basa en la explotación de **Permisos Excesivos**. Un ejemplo técnico clásico es el permiso `iam:PassRole`.

- Si un usuario tiene `iam:PassRole` y `ec2:RunInstances`, puede crear una nueva instancia de computación, pasarle un rol de Administrador y luego entrar en esa instancia para ejecutar comandos con total control sobre la cuenta de nube.
    

### 4. Ciclo de Vida del Ataque (Cyber Kill Chain)

- **Reconocimiento:** Identificación de roles asociados a servicios.
    
- **Explotación:** Compromiso del servicio (ej. vía Server-Side Request Forgery - SSRF).
    
- **Instalación:** Creación de nuevas versiones de políticas de IAM o creación de nuevos usuarios/claves de acceso.
    
- **Acciones sobre objetivos:** Borrado de backups, despliegue de mineros de criptomonedas a gran escala.
    

### 5. Impacto y Consecuencias

- **Control Total de la Infraestructura:** El atacante puede "secuestrar" la cuenta completa.
    
- **Persistencia Silenciosa:** Creación de puertas traseras que son difíciles de detectar si no se auditan los cambios en IAM.
    

### 6. Mitigación, Detección y Respuesta

- **Mitigación:**
    
    - Implementar **Permissions Boundaries** (Límites de permisos) para asegurar que un usuario nunca pueda exceder un nivel máximo de privilegios, incluso si tiene permisos de modificación de políticas.
        
    - Actualizar a **IMDSv2** en AWS para prevenir ataques de SSRF.
        
- **Detección:**
    
    - Alertas de GuardDuty o Azure Sentinel ante llamadas a la API sospechosas (ej. múltiples intentos fallidos de `iam:PutUserPolicy`).
        
- **Respuesta:**
    
    - Revocación inmediata de todas las sesiones de IAM del usuario comprometido.
        
    - Rotación de credenciales y auditoría de todas las políticas modificadas en las últimas horas.

