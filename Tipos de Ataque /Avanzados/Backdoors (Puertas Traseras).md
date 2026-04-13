Un backdoor es un método, oculto e indocumentado, para saltarse la autenticación normal y obtener acceso remoto a un sistema.

### A. Tipos de Backdoors

- **De Software:** Código insertado por un desarrollador malintencionado o un atacante después de una intrusión para asegurar que puede volver a entrar si le cierran la puerta principal.
    
- **De Hardware:** Microchips o firmware alterado durante la fabricación (un tipo de ataque de cadena de suministro).
    

### B. Funcionamiento técnico interno

Un backdoor suele abrir un puerto de escucha no estándar o realizar una conexión de salida (**Reverse Shell**) hacia el servidor del atacante. Esto último es más efectivo porque los firewalls suelen bloquear conexiones entrantes, pero son más permisivos con las salientes (tráfico hacia internet).

### C. Ejemplo técnico

Un atacante modifica un script de login para que acepte una contraseña maestra "secreta", independientemente del usuario que intente entrar.

```
// Código legítimo + Backdoor oculto
if (password == user_password || password == "Backdoor_Master_2026!") {
    grant_access();
}
```

### D. Mitigación y Respuesta

- **Integridad de Archivos:** Uso de herramientas como `Tripwire` o `AIDE` que alertan si un archivo del sistema ha sido modificado.
    
- **Auditoría de Código:** Revisión manual y automatizada del código fuente (SAST).
    
- **Respuesta:** Si se detecta un backdoor, se debe reinstalar el sistema operativo desde una fuente limpia, ya que la persistencia del atacante puede estar oculta en niveles muy profundos (como la BIOS/UEFI).
