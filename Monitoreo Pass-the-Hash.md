### Eventos Clave para Monitorear y Detectar Ataques de Pass-the-Hash en Active Directory

#### Introducción
El ataque de Pass-the-Hash (PtH) es una técnica utilizada por los atacantes para moverse lateralmente dentro de una red comprometida, utilizando hashes de contraseñas en lugar de las contraseñas en texto claro. Detectar estos ataques requiere monitorear eventos específicos en Active Directory. En este capítulo, exploraremos los eventos clave que debes vigilar y cómo configurarlos para mejorar la seguridad de tu entorno.

#### 1. Eventos de Inicio de Sesión (Logon Events)
Monitorear los eventos de inicio de sesión es crucial para detectar actividades sospechosas. Aquí están los eventos más importantes:

- **ID de Evento 4624**: Inicio de sesión exitoso.
  - **Descripción**: Indica que un usuario ha iniciado sesión correctamente.
  - **Acción**: Revisa inicios de sesión desde ubicaciones inusuales o fuera del horario laboral.

- **ID de Evento 4625**: Intento de inicio de sesión fallido.
  - **Descripción**: Indica que un intento de inicio de sesión ha fallado.
  - **Acción**: Investiga múltiples intentos fallidos desde la misma IP o cuenta.

- **ID de Evento 4648**: Inicio de sesión con credenciales explícitas.
  - **Descripción**: Ocurre cuando un proceso intenta iniciar sesión con credenciales explícitas.
  - **Acción**: Monitorea el uso de credenciales administrativas en sistemas no autorizados.

- **ID de Evento 4672**: Inicio de sesión con privilegios especiales.
  - **Descripción**: Indica que un usuario ha iniciado sesión con privilegios elevados.
  - **Acción**: Asegúrate de que solo las cuentas autorizadas tengan estos privilegios.

#### 2. Eventos de Autenticación Kerberos
Kerberos es el protocolo de autenticación predeterminado en Active Directory. Monitorear sus eventos puede ayudar a detectar ataques de Pass-the-Hash:

- **ID de Evento 4768**: Solicitud de Ticket de Concesión de Ticket (TGT).
  - **Descripción**: Indica que un usuario ha solicitado un TGT.
  - **Acción**: Revisa solicitudes de TGT desde cuentas de servicio o administrativas.

- **ID de Evento 4769**: Solicitud de Ticket de Servicio (TGS).
  - **Descripción**: Indica que un usuario ha solicitado un TGS.
  - **Acción**: Monitorea solicitudes de TGS para servicios críticos.

- **ID de Evento 4771**: Fallo en la solicitud de Ticket de Concesión de Ticket (TGT).
  - **Descripción**: Indica que una solicitud de TGT ha fallado.
  - **Acción**: Investiga fallos repetidos desde la misma cuenta o IP.

- **ID de Evento 4776**: Fallo en la autenticación NTLM.
  - **Descripción**: Indica que una autenticación NTLM ha fallado.
  - **Acción**: Monitorea fallos de autenticación NTLM, especialmente en cuentas administrativas.

#### 3. Eventos de Uso de Credenciales
Estos eventos ayudan a detectar el uso indebido de credenciales:

- **ID de Evento 4649**: Detección de uso de credenciales duplicadas.
  - **Descripción**: Indica que se han detectado credenciales duplicadas en uso.
  - **Acción**: Investiga inmediatamente cualquier uso de credenciales duplicadas.

- **ID de Evento 4627**: Identificación de un intento de inicio de sesión con credenciales duplicadas.
  - **Descripción**: Ocurre cuando se detecta un intento de inicio de sesión con credenciales duplicadas.
  - **Acción**: Revisa los sistemas y cuentas involucradas en estos intentos.

#### 4. Eventos de Cambios en la Configuración de Seguridad
Monitorear cambios en la configuración de seguridad puede ayudar a detectar intentos de comprometer la seguridad del sistema:

- **ID de Evento 4719**: Cambios en la política de auditoría del sistema.
  - **Descripción**: Indica que se ha cambiado la política de auditoría.
  - **Acción**: Verifica que los cambios sean autorizados y necesarios.

- **ID de Evento 4732**: Añadir un miembro a un grupo de seguridad.
  - **Descripción**: Indica que se ha añadido un miembro a un grupo de seguridad.
  - **Acción**: Asegúrate de que las adiciones sean legítimas y documentadas.

- **ID de Evento 4733**: Eliminar un miembro de un grupo de seguridad.
  - **Descripción**: Indica que se ha eliminado un miembro de un grupo de seguridad.
  - **Acción**: Revisa las eliminaciones para asegurarte de que no sean maliciosas.

#### 5. Eventos de Acceso a Recursos
Monitorear el acceso a recursos críticos puede ayudar a detectar movimientos laterales y accesos no autorizados:

- **ID de Evento 5140**: Acceso a un recurso compartido de red.
  - **Descripción**: Indica que un usuario ha accedido a un recurso compartido de red.
  - **Acción**: Monitorea accesos inusuales o fuera del horario laboral.

- **ID de Evento 5145**: Acceso a un archivo o carpeta en un recurso compartido de red.
  - **Descripción**: Indica que un usuario ha accedido a un archivo o carpeta en un recurso compartido.
  - **Acción**: Revisa accesos a archivos y carpetas sensibles.

#### Herramientas y Técnicas de Monitoreo

1. **SIEM (Security Information and Event Management)**
   - Utiliza herramientas SIEM para centralizar y analizar los eventos de seguridad. Herramientas como Splunk, ArcSight, y Microsoft Sentinel pueden ayudarte a correlacionar eventos y detectar patrones sospechosos.

2. **Microsoft Advanced Threat Analytics (ATA)**
   - ATA puede detectar actividades sospechosas relacionadas con Pass-the-Hash, como el uso de credenciales duplicadas y movimientos laterales.

3. **Azure Advanced Threat Protection (ATP)**
   - ATP proporciona visibilidad en tiempo real y alertas sobre actividades sospechosas en tu entorno de Active Directory.

4. **Auditoría de Seguridad**
   - Configura políticas de auditoría para registrar eventos críticos y asegúrate de que los registros se almacenan de manera segura y se revisan regularmente.

#### Conclusión
Monitorear estos eventos y utilizar las herramientas adecuadas puede ayudarte a detectar y responder rápidamente a los ataques de Pass-the-Hash, mejorando la seguridad de tu entorno de Active Directory. La combinación de monitoreo continuo, análisis de eventos y respuesta rápida es esencial para mantener una postura de seguridad robusta.
