# Módulo 2 — Gestión, Riesgo y Cumplimiento en Pruebas de Penetración

**Curso:** Ethical Hacker — Cisco Networking Academy  
**Estado:** Completado ✓  

---

## 2.1 Gestión, riesgo y cumplimiento

### Marcos normativos principales

| Marco | Alcance | Requisito de pentest |
|-------|---------|---------------------|
| PCI DSS | Procesamiento de tarjetas de pago | Pentest anual obligatorio |
| HIPAA | Información médica electrónica (ePHI) | Evaluación de seguridad requerida |
| GDPR | Datos personales en la UE | Auditoría de protección de datos |
| GLBA | Todas las instituciones financieras | Pentest periódico obligatorio |
| FedRAMP | Servicios en la nube para gobierno federal EE.UU. | Autorización federal requerida |
| NY DFS / NYCRR 500 | Entidades financieras en Nueva York | Pentest anual + evaluación semestral |
| NIST SP 800-57 | Organizaciones con claves criptográficas | Guía de gestión de claves |

### Sector financiero
- **GLBA:** aplica a toda organización que realice actividades financieras, sin importar el tamaño.
- **NY DFS Sección 500.05:** pentest anual y evaluación de vulnerabilidades semestral.

### Sector sanitario (HIPAA)
- Publicada el 20/02/2003. Ampliada por HITECH (2009) y Regla Ómnibus (2013).
- Cubre: proveedores de atención médica, planes de salud, centros de información sanitaria y asociados comerciales que manejan ePHI.

### PCI DSS — Detalle

| Término | Descripción |
|---------|-------------|
| QSA | Asesor de seguridad calificado para certificar cumplimiento PCI DSS |
| PFI | Investigador forense de PCI para incidentes con datos de tarjetas |
| ASV | Proveedor de escaneo aprobado (vulnerabilidades externas) |
| PAN | Número de cuenta principal (hasta 19 dígitos); su presencia activa PCI DSS |
| SAD | Datos de autenticación confidenciales: nunca almacenar tras la autorización |
| Adquiriente | Banco que inicia y mantiene la relación con el comerciante |
| Algoritmo de Luhn | Valida tarjetas de crédito e IMEI usando módulo aritmético base 10 |

### Elementos técnicos clave
- **Aislamiento de datos:** segmentación de red para aislar el entorno de datos sensibles (CDE en PCI DSS).
- **Gestión de contraseñas:** no usar valores predeterminados del proveedor; exigir longitud, complejidad, MFA.
- **Gestión de claves (NIST SP 800-57):** proteger claves en todo su ciclo: generación, almacenamiento, distribución, uso y destrucción.

### Restricciones legales
- **CFAA Sección 1030(a)(5)(B):** puede afectar a evaluadores sin autorización escrita en EE.UU.
- **Acuerdo de Wassenaar:** controla exportación de herramientas de seguridad en más de 40 países.
- **CCPA:** protege privacidad de consumidores en California.
- Siempre obtener autorización escrita antes de iniciar cualquier prueba.

### Conceptos legales

| Concepto | Descripción |
|----------|-------------|
| Contrato | Documento principal. Especifica términos, pago y servicios |
| SLA | Service Level Agreement: define el rendimiento mínimo/máximo del servicio |
| NDA | Non-Disclosure Agreement: qué información confidencial no puede divulgarse |
| Confidencialidad | Cómo manejar datos sensibles hallados durante el pentest |
| SOW | Statement of Work: alcance, entregables, metodología y plazos |
| MSA | Master Service Agreement: marco general para relación comercial a largo plazo |

---

## 2.2 Alcance y requisitos del cliente

### Reglas de compromiso

| Elemento | Descripción |
|----------|-------------|
| Línea de tiempo | Fechas de inicio, hitos y entrega del informe (Gantt / WBS) |
| Horas de prueba | Ventanas horarias autorizadas |
| Tipos de prueba permitidos | Qué técnicas y ataques están autorizados o prohibidos |
| Herramientas autorizadas | Lista de herramientas permitidas o no |
| Canales de comunicación | Contactos, escalamiento y métodos seguros (SCP, SFTP, PGP, S/MIME) |
| Permiso de prueba | Documento que autoriza el ataque |

### Activos dentro del alcance
- Rangos de IPs y dispositivos a evaluar
- SSIDs inalámbricos dentro y fuera del alcance
- FQDN/DNS de aplicaciones y subdominios autorizados
- Documentación de API (SOAP, Swagger, WSDL, GraphQL, WADL)
- Restricciones de proveedores de nube (AWS, GCP, Azure)

> **Scope Creep:** si el cliente solicita trabajo adicional fuera de la SOW original, se debe firmar una nueva SOW antes de continuar.

### Entornos desconocidos vs. conocidos

| Tipo | Info proporcionada | Perspectiva | Cuándo usarlo |
|------|--------------------|-------------|---------------|
| Desconocido (caja negra) | Mínima: IPs y dominios | Atacante externo | Evaluar postura de seguridad real |
| Conocido (caja blanca) | Completa: diagramas, código fuente | Auditor interno | Preocupaciones específicas, ahorra tiempo |

- Transferencia de archivos segura: SCP o SFTP
- Correo cifrado: PGP o S/MIME

---

## 2.3 Mentalidad ética — Profesionalismo e integridad

### Prácticas de piratería ética

| Práctica | Descripción |
|----------|-------------|
| Verificación de antecedentes | El cliente puede exigir verificaciones del equipo |
| Cumplimiento del alcance | Respetar lista permitida y denegada. Nunca sobrepasar los límites |
| Reporte de actividad delictiva | Si un atacante real ya comprometió sistemas, reportar inmediatamente |
| Limitar herramientas | Usar solo las herramientas autorizadas |
| Limitar invasividad | Ajustar la invasión de herramientas al alcance acordado |
| Confidencialidad | Toda información accedida durante el pentest debe protegerse |
| Riesgos profesionales | El incumplimiento puede generar multas o cargos penales |

### Gestión del riesgo

| Concepto | Definición |
|----------|------------|
| Apetito al riesgo | Nivel de riesgo que la organización está dispuesta a asumir |
| Tolerancia al riesgo | Variación aceptable alrededor del apetito |
| Evaluación del riesgo | Proceso para calcular el nivel actual de riesgo |
| Aceptación del riesgo | Asumir el riesgo aunque no esté dentro de la tolerancia (requiere alta dirección) |
| Mitigación del riesgo | Acciones para reducir el riesgo a un nivel aceptable |

> **Caso Equifax:** los dos principios éticos violados fueron (1) la obligación de proteger los datos personales y (2) la obligación de informar a los clientes que sus datos fueron divulgados.

---

## Correspondencias clave para el examen

### Marcos normativos
| Marco | Característica clave |
|-------|---------------------|
| PCI DSS | Asegura el procesamiento de tarjetas de crédito y pagos digitales |
| HIPAA | Protege la información médica electrónica (ePHI) |
| GLBA | Se aplica a todas las organizaciones de servicios financieros |
| GDPR | Refuerza la protección de datos personales en la UE |
| NIST SP 800-57 | Directrices para la administración de claves de cifrado |

### Conceptos legales
| Concepto | Ejemplo |
|----------|---------|
| Disclaimer | "El informe no protege contra pérdidas resultantes del acuerdo de prueba" |
| NDA | Especifica qué información confidencial no se puede divulgar a terceros |
| SLA | Documenta el rendimiento mínimo/máximo del servicio de pentest |
| Confidencialidad | Acuerdo sobre cómo manejar credenciales descubiertas durante las pruebas |
