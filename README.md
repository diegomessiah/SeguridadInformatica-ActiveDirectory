### Prácticas de Seguridad para Active Directory

1. **Mantén un número mínimo de usuarios con privilegios**:
   - Limita la cantidad de cuentas con privilegios elevados. Revisa regularmente los grupos privilegiados para asegurarte de que solo los usuarios necesarios tengan acceso².

2. **Utiliza grupos para asignar privilegios**:
   - Asigna permisos a través de grupos en lugar de cuentas individuales. Esto facilita la gestión y auditoría de permisos².

3. **Asegura las cuentas con privilegios de administrador**:
   - Implementa políticas de contraseñas fuertes y habilita la autenticación multifactor (MFA) para todas las cuentas administrativas².

4. **Aplica políticas de contraseñas modernas**:
   - Asegúrate de que todas las cuentas, especialmente las de servicio, utilicen contraseñas complejas y únicas².

5. **Desactiva servicios innecesarios**:
   - Desactiva el servicio Print Spooler y Server Message Block v1 (SMBv1) para reducir la superficie de ataque².

6. **Restringe el acceso a los controladores de dominio (DC)**:
   - Limita el acceso físico y lógico a los controladores de dominio. Solo el personal autorizado debe tener acceso².

7. **Planifica la recuperación de Active Directory**:
   - Ten un plan de recuperación ante desastres que incluya copias de seguridad regulares y pruebas de restauración².

8. **Supervisa Active Directory para detectar actividades sospechosas**:
   - Utiliza herramientas de monitoreo para detectar configuraciones inseguras y actividades inusuales. Configura alertas para responder rápidamente a posibles amenazas².

9. **Implementa la administración por niveles**:
   - Divide tu entorno de Active Directory en niveles de seguridad (por ejemplo, Tier 0, Tier 1, Tier 2) y aplica controles de acceso estrictos entre ellos⁴.

10. **Utiliza el filtrado SID en todos los fideicomisos forestales**:
    - El filtrado SID ayuda a prevenir ataques de escalación de privilegios a través de relaciones de confianza entre bosques².

### Configuraciones Específicas en Active Directory

1. **Habilitar el grupo de seguridad "Usuarios protegidos"**:
   - Este grupo proporciona protecciones adicionales contra el robo de credenciales y no permite el uso de NTLM¹.

2. **Configurar directivas de autenticación**:
   - Utiliza directivas de autenticación para controlar cómo y cuándo se pueden usar las credenciales, incluyendo silos de directivas de autenticación para cuentas privilegiadas¹.

3. **Desactivar NTLM donde sea posible**:
   - Configura tus sistemas para usar Kerberos en lugar de NTLM¹.

4. **Implementar el modo de administración restringida para escritorio remoto**:
   - Protege las credenciales de los administradores al no permitir que se almacenen en caché durante las sesiones de escritorio remoto¹.

5. **Configurar la protección LSA (Local Security Authority)**:
   - Habilita la protección LSA para evitar que el código no autorizado pueda extraer hashes de la memoria¹.
