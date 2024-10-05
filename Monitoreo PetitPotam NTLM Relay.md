### Monitoreo y Detección de Ataques de PetitPotam NTLM Relay en Active Directory

#### Introducción
El ataque de PetitPotam es una técnica utilizada por los atacantes para explotar la autenticación NTLM y obtener acceso no autorizado a recursos de red en entornos de Active Directory. Este ataque permite a los atacantes forzar la autenticación NTLM de un controlador de dominio (DC) y luego relayar esas credenciales a un servidor de Active Directory Certificate Services (AD CS) para obtener un certificado que puede ser utilizado para escalar privilegios. En este capítulo, exploraremos cómo monitorear y detectar estos ataques en entornos de Active Directory.

#### 1. Comprensión del Ataque PetitPotam NTLM Relay
**Descripción**: PetitPotam explota el protocolo MS-EFSRPC para forzar a un controlador de dominio a autenticarse utilizando NTLM. Luego, las credenciales NTLM pueden ser relayadas a un servidor AD CS para obtener un certificado que permite la escalación de privilegios⁵.

**Beneficio**: Entender cómo funciona el ataque es crucial para implementar medidas de detección efectivas.

**Pasos para Implementar**:
1. **Forzar Autenticación NTLM**: El atacante utiliza PetitPotam para forzar a un DC a autenticarse con NTLM.
2. **Relay de Credenciales**: Las credenciales NTLM son relayadas a un servidor AD CS para obtener un certificado.
3. **Uso del Certificado**: El certificado obtenido se utiliza para solicitar un Ticket de Concesión de Ticket (TGT) y comprometer el dominio.

#### 2. Monitoreo de Eventos Clave
**Descripción**: Monitorear eventos específicos en Active Directory es crucial para detectar actividades sospechosas relacionadas con PetitPotam NTLM Relay.

**Beneficio**: La detección temprana de actividades sospechosas permite una respuesta rápida para mitigar amenazas.

**Eventos Clave a Monitorear**:
- **ID de Evento 4768**: Solicitud de Ticket de Concesión de Ticket (TGT).
  - **Descripción**: Indica que un usuario ha solicitado un TGT.
  - **Acción**: Revisa solicitudes de TGT que utilicen certificados, especialmente si provienen de cuentas de servicio o administrativas.

- **ID de Evento 4769**: Solicitud de Ticket de Servicio (TGS).
  - **Descripción**: Indica que un usuario ha solicitado un TGS.
  - **Acción**: Monitorea solicitudes de TGS para servicios críticos y verifica que provengan de usuarios autorizados.

- **ID de Evento 4771**: Fallo en la solicitud de Ticket de Concesión de Ticket (TGT).
  - **Descripción**: Indica que una solicitud de TGT ha fallado.
  - **Acción**: Investiga fallos repetidos desde la misma cuenta o IP, ya que pueden indicar intentos de ataque.

#### 3. Uso de Herramientas de Monitoreo y Detección
**Descripción**: Utiliza herramientas especializadas para monitorear y detectar actividades sospechosas en tu entorno de Active Directory.

**Beneficio**: Herramientas avanzadas proporcionan visibilidad en tiempo real y alertas sobre actividades sospechosas.

**Herramientas Recomendadas**:
1. **Microsoft Defender for Identity**: Monitorea eventos de Kerberos y NTLM, y detecta actividades sospechosas.
2. **SIEM (Security Information and Event Management)**: Utiliza herramientas SIEM como Splunk o Microsoft Sentinel para centralizar y analizar eventos de seguridad⁴.

#### 4. Configuración de Alertas
**Descripción**: Configura alertas para actividades sospechosas relacionadas con PetitPotam NTLM Relay.

**Beneficio**: Las alertas permiten una respuesta rápida y proactiva ante posibles amenazas.

**Pasos para Implementar**:
1. **Definición de Reglas de Alerta**: Define reglas de alerta específicas para eventos de solicitud de TGT y TGS que utilicen certificados.
2. **Configuración de Notificaciones**: Configura notificaciones para que el equipo de seguridad reciba alertas en tiempo real.

#### 5. Auditoría y Revisión Regular
**Descripción**: Realiza auditorías y revisiones regulares de los eventos de seguridad y configuraciones de Active Directory.

**Beneficio**: Las auditorías regulares ayudan a identificar y corregir configuraciones inseguras y detectar actividades sospechosas.

**Pasos para Implementar**:
1. **Revisión de Logs**: Revisa regularmente los logs de eventos de autenticación Kerberos y NTLM.
2. **Auditorías de Seguridad**: Realiza auditorías de seguridad periódicas para evaluar la efectividad de las medidas de protección implementadas.

#### 6. Capacitación y Concienciación
**Descripción**: Educa a los usuarios y al equipo de TI sobre las mejores prácticas de seguridad y cómo detectar actividades sospechosas.

**Beneficio**: La capacitación y concienciación mejoran la capacidad de respuesta ante posibles amenazas.

**Pasos para Implementar**:
1. **Programas de Capacitación**: Desarrolla y despliega programas de capacitación en seguridad.
2. **Simulaciones de Ataques**: Realiza simulaciones de ataques para evaluar y mejorar la capacidad de respuesta del equipo de seguridad.

#### 7. Actualización y Parches Regulares
**Descripción**: Mantén todos los sistemas actualizados con los últimos parches de seguridad.

**Beneficio**: Reduce las vulnerabilidades que los atacantes pueden explotar para realizar ataques de relay.

**Pasos para Implementar**:
1. **Política de Actualización**: Establece una política de actualización regular.
2. **Automatización**: Utiliza herramientas de gestión de parches para automatizar el proceso.
3. **Monitoreo**: Monitorea el estado de las actualizaciones y parches.

#### Conclusión
Monitorear y detectar ataques de PetitPotam NTLM Relay en Active Directory es crucial para mantener la seguridad de tu entorno. Implementar estas estrategias avanzadas puede fortalecer significativamente tu capacidad para detectar y responder a estos ataques, mejorando la seguridad general de tu red.
