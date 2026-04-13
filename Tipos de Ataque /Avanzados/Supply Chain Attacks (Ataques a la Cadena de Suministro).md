En lugar de atacar directamente a una empresa protegida, el atacante compromete a un **proveedor de confianza** de esa empresa (software, hardware o servicios).

### A. Perfil del atacante

Actores muy avanzados que buscan un "efecto multiplicador". Al infectar a un solo proveedor, ganan acceso automático a miles de sus clientes.

### B. Vector de ataque (Ejemplo SolarWinds / Kaseya)

1. **Compromiso del Proveedor:** El atacante hackea el entorno de desarrollo de una empresa de software.
    
2. **Inyección de Código:** Inserta un backdoor en una **actualización legítima** del software.
    
3. **Distribución:** El proveedor firma digitalmente la actualización infectada y la envía a todos sus clientes.
    
4. **Ejecución:** Los clientes instalan la actualización "oficial", abriendo la puerta al atacante sin saberlo.
    

### C. Impacto

Es catastrófico porque la víctima confía en el origen del software. Las herramientas de seguridad suelen ignorar los archivos firmados por proveedores legítimos.

### D. Mitigación

Verificación de integridad de software (hashes), análisis de composición de software (SCA) para revisar librerías de terceros y exigir auditorías de seguridad a los proveedores.

---
