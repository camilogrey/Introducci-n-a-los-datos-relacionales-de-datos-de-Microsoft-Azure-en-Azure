# Exploración de los servicios de bases de datos relacionales en Azure

* 10 min. restante  
* Módulo  
* 5 de 6 unidades completadas

PrincipianteAnalista de datosIngeniero de datosAdministrador de base de datosEstudianteAzure

Microsoft Azure proporciona varios servicios para bases de datos relacionales. Puede elegir el sistema de administración de bases de datos relacionales que mejor se adapte a sus necesidades y hospedar datos relacionales en la nube.

## Objetivos de aprendizaje

En este módulo aprenderá a:

* Identificar las opciones para los servicios de Azure SQL.  
* Identifique las opciones para las bases de datos de código abierto en Azure.  
* Aprovisionar un servicio de base de datos en Azure.

\[\]()

# Introducción

Azure admite varios servicios de base de datos, lo que permite ejecutar en la nube diversos sistemas de administración de bases de datos relacionales conocidos, por ejemplo, SQL Server, PostgreSQL y MySQL.

La mayoría de los servicios de base de datos de Azure están totalmente administrados, con lo cual dispondrá de un tiempo muy valioso que, de otro modo, desperdiciaría administrando la base de datos. El rendimiento de nivel empresarial con alta disponibilidad integrada significa que es posible realizar un escalado rápidamente y conseguir una distribución global sin preocuparse de los costosos tiempos de inactividad. Los desarrolladores pueden sacar partido de innovaciones punteras en el sector, como la seguridad integrada con supervisión automática y detección de amenazas, y el ajuste automático para mejorar el rendimiento. Además, aparte de todas estas características, la disponibilidad está garantizada.

En este módulo, explorará las opciones disponibles para los servicios de bases de datos relacionales en Azure.

# Descripción de los servicios y las capacidades de Azure SQL

Completado

100 XP

* 10 minutos

Azure SQL es un término colectivo para referirse a una familia de servicios de base de datos basados en Microsoft SQL Server en Azure. Los servicios específicos de Azure SQL incluyen los siguientes:

* SQL Server en Azure Virtual Machines (VMs) \- Una máquina virtual que se ejecuta en Azure con SQL Server instalado. El uso de una máquina virtual convierte esta opción en una solución de infraestructura como servicio (IaaS) que permite virtualizar la infraestructura de hardware para proceso, almacenamiento y redes en Azure. Por este motivo, se trata de una opción excelente para la migración lift-and-shift de instalaciones locales de SQL Server a la nube.  
* Azure SQL Managed Instance: una opción de plataforma como servicio (PaaS) que proporciona una compatibilidad casi completa con instancias de SQL Server locales y permite abstraer el hardware y el sistema operativo subyacentes. Este servicio incluye administración automatizada de actualizaciones de software, copias de seguridad y otras tareas de mantenimiento, lo que reduce la carga administrativa que supone admitir una instancia de servidor de bases de datos.  
* Azure SQL Database : un servicio de base de datos PaaS totalmente administrado y altamente escalable diseñado para la nube. Este servicio incluye las principales capacidades de base de datos de SQL Server local y es una buena opción cuando hay que crear una aplicación en la nube.

## Comparación de los servicios de Azure SQL

| \-- | SQL Server en Máquinas virtuales de Azure | Azure SQL Managed Instance | Azure SQL Database |
| ----- | ----- | ----- | ----- |
|  | ![Captura de pantalla del logotipo de una máquina virtual de Azure con SQL Server.][image1] | ![Captura de pantalla de un logotipo de Instancia administrada de Azure SQL.][image2] | ![Captura de pantalla de un logotipo de Azure SQL Database.][image3] |
| Tipo de servicio en la nube | IaaS | PaaS (Plataforma como Servicio) | PaaS (Plataforma como Servicio) |
| Compatibilidad con SQL Server | Es totalmente compatible con instalaciones físicas y virtualizadas locales. Las aplicaciones y bases de datos se pueden migrar fácilmente usando el método lift-and-shift y sin cambios. | Es casi completamente compatible con SQL Server. La mayoría de las bases de datos locales se pueden migrar con cambios mínimos de código mediante [El servicio Azure Database Migration](https://learn.microsoft.com/es-es/azure/dms) | Admite la mayoría de las funcionalidades básicas de base de datos de SQL Server. Es posible que algunas características de las que dependa una aplicación local no estén disponibles. |
| Arquitectura | Las instancias de SQL Server se instalan en una máquina virtual. Cada instancia puede admitir varias bases de datos. | Cada instancia administrada puede admitir varias bases de datos. Además, los *grupos de instancias* se pueden usar para compartir recursos de forma eficaz entre instancias más pequeñas. | Puede aprovisionar una *base de datos única* en un servidor dedicado administrado (lógico); o puede usar un *grupo elástico* para compartir recursos en varias bases de datos y aprovechar la escalabilidad a petición. |
| Disponibilidad | 99,99 % | 99,99 % | 99,995 % |
| Administración | Debe administrar todos los aspectos del servidor, incluidos el sistema operativo y SQL Server, la configuración, las copias de seguridad y otras tareas de mantenimiento. | Actualizaciones, copias de seguridad y recuperación totalmente automatizados | Actualizaciones, copias de seguridad y recuperación totalmente automatizados |
| Casos de uso | Use esta opción cuando necesite migrar o ampliar una solución de SQL Server local y conservar el control total sobre todos los aspectos de la configuración del servidor y la base de datos. | Use esta opción para la mayoría de los escenarios de migración a la nube, especialmente cuando necesite cambios mínimos en las aplicaciones existentes. | Use esta opción para nuevas soluciones en la nube o para migrar aplicaciones que tengan dependencias mínimas de instancia. |

## SQL Server en Azure Virtual Machines

SQL Server en Virtual Machines le permite usar versiones completas de SQL Server en la nube sin tener que administrar ningún hardware local. Este es un ejemplo del enfoque de IaaS.

Al ejecutar SQL Server en una máquina virtual de Azure, se replica la base de datos que se ejecuta en un hardware local real. La migración desde el sistema local a una máquina virtual de Azure no es diferente a migrar las bases de datos de un servidor local a otro.

Este enfoque es adecuado para las migraciones y aplicaciones que requieren acceso a características del sistema operativo que podrían no admitirse en el nivel de PaaS. Las máquinas virtuales de SQL están listas para *migrar mediante lift-and-shift* las aplicaciones existentes que requieren una migración rápida a la nube con unos cambios mínimos. También puede usar SQL Server en máquinas virtuales de Azure para ampliar las aplicaciones locales existentes a la nube en implementaciones híbridas.  
 Nota:

Una *implementación híbrida* es un sistema en el que parte de la operación se ejecuta de forma local y forma parte de la nube. La base de datos podría formar parte de un sistema más grande que se ejecuta de forma local, aunque los elementos de la base de datos podrían estar hospedados en la nube.

Puede usar SQL Server en una máquina virtual para desarrollar y probar aplicaciones de SQL Server tradicionales. Con una máquina virtual, tiene todos los derechos administrativos sobre el sistema operativo y el DBMS. Es una opción perfecta cuando una organización ya tiene recursos de TI disponibles para mantener las máquinas virtuales.

Estas funcionalidades le permiten:

* Cree escenarios de desarrollo y prueba rápidos cuando no quiera comprar hardware de SQL Server local y que no sea de producción.  
* Tener todo preparado para migrar mediante lift-and-shift las aplicaciones existentes que requieren una migración rápida a la nube con cambios mínimos o sin cambios.  
* Escalar verticalmente la plataforma en la que se ejecuta SQL Server asignando más memoria, potencia de CPU y espacio en disco a la máquina virtual. Puede cambiar rápidamente el tamaño de una máquina virtual de Azure sin tener que reinstalar el software que se ejecuta en ella.

### Ventajas empresariales

La ejecución de SQL Server en máquinas virtuales le permite satisfacer necesidades empresariales exclusivas y diversas a través de una combinación de implementaciones locales y hospedadas en la nube, a la vez que usa el mismo conjunto de productos de servidor, herramientas de desarrollo y conocimientos en estos entornos.

No siempre es fácil para las empresas cambiar su DBMS a un servicio totalmente administrado. Puede ser necesario cumplir requisitos específicos para poder migrar a un servicio administrado que requiere realizar cambios en la base de datos y en las aplicaciones que lo usan. Por esta razón, el uso de máquinas virtuales puede ofrecer una solución, pero no elimina la necesidad de administrar el DBMS tan cuidadosamente como lo haría en el entorno local.

## Azure SQL Managed Instance

Azure SQL Managed Instance permite ejecutar eficazmente una instancia totalmente controlable de SQL Server en la nube. Además, puede instalar varias bases de datos en la misma instancia y tiene un control total sobre esta instancia, como el que tendría sobre un servidor local. Con SQL Managed Instance se automatizan las copias de seguridad, la aplicación de revisiones de software, la supervisión de bases de datos y otras tareas generales, pero sigue teniendo control total sobre la seguridad y la asignación de recursos para las bases de datos. Puede encontrar información detallada en [¿Qué es Azure SQL Managed Instance?](https://learn.microsoft.com/es-es/azure/sql-database/sql-database-managed-instance).

Las instancias administradas dependen de otros servicios de Azure, como Azure Storage para las copias de seguridad, Azure Event Hubs para la telemetría, Microsoft Entra ID para la autenticación, Azure Key Vault para el cifrado de datos transparente (TDE), y un par de servicios de la plataforma de Azure que proporcionan características de seguridad y compatibilidad. Las instancias administradas realizan conexiones con estos servicios.

Todas las comunicaciones están cifradas y firmadas mediante certificados. Para comprobar la confiabilidad de las partes que se comunican, las instancias administradas comprueban constantemente estos certificados a través de listas de revocación de certificados. Si los certificados se revocan, la instancia administrada cierra las conexiones para proteger los datos.

### Casos de uso

Considere la posibilidad de usar Azure SQL Managed Instance si desea *migrar mediante lift-and-shift* una instancia local de SQL Server y todas sus bases de datos a la nube, sin incurrir en la sobrecarga de administración de ejecutar SQL Server en una máquina virtual.

Azure SQL Managed Instance incluye características que no están disponibles en Azure SQL Database (se describen a continuación). Si su sistema usa características como servidores vinculados, Service Broker (un sistema de procesamiento de mensajes que se puede usar para distribuir el trabajo entre servidores) o Correo electrónico de base de datos (que permite a la base de datos enviar mensajes de correo electrónico a los usuarios), debe usar la opción Instancia administrada. Para comprobar la compatibilidad con un sistema local existente, puede instalar [Data Migration Assistant (DMA).](https://www.microsoft.com/download/details.aspx?id=53595) Esta herramienta analiza sus bases de datos en SQL Server e informa de los problemas que podrían bloquear la migración a una instancia administrada.

### Ventajas empresariales

Permite a un administrador del sistema dedicar menos tiempo a tareas administrativas, ya que el servicio las realiza automáticamente o las simplifica en gran medida. Entre las tareas automatizadas se incluyen: la instalación y revisión del software del sistema operativo y del sistema de administración de bases de datos, el cambio de tamaño y la configuración de instancias dinámicas, la realización de copias de seguridad, la replicación de bases de datos (incluidas las bases de datos del sistema), la configuración de alta disponibilidad, y la configuración de flujos de datos de supervisión del estado y del rendimiento.

Tiene una compatibilidad casi completa con SQL Server Enterprise Edition, que se ejecuta de forma local.

Admite inicios de sesión del motor de base de datos de SQL Server e inicios de sesión integrados en Microsoft Entra ID. Los inicios de sesión del motor de base de datos de SQL Server incluyen un nombre de usuario y una contraseña. Debe escribir sus credenciales cada vez que se conecta al servidor. Los inicios de sesión de Microsoft Entra usan las credenciales asociadas con el inicio de sesión del equipo actual y no es necesario que las proporcione cada vez que se conecta al servidor.

## Azure SQL Database

Azure SQL Database es una oferta de PaaS de Microsoft. Después de crear un servidor de bases de datos administrado en la nube, debe implementar las bases de datos en este otro servidor.  
 Nota:

Un servidor de SQL Database es una construcción lógica que actúa como punto administrativo central para varias bases de datos individuales o agrupadas, inicios de sesión, reglas de firewall, reglas de auditoría, directivas de detección de amenazas y grupos de conmutación por error.

Azure SQL Database está disponible como una *base de datos única* o un grupo *elástico*.

### Base de datos única

Esta opción le permite configurar y ejecutar rápidamente una sola base de datos de SQL Server. Puede crear y ejecutar un servidor de bases de datos en la nube y acceder a la base de datos a través de este servidor. Microsoft administra el servidor, por lo que solo tiene que configurar la base de datos, crear las tablas y rellenarlas con sus datos. Puede escalar la base de datos si necesita más espacio de almacenamiento, memoria o potencia de procesamiento. De forma predeterminada, los recursos están asignados previamente y se le cobra por hora por los recursos que ha solicitado. También puede especificar una configuración *sin servidor* . En esta configuración, Microsoft crea su propio servidor, que se puede compartir entre las bases de datos que pertenecen a otros suscriptores de Azure. En este caso, Microsoft garantiza la privacidad de su base de datos. Su base de datos se escala automáticamente y los recursos se asignan o desasignan según sea necesario.

### Grupo elástico

Esta opción es similar a *Base de datos única*, excepto que, por defecto, varias bases de datos pueden compartir los mismos recursos, como la memoria, el espacio de almacenamiento de datos y la capacidad de procesamiento, a través de la multitenencia. Los recursos se conocen como un *grupo*. Al crear un grupo, solo sus bases de datos pueden usarlo. Este modelo es útil si tiene bases de datos con requisitos de recursos que varían con el tiempo, además, puede ayudarle a reducir los costos. Por ejemplo, su base de datos de nóminas puede requerir una gran cantidad de potencia de CPU al final de cada mes a medida que se encarga del procesamiento de nóminas, pero en otras ocasiones la base de datos podría estar mucho menos activa. Es posible que tenga otra base de datos para ejecutar informes. Esta base de datos podría activarse durante varios días a mediados del mes mientras se generan informes de administración, pero podría tener una carga más ligera en otras ocasiones. La opción Grupo elástico le permite usar los recursos disponibles en el grupo y liberarlos una vez que se haya completado el procesamiento.

### Casos de uso

Azure SQL Database ofrece la mejor opción por un costo bajo con administración mínima. No es totalmente compatible con las instalaciones de SQL Server locales. A menudo se usa en nuevos proyectos en la nube, donde el diseño de la aplicación puede acomodar los cambios necesarios en las aplicaciones.  
 Nota:

Puede usar la herramienta Data Migration Assistant para detectar problemas de compatibilidad con sus bases de datos que pueden afectar a su funcionalidad en Azure SQL Database. Para obtener más información, consulte [Introducción a Data Migration Assistant](https://learn.microsoft.com/es-es/sql/dma/dma-overview).

Azure SQL Database se suele usar para:

* Aplicaciones modernas en la nube que necesitan usar las características estables más recientes de SQL Server.  
* Aplicaciones que requieren alta disponibilidad.  
* Sistemas con una carga variable que necesitan escalar y reducir verticalmente el servidor de bases de datos de forma rápida.

### Ventajas empresariales

Azure SQL Database actualiza automáticamente el software de SQL Server y le aplica revisiones para asegurarse de que siempre se ejecuta la versión más reciente y más segura del servicio.

Las características de escalabilidad de Azure SQL Database garantizan que pueda aumentar los recursos disponibles para almacenar y procesar los datos sin tener que llevar a cabo una actualización manual costosa.

Este servicio proporciona garantías de alta disponibilidad para garantizar que las bases de datos están disponibles al menos el 99,995 % del tiempo. Azure SQL Database admite la restauración a un momento dado, lo que le permite recuperar una base de datos al estado en que se encontraba en cualquier momento del pasado. Las bases de datos se pueden replicar en distintas regiones para proporcionar más resistencia y una mayor recuperación ante desastres.

Advanced Threat Protection proporciona funcionalidades de seguridad avanzadas, como las evaluaciones de vulnerabilidad, para ayudar a detectar y corregir posibles problemas de seguridad con las bases de datos. También detecta actividades anómalas que indican intentos poco habituales y posiblemente dañinos de acceder a sus bases de datos o aprovecharse de ellas. Supervisa constantemente la base de datos para detectar actividades sospechosas y proporciona de forma inmediata alertas de seguridad de posibles vulnerabilidades, ataques por inyección de código SQL y patrones anómalos de acceso a las bases de datos. Las alertas de detección de amenazas proporcionan detalles de la actividad sospechosa y recomiendan acciones sobre cómo investigar y mitigar la amenaza.

La auditoría hace un seguimiento de los eventos de una base de datos y los escribe en un registro de auditoría de su cuenta de almacenamiento de Azure. La auditoría puede ayudarle a mantener el cumplimiento de normativas, comprender la actividad de las bases de datos y conocer las discrepancias y anomalías que pueden indicar problemas en el negocio o presuntas violaciones de seguridad.

SQL Database ayuda a proteger los datos proporcionando cifrado que protege los datos almacenados en la base de datos (*en reposo*) y mientras se transfieren a través de la red (*en movimiento*).

# Descripción de los servicios de Azure para bases de datos de código abierto

Completado

100 XP

* 5 minutos

Además de los servicios de Azure SQL, los servicios de datos de Azure están disponibles para otros sistemas populares de bases de datos relacionales, como MySQL y PostgreSQL. La razón principal de incluir estos servicios es permitir que las organizaciones que los usan en aplicaciones locales migren a Azure rápidamente, sin necesidad de realizar cambios significativos en sus aplicaciones.

## ¿Qué son MySQL y PostgreSQL?

MySQL y PostgreSQL son sistemas de administración de bases de datos relacionales que se adaptan a diferentes especializaciones.

MySQL comenzó siendo un sistema de administración de bases de datos de código abierto fácil de usar. Es la base de datos relacional de código abierto líder para aplicaciones de pila de *Linux, Apache, MySQL y PHP* (LAMP). Está disponible en varias ediciones; Community, Estándar y Enterprise. La edición Community está disponible de forma gratuita y se ha usado históricamente como sistema de administración de bases de datos para aplicaciones web que se ejecutan en Linux. También hay versiones disponibles para Windows. La edición Estándar ofrece mayor rendimiento y usa una tecnología diferente para almacenar los datos. La edición Enterprise proporciona un completo conjunto de herramientas y características, entre las que se incluyen seguridad mejorada, disponibilidad y escalabilidad. Las ediciones Estándar y Enterprise son las más usadas por las organizaciones comerciales, aunque estas versiones del software no son gratuitas.

PostgreSQL es una base de datos híbrida de objetos relacionales. Una base de datos de PostgreSQL permite almacenar datos en tablas relacionales, pero también tipos de datos personalizados con sus propias propiedades no relacionales. El sistema de administración de bases de datos es extensible, es decir, se pueden agregar módulos de código a la base de datos, los cuales pueden ejecutarse mediante consultas. Otra característica clave es su capacidad de almacenar y manipular datos geométricos, como líneas, círculos y polígonos.

PostgreSQL dispone de su propio lenguaje de consulta llamado *pgsql*. Este lenguaje es una variante del lenguaje de consulta relacional estándar, SQL, y cuenta con características que permiten escribir procedimientos almacenados que se ejecutan en la base de datos.

## Azure Database for MySQL

![Captura de pantalla de un logotipo de Azure Database for MySQL.][image4] Azure Database for MySQL es una implementación PaaS de MySQL en la nube de Azure que se basa en la edición Community de MySQL.

El servicio Azure Database for MySQL incluye alta disponibilidad sin costos adicionales y escalabilidad según sea necesario. Solo paga por lo que usa. Se proporcionan copias de seguridad automáticas con restauración a un momento dado.

El servidor ofrece seguridad de conexión para aplicar las reglas de firewall y, opcionalmente, requerir conexiones SSL. Muchos parámetros de servidor permiten configurar opciones del servidor, como los modos de bloqueo, el número máximo de conexiones y los tiempos de espera.

Azure Database for MySQL proporciona un sistema de base de datos global que se puede escalar verticalmente a bases de datos grandes sin necesidad de administrar el hardware, los componentes de red, los servidores virtuales, las revisiones de software y otros componentes subyacentes.

Hay algunas operaciones que no están disponibles con Azure Database for MySQL. Estas funciones están relacionadas principalmente con la seguridad y la administración. Azure administra estos aspectos del propio servidor de bases de datos.

### Ventajas de Azure Database for MySQL

Azure Database for MySQL ofrece las siguientes características:

* Características de alta disponibilidad integradas.  
* Rendimiento predecible.  
* Escalado sencillo que responde rápidamente a la demanda.  
* Protección de los datos, tanto en reposo como en movimiento.  
* Copias de seguridad automáticas y restauración en un momento específico de los últimos 35 días.  
* Seguridad de categoría empresarial y cumplimiento normativo.

El sistema utiliza un modelo de precios de pago por uso, de manera que solo pagas por lo que realmente utilizas.

Los servidores de Azure Database for MySQL proporcionan funcionalidades de supervisión para agregar alertas y para ver las métricas y los registros.

### Azure Database for MySQL: servidor flexible

La opción de implementación flexible-servidor es un servicio de base de datos totalmente administrado diseñado para proporcionar un control y flexibilidad más granulares sobre las funciones de administración de bases de datos y las opciones de configuración. Proporciona controles de optimización de costos y es la opción de implementación recomendada para las nuevas cargas de trabajo.

## Base de Datos de Azure para PostgreSQL

![Captura de pantalla de un logotipo de Azure Database for PostgreSQL.][image5] Si prefiere PostgreSQL, puede elegir Azure Database for PostgreSQL para ejecutar una implementación PaaS de PostgreSQL en la nube de Azure. Este servicio proporciona las mismas ventajas de disponibilidad, rendimiento, escalado, seguridad y administración que MySQL.

Algunas características de las bases de datos locales de PostgreSQL no están disponibles en Azure Database for PostgreSQL. Estas características están relacionadas principalmente con las extensiones que los usuarios pueden agregar a una base de datos para realizar tareas especializadas, como escribir procedimientos almacenados en varios lenguajes de programación (distintos de pgsql, el cual está disponible) e interactuar directamente con el sistema operativo. Se admite un conjunto básico de las extensiones que se usan con más frecuencia, y la lista de extensiones disponibles se revisa continuamente.

### Servidor flexible de base de datos de Azure para PostgreSQL

La opción de implementación de servidor flexible para PostgreSQL es un servicio de base de datos totalmente administrado. Proporciona un elevado nivel de control y personalizaciones de configuración de servidor, así como controles de optimización de costos.

### Ventajas de Azure Database for PostgreSQL

Azure Database for PostgreSQL es un servicio de alta disponibilidad. Integra mecanismos de detección de fallos y conmutación por error.

Los usuarios de PostgreSQL están familiarizados con la herramienta pgAdmin, que puede usar para administrar y supervisar una base de datos de PostgreSQL. Puede seguir usando esta herramienta para conectarse a Azure Database for PostgreSQL, Aun así, algunas funcionalidades centradas en el servidor, como la realización de copias de seguridad y la restauración del servidor, no están disponibles porque Microsoft se encarga de administrar y mantener el servidor.

Azure Database for PostgreSQL registra información de las consultas que se ejecutan en las bases de datos del servidor y las guarda en una base de datos llamada *azure\_sys*. Puede consultar la vista *query\_store.qs\_view* para ver esta información y usarla para supervisar las consultas que ejecutan los usuarios. Esta información puede resultar muy valiosa si necesita ajustar las consultas que realizan las aplicaciones.

# Evaluación del módulo

200 XP

* 10 Minutos

Esta valoración evalúa su comprensión del módulo. A diferencia de lo anterior, no recibirá comentarios sobre respuestas individuales, solo si son correctos o incorrectos. Esto está pensado para medir lo que ha aprendido. Dedique tiempo a revisar los materiales del módulo antes de empezar.  
Contenido generado por IA Las preguntas y las opciones de respuesta de esta evaluación del módulo se generaron mediante la inteligencia artificial y se revisaron mediante un autor humano.  
1\. Su organización planea migrar una aplicación que se basa en gran medida en trabajos del Agente SQL Server y servidores vinculados. ¿Qué servicio Azure SQL debe seleccionarse para asegurarse de que se admiten estas características?   
Instancia Gestionada de Azure SQLSQL Server en Azure Virtual MachinesAzure SQL Database  
2\. Una empresa planea migrar su base de datos MySQL a Azure para mejorar la escalabilidad y las copias de seguridad automatizadas. ¿Qué servicio de Azure deben elegir?   
Azure SQL DatabaseBase de Datos Azure para MySQLInstancia Gestionada de Azure SQL  
3\. Una organización busca una solución de base de datos de código abierto totalmente administrada con alta disponibilidad y seguridad de nivel empresarial para sus aplicaciones web. ¿Qué servicio de Azure deben tener en cuenta?   
Azure SQL DatabaseBase de Datos Azure para MySQLSQL Server en Azure Virtual Machines  
4\. Una empresa requiere una solución de base de datos que permita la integración con Microsoft Entra ID para la autenticación y proporciona alta disponibilidad. ¿Qué servicio Azure SQL se ajusta a estos requisitos?   
SQL Server en Azure Virtual MachinesAzure SQL DatabaseInstancia Gestionada de Azure SQL  
5\. Una empresa quiere implementar rápidamente una nueva aplicación basada en la nube con tareas administrativas mínimas. La aplicación requiere un servicio de base de datos escalable con alta disponibilidad. ¿Qué servicio Azure SQL debe implementar?   
Azure SQL DatabaseInstancia Gestionada de Azure SQLSQL Server en Azure Virtual Machines  
6\. Una empresa debe migrar su base de datos a la nube con cambios mínimos en sus aplicaciones existentes y requiere características como servidores vinculados y Service Broker. ¿Qué servicio debe elegir?   
Instancia Gestionada de Azure SQLAzure SQL DatabaseSQL Server en Azure Virtual Machines  
7\. Su organización está considerando usar PostgreSQL debido a su compatibilidad con tipos de datos personalizados y propiedades no relacionales. ¿Qué servicio de Azure se debe usar?   
Base de Datos de Azure para PostgreSQLInstancia Gestionada de Azure SQLAzure SQL Database  
8\. ¿Qué servicio Azure SQL sería más adecuado para una empresa que busca migrar sus bases de datos de SQL Server locales existentes a la nube con cambios mínimos de código y compatibilidad total?   
Azure SQL DatabaseSQL Server en Azure Virtual MachinesInstancia Gestionada de Azure SQL  
9\. Una empresa tecnológica necesita una solución de base de datos escalable para su nueva aplicación en la nube que minimiza los costos y los esfuerzos administrativos. Esperan cargas variables y requieren escalado rápido. ¿Qué servicio Azure SQL es más adecuado?   
Azure SQL Database con configuración sin servidorInstancia Gestionada de Azure SQLSQL Server en Azure Virtual Machines

# Resumen

# Azure admite una variedad de servicios de base de datos que puede usar para admitir nuevas aplicaciones en la nube o migrar aplicaciones existentes a la nube.

En este módulo, ha aprendido a:

* Identificación de las opciones de los servicios de Azure SQL  
* Identificación de opciones para bases de datos de código abierto en Azure  
* Aprovisionamiento de un servicio de base de datos en Azure

## Pasos siguientes

Ahora que ha aprendido sobre los servicios de base de datos relacionales de Azure, considere la posibilidad de obtener más información sobre las cargas de trabajo relacionadas con los datos en Azure mediante la realización de una certificación de Microsoft en [Aspectos básicos de datos de Azure](https://learn.microsoft.com/es-es/certifications/azure-data-fundamentals/).

[image1]: <data:image/png;base64,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>

[image2]: <data:image/png;base64,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>

[image3]: <data:image/png;base64,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>

[image4]: <data:image/png;base64,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>

[image5]: <data:image/png;base64,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>