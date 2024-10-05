### Eventos Clave para Monitorear y Detectar Ataques de Pass-the-Ticket en Active Directory

#### Introducción
El ataque de Pass-the-Ticket (PtT) es una técnica utilizada por los atacantes para obtener acceso no autorizado a recursos de red en entornos que utilizan Kerberos, el protocolo de autenticación predeterminado en Active Directory. Este ataque explota los tickets de concesión de tickets (TGT) y los tickets de servicio dentro del proceso de autenticación Kerberos. En este capítulo, exploraremos los eventos clave que debes vigilar y cómo configurarlos para mejorar la seguridad de tu entorno.

#### 1. Eventos de Autenticación Kerberos
Monitorear los eventos de autenticación Kerberos es crucial para detectar actividades sospechosas relacionadas con Pass-the-Ticket:

- **ID de Evento 4768**: Solicitud de Ticket de Concesión de Ticket (TGT).
  - **Descripción**: Indica que un usuario ha solicitado un TGT.
  - **Acción**: Revisa solicitudes de TGT desde cuentas de servicio o administrativas, especialmente fuera del horario laboral.

- **ID de Evento 4769**: Solicitud de Ticket de Servicio (TGS).
  - **Descripción**: Indica que un usuario ha solicitado un TGS.
  - **Acción**: Monitorea solicitudes de TGS para servicios críticos y verifica que provengan de usuarios autorizados.

- **ID de Evento 4771**: Fallo en la solicitud de Ticket de Concesión de Ticket (TGT).
  - **Descripción**: Indica que una solicitud de TGT ha fallado.
  - **Acción**: Investiga fallos repetidos desde la misma cuenta o IP, ya que pueden indicar intentos de ataque.

- **ID de Evento 4776**: Fallo en la autenticación NTLM.
  - **Descripción**: Indica que una autenticación NTLM ha fallado.
  - **Acción**: Monitorea fallos de autenticación NTLM, especialmente en cuentas administrativas, para detectar posibles intentos de Pass-the-Ticket.

#### 2. Eventos de Uso de Credenciales
Estos eventos ayudan a detectar el uso indebido de tickets de Kerberos:

- **ID de Evento 4649**: Detección de uso de credenciales duplicadas.
  - **Descripción**: Indica que se han detectado credenciales duplicadas en uso.
  - **Acción**: Investiga inmediatamente cualquier uso de credenciales duplicadas, ya que puede ser un indicio de un ataque en curso.

- **ID de Evento 4627**: Identificación de un intento de inicio de sesión con credenciales duplicadas.
  - **Descripción**: Ocurre cuando se detecta un intento de inicio de sesión con credenciales duplicadas.
  - **Acción**: Revisa los sistemas y cuentas involucradas en estos intentos para identificar posibles compromisos.

#### 3. Eventos de Cambios en la Configuración de Seguridad
Monitorear cambios en la configuración de seguridad puede ayudar a detectar intentos de comprometer la seguridad del sistema:

- **ID de Evento 4719**: Cambios en la política de auditoría del sistema.
  - **Descripción**: Indica que se ha cambiado la política de auditoría.
  - **Acción**: Verifica que los cambios sean autorizados y necesarios para evitar configuraciones inseguras.

- **ID de Evento 4732**: Añadir un miembro a un grupo de seguridad.
  - **Descripción**: Indica que se ha añadido un miembro a un grupo de seguridad.
  - **Acción**: Asegúrate de que las adiciones sean legítimas y documentadas para evitar escalaciones de privilegios no autorizadas.

- **ID de Evento 4733**: Eliminar un miembro de un grupo de seguridad.
  - **Descripción**: Indica que se ha eliminado un miembro de un grupo de seguridad.
  - **Acción**: Revisa las eliminaciones para asegurarte de que no sean maliciosas y que no comprometan la seguridad del grupo.

#### 4. Eventos de Acceso a Recursos
Monitorear el acceso a recursos críticos puede ayudar a detectar movimientos laterales y accesos no autorizados:

- **ID de Evento 5140**: Acceso a un recurso compartido de red.
  - **Descripción**: Indica que un usuario ha accedido a un recurso compartido de red.
  - **Acción**: Monitorea accesos inusuales o fuera del horario laboral para detectar posibles compromisos.

- **ID de Evento 5145**: Acceso a un archivo o carpeta en un recurso compartido de red.
  - **Descripción**: Indica que un usuario ha accedido a un archivo o carpeta en un recurso compartido.
  - **Acción**: Revisa accesos a archivos y carpetas sensibles para identificar actividades sospechosas.

#### Herramientas y Técnicas de Monitoreo

1. **SIEM (Security Information and Event Management)**
   - Utiliza herramientas SIEM para centralizar y analizar los eventos de seguridad. Herramientas como Splunk, ArcSight, y Microsoft Sentinel pueden ayudarte a correlacionar eventos y detectar patrones sospechosos.

2. **Microsoft Advanced Threat Analytics (ATA)**
   - ATA puede detectar actividades sospechosas relacionadas con Pass-the-Ticket, como el uso de credenciales duplicadas y movimientos laterales.

3. **Azure Advanced Threat Protection (ATP)**
   - ATP proporciona visibilidad en tiempo real y alertas sobre actividades sospechosas en tu entorno de Active Directory.

4. **Auditoría de Seguridad**
   - Configura políticas de auditoría para registrar eventos críticos y asegúrate de que los registros se almacenan de manera segura y se revisan regularmente.

#### Conclusión
Monitorear estos eventos y utilizar las herramientas adecuadas puede ayudarte a detectar y responder rápidamente a los ataques de Pass-the-Ticket, mejorando la seguridad de tu entorno de Active Directory. La combinación de monitoreo continuo, análisis de eventos y respuesta rápida es esencial para mantener una postura de seguridad robusta.

