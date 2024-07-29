# oci
<aside>
💡 Mis notas de uso personal.

</aside>

# Políticas de respaldo

## Política Bronce

La política Silver incluye copias de seguridad incrementales semanales que se ejecutan los domingos. Estas copias de seguridad se conservan durante cuatro semanas. Esta política también incluye copias de seguridad incrementales mensuales, ejecutadas el primer día del mes y retenidas durante doce meses. También incluye una copia de seguridad incremental, que se ejecuta anualmente durante la primera parte de enero. Esta copia de seguridad se conserva durante cinco años

### Política Bronce

La política Bronce incluye copias de seguridad incrementales mensuales, que se ejecutan el primer día del mes.→ doce meses.

copia de seguridad incremental, anualmente durante la primera parte de enero. → cinco años.

### Política Plata

La política Plata incluye:

 copias de seguridad incrementales semanales que se ejecutan el domingo → cuatro semanas.

 copias de seguridad incrementales mensuales, que se ejecutan el primer día del mes → doce meses. 

 copia de seguridad incremental, que se ejecuta anualmente durante la primera parte de enero → cinco años.

### Política Oro

 copias de seguridad incrementales diarias → siete días,

incrementales semanales, que se ejecutan el domingo →  cuatro semanas. 

 incrementales mensuales, que se ejecutan el primer día del mes → doce meses.

incremental anual durante la primera parte de enero → durante cinco años.

[Copias de seguridad basadas en políticas](https://docs.oracle.com/es-ww/iaas/Content/Block/Tasks/schedulingvolumebackups.htm)

### crear un clon

Solo puede crear un clon en el mismo dominio de disponibilidad que su sistema de archivos principal.
Se copian las propiedades del sistema de archivos, como el compartimento, las etiquetas, el nombre para mostrar, las claves y la información de exportación del destino de montaje pero los metadatos no se copian del sistema principal.
 Una instantánea proporciona el modelo inicial para un clon. Puedes clonar un sistema de archivos principal o puedes clonar un clon, siempre que haya al menos una instantánea disponible. Las propiedades del sistema de archivos, como el compartimento, las etiquetas, el nombre para mostrar, las claves y la información de exportación del destino de montaje, no se copian del sistema principal. Estas propiedades deben especificarse manualmente. Solo puede crear un clon en el mismo dominio de disponibilidad que su sistema de archivos principal.

### Rendimiento de volumen en bloque

Se recomienda un costo más bajo para cargas de trabajo de alto rendimiento con grandes E/S secuenciales, como transmisión, procesamiento de registros y almacenes de datos.

- **Rendimiento ultraalto**: 30 y 120 VPU por GB/mes se recomienda en el caso de cargas de trabajo con los mayores requisitos de E/S que necesitan el mejor rendimiento posible Con esta opción [Rendimiento ultraalto](https://docs.oracle.com/es-ww/iaas/Content/Block/Concepts/blockvolumeultrahighperformance.htm#Higher_Performance).
- **Alto rendimiento**: 20 VPU por GB/mes recomendado para cargas de trabajo con altos requisitos de E/S que no requieren el rendimiento del nivel **Ultra alto rendimiento**.  [Alto rendimiento](https://docs.oracle.com/es-ww/iaas/Content/Block/Concepts/blockvolumehigherperformance.htm#Higher_Performance).
- **Equilibrado**: 10 VPU por GB/mes. nivel de rendimiento por defecto para volúmenes de inicio y en bloque nuevos y existentes,  [Rendimiento equilibrado](https://docs.oracle.com/es-ww/iaas/Content/Block/Concepts/blockvolumebalancedperformance.htm#Balanced_Performance).
- **Costo bajo**: opción recomendada para las cargas de trabajo que requieren un alto nivel de rendimiento y con grandes trabajos de E/S secuenciales, como flujo, procesamiento de logs y almacenes de datos. El costo es solo el costo de almacenamiento, no existe un costo de VPU adicional.  solo está disponible para volúmenes en bloque, **no está disponible para volúmenes de inici**o  [Costo bajo](https://docs.oracle.com/es-ww/iaas/Content/Block/Concepts/blockvolumelowercost.htm#Lower_Cost).

## Auth Tokens

[Los tokens de autenticación en Oracle Cloud Infrastructure (OCI) se utilizan para autenticar y autorizar a los usuarios y sistemas que interactúan con los recursos de OCI1](https://docs.oracle.com/es-ww/iaas/Content/Functions/Tasks/functionsgenerateauthtokens.htm)[2](https://docs.oracle.com/es-ww/iaas/Content/APIGateway/Tasks/apigatewayusingjwttokens.htm). Aquí te explico cómo se utilizan:

1. [**Generación de un token de autenticación**: Antes de utilizar OCI Functions, la cuenta de usuario que utilizará para crear y desplegar funciones debe tener un token de autenticación de Oracle Cloud Infrastructure1](https://docs.oracle.com/es-ww/iaas/Content/Functions/Tasks/functionsgenerateauthtokens.htm). [Este token se utiliza como contraseña al conectar Docker a Oracle Cloud Infrastructure Registry1](https://docs.oracle.com/es-ww/iaas/Content/Functions/Tasks/functionsgenerateauthtokens.htm). [Para generar un token de autenticación, debes conectarte a la consola como desarrollador de funciones, abrir el menú Perfil en la esquina superior derecha de la Consola, hacer clic en Configuración de usuario para ver los detalles, y en la página Tokens de autenticación, hacer clic en Generar token1](https://docs.oracle.com/es-ww/iaas/Content/Functions/Tasks/functionsgenerateauthtokens.htm).
2. [**Uso del token para la autenticación**: Una vez generado el token, debes copiarlo inmediatamente en una ubicación segura desde donde puedas recuperarlo más tarde, ya que no verás el token de autenticación de nuevo en la consola1](https://docs.oracle.com/es-ww/iaas/Content/Functions/Tasks/functionsgenerateauthtokens.htm). [Este token se utiliza para autenticar a los clientes de API con Oracle SaaS Cloud3](https://www.ateam-oracle.com/post/a-quick-note-on-using-jwt-token-authentication-with-oracle-saas-api).
3. [**Validación del token para la autorización**: Puedes agregar la funcionalidad de autenticación y autorización a un gateway de API haciendo que el gateway de API valide los tokens incluidos en una solicitud2](https://docs.oracle.com/es-ww/iaas/Content/APIGateway/Tasks/apigatewayusingjwttokens.htm). [Para que el gateway de API valide el token incluido en una solicitud, debes crear una política de solicitud de autenticación de tipo TOKEN_AUTHENTICATION2](https://docs.oracle.com/es-ww/iaas/Content/APIGateway/Tasks/apigatewayusingjwttokens.htm).

### To authenticate third-party APIs:

 Every user can generate up to two auth tokens. 

 Auth tokens do not expire. Each user can have up to two auth tokens at a time.

### Notifications

The Notifications service enables you to set up communication channels for publishing messages using topics and subscriptions. When a message is published to a topic, the Notifications service sends the message to all of the topic's subscriptions.

### security lists

The default security list does not include a rule to allow ping requests.

The default security list allows TCP traffic on destination port 22 (SSH) from authorized source IP addresses and any source port.

 Each subnet can have multiple security lists associated with it. The default security list has a stateful ingress rule: Allow TCP traffic on destination port 22 (SSH) from authorized source IP addresses and any source port. You configure your security lists at the subnet level, which means that all VNICs in a given subnet are subject to the same set of security lists.

## Las unidades son plantillas que determinan los recursos asignados a una instancia:

- Flexibles (solo MV)
    - personalizables
        - 1-64 OCPU AMD (1024GB ram max) ****¿ram x OCPU???****
            - VM.Standard.E3.Flex **ADMITIDA PARA AMPLIABLE**
            - VM.Standard.E4.Flex **ADMITIDA PARA AMPLIABLE**
        - 1-32 OPCU Intel (512GB max)
            - VM.Standard3.Flex **ADMITIDA PARA AMPLIABLE**
            - VM.Optimized3.Flex
        - 1-80 OCPU Ampere (512GB max) el blog dicec hasta 64gb x cpu
            - VM.Standard.A1.Flex

Fijas No personalizables

- Hard dedicado o MV

## Unidades de GPU

Para cargas de trabajo impulsadas mediante hardware : grafico, videos, IA, HPC, redes de clusters de alto rendimiento:

- NVIDIA
    - A100
    - A10
    - V100
    - P100

***MAQUINAS VIRTUALES***

- VM.GPU2 X7
    - GPU NVIDIA TESLA P100 16B
    - CPU Intel Xeon PLatinum 8167 2.0Ghz - 2.4Ghz
- VM.GPU3 X7
    - GPU NVIDIA TESLA V100 16GB
    - CPU Intel Xeon Platinum 8167 2.0Ghz - 2.4Ghz
- VM.GPU.A10 X9
    - GPU NVIDIA A10 24GB
    - CPU Intel Xeon Platinum 8358 2.6Ghz. - 3.4Ghz.

**Hardware Dedicado**

- BM.GPU2 X7
    - GPU NVIDIA TESLA P100 16B
    - CPU Intel Xeon PLatinum 8167 2.0Ghz - 2.4Ghz
- BM.GPU3 X7
    - GPU NVIDIA TESLA V100 16GB
    - CPU Intel Xeon Platinum 8167 2.0Ghz - 2.4Ghz
- BM.GPU4 E3
    - GPU NVIDIA A100 40GB
    - CPU AMD EPYC 7542 2.9Ghz - 3.4Ghz
- BM.GPU.A100
    - NVIDIA A100 80GB
    - AMD EPYC 7J13 2.55Ghz - 3.7Ghz
- BM.GPU.A10 X9
    - GPU NVIDIA A10 24GB
    - CPU Intel Xeon Platinum 8358 2.6Ghz. - 3.4Ghz.

https://gitmind.com/app/docs/mlhfcwq8

**Host de MV Dedicado (DVH)**

- No se factura para instancias de VM individuales ubicadas en el Host. (Algunas OCPU reservadas se facturan.)
- Inquilino unico
- Requisitos basados en Nodo
- Para requisitos de conformidad y aislamiento

**Unidades de Host de MV Dedicado (DVH)**

- DVH.Standard2.52 - Serie VM.Standard2
- DVH.Standard3.64 - Serie VM.Standard3
- DVH.Standard.E2.64 - Serie VM.Standard.E2
- DVH.Standard.E3.128 - Serie VM.Standard.E3
- DVH.Standard.E4.128 - Serie VM.Standard.E4
- DVH.DenselO2.52 - Serie VM.DenselO2
- DVH.Optimized3.36 - Serie VM.Optimized3
    
    ### No admite:
    
    - escala automatica.
    - Reserva de capacidad.
    - Configuracion de instancia.
    - Grupo de instancia.
    - Instancia ampliable.
    - Migracion con reinicio.

**Instancias Interrumpibles**

Recursos Excedentes

Corto plazo de uso

50% mas barato que bajo demanda

No se pueden cambiar post creación

No se pueden convertir en bajo demanda

No admite Hard dedicado ni pool de instancias

Interrumpible en cualquier momento

Servicio Events notifica cuando se reclama **(¿hay que configurarlo??)**

**Instancias Ampliables**

RENDIMIENTO BASE GARANTIZADO

AMPLIACION (solo cpu) MEDIANTE RAFAGA EN PICOS OCASIONALES (se carga para linea base definida - DEPENDE CAPACIDAD DISPONIBLE: SI EL USO DE CPU EN LAS ULTIMAS 24HS ESTA POR DEBAJO DE LA LINEA BASE)

LINEA BASE: **12.5% / 50% DE LA CAP TOTAL.**

ESCENARIOS:

- MICROSERVICIOS
- DESARROLLO Y PRBA
- CI/CD INTEGRACION Y ENTREGA CONTINUAS
- SITIOS WEB ESTATICOS
- SISTEMAS DE SUPERVISION

### Reservas de Capacidad Informática

- Vinculadas a un AD especifico ( no se pueden mover a otro AD)
- No aplicable a Host de VM dedicados.
- Instancias limitadas a la conf definida en la reserva
- CApacidad asignada tras la creación
    - Si no esta definible la creación fallara

**Instancias:** 🧗🏼‍♂️ VERTICAL

- No cambia: vNIC - Adjuntos de volumen - IP priv. y pub.
- La imagen debe ser compatible con la la nueva instancia
- La operacion requiere reinicio
- Afecta a:
    - OCPU
    - Memoria
    - Ancho de banda de red
    - número max de vNIC

## Pool de Instancias

- Solo se asocia 1 configuración de instancia.
- Asociar o anular los equilibradores de carga
- Ajustar el nro de instancias en funcion de la métrica o el programa

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9761aaee-332b-48f7-8404-118604a6eb44/b3e3ab73-ec99-4085-a92b-71a531dd59e1/Untitled.jpeg)

## GoldenGate

<aside>
💡 OCI GoldenGate, selecciona la opción número de OCPU entre 1 y 24 que usará la implementación. Cada OCPU asigna un 16 GB de memoria adicional. OCI GoldenGate no puede escalar más de 24 OCPU, que es el máximo número de OCPU. Por ejemplo, si selecciona 9 OCPU como recuento de OCPU base y habilita Auto Scale, el servicio escalará hasta 24 OCPU. Puede activar o desactivar automáticamente escalado en cualquier momento.

</aside>

### Tema: Servicio de monitoreo

### Recordar

### Notas

- El historial de alarmas se guarda por un máximo de 90 dias
- Cuales son los tres principales componenetes de una consulta? →
    - Métrica.
    - intervalo.
    - Estadística.

Que metodo de notificación se actualiza al modificar una alarma?

Qué componente controla la ventana de tiempo en cada metrica de consulta

Que es usado para filtrar datos agregados de cada consulta

---

### Tema: Servicio de Logs

### **RESUMEN: Los logs de serviciom tendran los detalles genericos sobre lo que esta pasando con el recurso. Los logs de auditoria solo tienen las llamadas a API de REST ejecutadas en el recurso.**

Un “Agente de Configuración” es creado para habilitar la ingestion de logs de una instancia: para lo cual hay que seleccionar un “Grupo de Host” (como un grupo dinámico) en el “Agente de Configuración”

Cuales son los tres tipos de logs utilizados por el servicio de logging:

- Logs personalizados.
- Logs de Servicio.
- Logs de Auditoría.

Para colectar logs personalizados de unaplicaciones externas Fluentd D y Servcio de conectores

---

### Tema: IAM

[Gestión de credenciales de usuario](https://docs.oracle.com/es-ww/iaas/Content/Identity/Tasks/managingcredentials.htm)

---

### Tema: **Uso de cargas de varias partes**

### Recordar

tamaño máximo de un objeto cargado es de 10 TiB. Las partes del objeto **NO** deben ser superiores a 50 GiB.

### Notas

- Max  object = 10Tb
- Max parte = 50Gb

[Uso de cargas de varias partes](https://docs.oracle.com/es-ww/iaas/Content/Object/Tasks/usingmultipartuploads.htm)

### Cargas de varias partes para objetos grandes

Los objetos se pueden cargar en depósitos usando la consola, pero hay un límite de 2 GB por objeto. La CLI, los SDK o la API se pueden utilizar para cargar objetos más grandes, de hasta 10 TB, realizando una carga de varias partes y paralelizando la carga para reducir el tiempo total de carga. Al utilizar la API, debe dividir el objeto en varias partes, cargar las partes y confirmar la carga, lo que permite que el servicio de almacenamiento de objetos reconstruya el objeto grande a partir de sus partes constituyentes. Al utilizar la CLI, no es necesario dividir el objeto en partes manualmente, ya que la utilidad realiza automáticamente la división, la carga y la confirmación. Puede elegir el tamaño de los componentes y el número máximo de piezas que se cargarán en paralelo (el valor predeterminado es tres). El siguiente comando CLI le permite iniciar la carga multiparte. Un ejemplo resuelto muestra un archivo de 10 GB dividido en partes de 2 GB y cargado mediante cinco subprocesos paralelos.

---

### Tema: ESCALA AUTOMATICA

### Recordar

Puede agregar un máximo de 50 políticas de escala automática basada en el programa a una configuración de escala automática.

Cada pool de instancias solo puede tener una configuración de escala automática.

Al utilizar la escala automática basada en el programa para parar o reiniciar instancias, se conserva la información sobre las instancias. Cuando las instancias se inician después de un cierre, se devuelven al estado en el que se encontraban antes de que se produjera el cierre.

Tener:

- Un pool de instancias.
- Supervision activada.
- Supervision recibe métricas.
- Limite de servicio.

[Creación de una regla de Events](https://docs.oracle.com/es-ww/iaas/Content/Events/Task/create-events-rule.htm)

[Cron Trigger Tutorial](https://www.quartz-scheduler.org/documentation/quartz-2.3.0/tutorials/crontrigger.html)

[Free Online Cron Expression Generator and Describer - FreeFormatter.com](https://www.freeformatter.com/cron-expression-generator-quartz.html#cronconverttotext)

- 

[Escala automática](https://docs.oracle.com/es-ww/iaas/Content/Compute/Tasks/autoscalinginstancepools.htm)

<aside>
📌 **RESUMEN:**

### Gestión de varios programas

Si existen varias políticas de escala automática basadas en el programa, los programas pueden entrar en conflicto. Si se produce un conflicto, Oracle elige una política de estado del ciclo de vida y una política de escala automática para ejecutarse. → La política de estado del ciclo de vida se ejecuta primero.

Para la política de **estado del ciclo de vida**, se elige la política con *la acción de mayor prioridad*. Las acciones se priorizan de la siguiente manera, enumeradas de la prioridad más alta a la más baja:

- Forzar reinicio
- Reiniciar
- Iniciar
- Forzar parada
- Detener

Para la **política de escala automátic**a, se selecciona ***la política con el recuento de instancias más alto***.

**Estas métricas de rendimiento se agregan a períodos de tiempo de *un minuto* y, a continuación, se realiza *la media* entre todas las instancias del pool de instancias. *Cuando tres valores consecutivos (es decir, la media de métricas durante tres minutos consecutivos) alcanzan el umbral, se desencadena un evento de escala automática.***

</aside>

[cron (Unix)](https://es.wikipedia.org/wiki/Cron_(Unix))

---

### Tema: Acceso a Oracle Services: **gateway de servicio**

[Acceso a Oracle Services: gateway de servicio](https://docs.oracle.com/es-ww/iaas/Content/Network/Tasks/servicegateway.htm)

### Recordar

<aside>
📌 **RESUMEN:**

## Aspectos destacados

- Un gateway de servicios permite a la red virtual en la nube (VCN) acceder de forma privada a servicios de Oracle concretos sin exponer los datos a la red pública de internet. No se requiere ningún gateway de internet ni gateway de NAT para acceder a esos servicios específicos. Los recursos de la VCN pueden estar en una subred privada y utilizar solo direcciones IP privadas. El tráfico desde la VCN al servicio Oracle recorre el tejido de red de Oracle y no internet.
- El gateway de servicio es regional y permite el acceso solo a los servicios de Oracle **admitidos *en la misma región* que la VCN.**
- Solo se necesita un gateway de servicio para cada VCN. Todas las subredes de una VCN tienen acceso al gateway de servicio si las reglas de seguridad y las reglas de tabla de rutas permiten ese acceso.
- El gateway de servicio permite acceder a los servicios de Oracle admitidos dentro de la región para proteger a sus datos de internet. Puede que las cargas de trabajo necesiten acceder a los puntos finales públicos o a servicios que no admite el gateway de servicios (por ejemplo, para descargar actualizaciones o parches). Asegúrese de tener un [gateway de NAT](https://docs.oracle.com/es-ww/iaas/Content/Network/Tasks/NATgateway.htm#NAT_Gateway) u otro acceso a internet si es necesario.
- Los servicios de Oracle admitidos son Oracle Cloud Infrastructure Object Storage y otros incluidos en Oracle Services Network. Para obtener una lista, consulte [Gateway de servicio: servicios en la nube admitidos en Oracle Services Network](https://www.oracle.com/cloud/networking/service-gateway/service-gateway-supported-services/).
- El gateway de servicio utiliza el concepto de *etiqueta CIDR de servicio*, que es una cadena que representa todos los rangos de direcciones IP públicas regionales para el servicio o el grupo de servicios de interés (por ejemplo, *OCI PHX Object Storage* es la cadena para Object Storage en el Oeste de EE. UU. (Phoenix)). Puede usar esa etiqueta CIDR de servicio al configurar el gateway de servicio y las reglas de ruta relacionadas para controlar el tráfico al servicio. También puede utilizarlo al configurar [reglas de seguridad](https://docs.oracle.com/es-ww/iaas/Content/Network/Concepts/securityrules.htm#Security_Rules). Si las direcciones IP públicas del servicio cambian en el futuro, no tiene que ajustar esas reglas.
- Puede configurar la VCN para que su red local tenga *acceso privado* a los servicios de Oracle mediante la VCN y el gateway de servicios de la VCN. Los hosts de la red local se comunican con sus direcciones IP privadas y el tráfico no pasa por internet. Para obtener más información, consulte [Acceso privado a los servicios de Oracle](https://docs.oracle.com/es-ww/iaas/Content/Network/Tasks/transitroutingoracleservices.htm#Transit_Routing_Private_Access_to_Oracle_Services).
</aside>

---

## https://docs.oracle.com/es-ww/iaas/Content/Block/Concepts/blockvolumebackups.htm#ariaid-title13

### Tema: COPIA DE SEGURIDAD DE VOLUMEN EN BLOQUE

### Recordar

La función de copias de seguridad del servicio Oracle Cloud Infrastructure Block Volume permite realizar una instantánea puntual de los datos en un volumen en bloque.  A continuación, estas copias de seguridad se pueden restaurar a volúmenes nuevos inmediatamente después de una copia de seguridad o más tarde si así lo elige.

 Esta función proporciona una copia de reserva de un volumen y permite completar correctamente la recuperación ante desastres en la misma región.

Hay dos formas de iniciar una copia de seguridad, ya sea manualmente o mediante la asignación de una política que defina un programa de copia de seguridad definido.

### Notas

- Puede realizar una copia de seguridad de un volumen al asociarlo a una instancia o mientras está desasociado.
- Las copias de seguridad se cifran y almacenan en [Oracle Cloud Infrastructure Object Storage](https://docs.oracle.com/es-ww/iaas/Content/Object/Concepts/objectstorageoverview.htm#Overview_of_Object_Storage), y se pueden restaurar como volúmenes nuevos en cualquier dominio de disponibilidad dentro de la **misma región** en la que se almacenan.

<aside>
📌 **RESUMEN:**

## Diferencias entre clonaciones y copias de seguridad de volumen en bloque

Tenga en cuenta los siguientes criterios cuando decida si desea crear una copia de seguridad o una clonación de un volumen.

|  | Copia de seguridad de volumen | Clonación de volumen |
| --- | --- | --- |
| Descripción | Crea una copia de seguridad de un momento dado de los datos en un volumen. Puede restaurar varios volúmenes nuevos a partir de la copia de seguridad en el futuro. | Crea una sola copia de un momento dado de un volumen sin tener que pasar por el proceso de copia de seguridad y restauración. |
| Caso de uso | Mantenga una copia de seguridad de los datos en un volumen para poder duplicar un entorno más tarde o conservar los datos para su uso posterior.
Cumpla los requisitos normativos y de conformidad, ya que los datos de una copia de seguridad no se modifican con el tiempo.
Soporte los requisitos de continuidad de negocio.
Reduzca el riesgo de interrupciones o la modificación de datos a lo largo del tiempo. | Duplique rápidamente un entorno existente. Por ejemplo, puede utilizar una clonación para probar los cambios de configuración sin que esto afecte al entorno de producción. |
| Velocidad | Más lento (minutos u horas) | Más rápido (segundos) |
| Costo | Costo bajo | Costo superior |
| Ubicación de almacenamiento | Almacenamiento de objetos | Volumen en bloque |
| Política de retención | Las copias de seguridad basadas en políticas caducan, las copias de seguridad manuales no caducan | Sin caducidad |
| Grupos de volúmenes | Soportado. Puede realizar una copia de seguridad de un grupo de volúmenes. | Soportado. Puede clonar un grupo de volúmenes. |
</aside>

# Retention rules

Retention rules are configured at the bucket level and are applied to all individual objects in the bucket.

---

### Tema: File Storage

### Recordar

Sistema de archivos: almacenamiento donde existen los archivos

Exportar NFS: Capa de control

Dest. de montaje: pto final utilizado por los cli para conectarse al FSS

Ruta de exportaci{on: identificacion unica el sistema de archivos dentro del destino de montaje.

opciones de exportacion: conj. de parametros del niveld e acceso otorgado a los clientes

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9761aaee-332b-48f7-8404-118604a6eb44/853184ea-6a35-4ae9-98cb-85e7c2698532/Untitled.jpeg)

### Notas

- SOLO SE ADMITE EL CIFRADO AES
- agregar politica: Allow service blockstorage, objectstorage-<region_name>, <file_storage_service_user>, oke, streaming to use keys in compartment ABC where [target.key.id](http://target.key.id/) = '<key_OCID>'
    - (https://docs.oracle.com/en-us/iaas/Content/Identity/policiescommon/commonpolicies.htm#)

<aside>
💡 La instantanea del FSS no consume mas espacio HASTA que se cambia el contenido del sistema de archivos, eso crea un diferencial con los datos agregados → instantanea + datos agregados al FSS original = nueva metrica → 1+0.5 = 1.5

</aside>

<aside>
💡 Para medir el CLON1 del dir2 del FSS se mide datos+metadatos + metadatos del clon → 1.5+0.5=2gb  si agrego un archivo file1 de 1gb al clon queda → 2gb + 1gb = 3gb, **si borro dir2** queda (dir1+metadir1)+clon → 1gb+3gb=4gb.

</aside>

<aside>
💡 LE costo de ancho de banda para la replicacion de FSS en la misma region entre AD es 0 (tampoco se cobra datos entrantes), entre regiones SI se cobra:

- Las instantáneas creadas por el usuario para el Sistema de archivos B son idénticas al Sistema de archivos A y se miden solo con respecto a los datos diferenciados.
- Las instantáneas creadas por la replicación se miden únicamente con respecto a los datos diferenciados y se suprimen una vez que se ha completado un ciclo de replicación.

**Nota**Hasta que se complete un ciclo de replicación, el uso de datos y metadatos para el Sistema de archivos B puede ser diferente para el Sistema de archivos A.

</aside>

<aside>
📌 **RESUMEN:Hasta 10 mil instantaneas por FSS Cifrado estatico y en transito**

</aside>

Un sistema de archivos distribuido es una solución para almacenar y acceder a datos basada en una arquitectura cliente/servidor. Los datos se almacenan en un dispositivo de almacenamiento central, pero se accede a ellos y se procesan como si estuvieran almacenados en una máquina cliente local. Con un sistema de archivos distribuido, los usuarios en la misma red comparten fácilmente información en los archivos de manera controlada y autorizada

Un sistema de archivos distribuido va a permitir almacenar y acceder a archivos remotos como si fueran locales, esto sin notar pérdidas en el rendimiento. Este sistema es útil cuando es necesario que los usuarios tengan acceso a información compartida en diferentes ubicaciones de forma ininterrumpida.https://es.wikipedia.org/wiki/Sistema_de_archivos_distribuido

---

### Tema: Instancias - Imagenes personalizadas

### Recordar: El max tamaño para una imagen personalizada es de 400Gb

Los cambios realizados en las unidades locales de la instancia se pierden al finalizar la sesión

### Notas

- W admite imagenes personalizadas y especializadas
- LA importacino/exportacin utiliza el servicio object storage, admite emulacion-aparavirtualizado/nativo.
- La exportacin entre regiones se hace 1° exportando aun cubo en mi region y 2° luego a otro en la de detino.
- BYOI se reaiz generando una imagen .qcow2 → subiendola a object storage  → creando na imagen personalizada y tomandola en la sintancia. ¿como la tomo??

<aside>
📌 **RESUMEN:**

</aside>

**Las imágenes cuyo nombre incluye "aarch64", como Oracle-Linux-8.*x*-aarch64-*edición* son de unidades que utilizan procesadores basados en Arm. Las imágenes sin "aarch64" en el nombre se utilizan para unidades que utilizan procesadores x86.Las imágenes cuyo nombre incluye "GPU", como Oracle-Linux-8.*x*-Gen2-GPU-*edición* son de unidades GPU. Algunas imágenes, como Windows Server, tienen una única compilación de imagen que soporta tanto unidades GPU y como no GPU.**

---

### Tema: ¿Qué almacenamiento usaría si su carga de trabajo de big data requiere acceso compartido y una interfaz basada en NFS?

### Recordar

Utilice el servicio File Storage cuando la aplicación o la carga de trabajo incluyan big data y análisis, procesamiento de medios o gestión de contenido.

### Notas

- semántica de acceso del sistema de archivos compatible con la interfaz del sistema operativo portátil (POSIX)
- el almacenamiento accesible de manera simultánea.

<aside>
📌 **RESUMEN:**

- **Almacenamiento de archivos de uso general:** acceda a un pool ilimitado de sistemas de archivos para gestionar el crecimiento de los datos estructurados y no estructurados.
- **Big data y análisis:** ejecute cargas de trabajo analíticas y utilice sistemas de archivos compartidos para almacenar los datos persistentes.
- **Migración a la nube de aplicaciones empresariales:** migre aplicaciones de Oracle existentes que requieren almacenamiento NFS, como Oracle E-Business Suite y PeopleSoft.
- **Bases de datos y aplicaciones transaccionales:** ejecute cargas de trabajo de prueba y desarrollo con Oracle, MySQL u otras bases de datos.
- **Copias de seguridad, continuidad del negocio y recuperación ante desastres:** aloje una copia secundaria de los sistemas de archivos relevantes de la ubicación local en la nube para fines de copia de seguridad y recuperación ante desastres.
- **Microservicios y Docker:** ofrezca persistencia con estado para contenedores. Amplíe fácilmente a medida que crecen sus entornos basados en contenedores.
</aside>

---

### Tema: preferencias de clonación: Rendimiento de un Volumen en bloque

### Recordar

### Notas

- Al activar el ajuste automático basado en el rendimiento, el rendimiento del volumen se ajustará automáticamente entre VPU especificada por defecto y VPU/GB máximo inclusive. Al activar, el valor de VPU/GB por defecto no se puede definir en 0 ni 120 y el valor de VPU/GB máximo debe ser al menos 10 VPU/GB mayor que el valor de VPU/GB por defecto. Al desactivarlo, el rendimiento del volumen volverá al valor de VPU/GB por defecto
- ...

<aside>
📌 **RESUMEN:**

</aside>

---

### Tema: permisos para que una instancia se comunique con otro servicios de OCI

### Recordar:

 Cree un grupo dinámico con reglas coincidentes para incluir su instancia y escriba una política para este grupo dinámico

### Notas

- Los grupos dinámicos le permiten agrupar instancias informáticas de Oracle Cloud Infrastructure como actores "principales" (similares a los grupos de usuarios).

<aside>
📌 **RESUMEN:**

Cuando crea un grupo dinámico, en lugar de agregar miembros explícitamente al grupo, define un **conjunto de reglas coincidentes** para definir los miembros del grupo. Por ejemplo, una regla podría especificar que todas las instancias que se inicien y finalicen en ese compartimento.

Un grupo dinámico **no tiene permisos hasta que escriba al menos una política que le otorgue permiso** a ese grupo dinámico para el arrendamiento o un compartimento. Al escribir la política, puede especificar el grupo dinámico utilizando el **nombre exclusivo o el OCID del grupo dinámico**. Según la nota anterior, incluso si especifica el nombre del grupo dinámico en la política, IAM utiliza internamente el OCID para determinar el grupo dinámico.

</aside>

### 

**Una instancia que se ejecuta en un compartimento de desarrollo necesita realizar llamadas API a otros servicios OCI. esto se puede lograr esto sin configurar las credenciales de usuario o configurar un archivo de configuración:**
Cree un grupo dinámico con reglas coincidentes para incluir su instancia y escriba una política para este grupo dinámico.
 *En la definición del grupo dinámico, usted proporciona las reglas de coincidencia para especificar qué instancias desea permitir que realicen llamadas API a los servicios. Después de haber creado un grupo dinámico, debe crear políticas para permitir que los grupos dinámicos accedan a los servicios de Oracle Cloud Infrastructure.*

---

### Tema: Acceso de los clientes NFS al sistema de Archivo (FSS)

### Recordar

Ubique el objetivo de montaje en una subred que tenga un CIDR
rango mayor que /30 ya que cada objetivo de montaje requiere tres IP privadas
direcciones. Los clientes NFS se conectan al destino de montaje. Para evitar posibles
conflictos de IP, es una buena práctica colocar objetivos de montaje y subredes en
subredes dedicadas.
El objetivo debe permitir la entrada de tráfico TCP y UDP en los puertos 111, 2048, 2049 y 2050. y el ingreso con estado desde cualquier dirección IP de origen (0.0.0.0/0).

What is the recommended approach to create this backup using FSS features?

1. Implement a backup policy to execute a snapshot of the shared volume.

### Notas

- Las opciones de exportación pueden especificar la IP de origen permitida.
direcciones y puertos, ya sea que el acceso sea de lectura/escritura o
solo lectura y cómo los usuarios y grupos acceden al estilo Unix. Una entrada de opciones de exportación NFS dentro de una exportación define el acceso a una única dirección IP o rango de bloques CIDR.
- .

the export paths /exp1 and /exp1/p1 are
overlapping and are not allowed to be exported to the
same mount target.

<aside>
📌 **RESUMEN:**

The FSS is a regional service available to
instances in all ADs in a region. 

FSS provides NFSv3–compatible file systems
supporting full POSIX semantics similar to NFS file
systems that have been available on traditional
networks for decades.

FSS provides network-based file systems in a region.
These file systems are physically located on storage
servers in an AD and are replicated to other ADs or fault
domains providing high durability.

Un sistema de archivos es el recurso principal para almacenar archivos en FSS. Un sistema de archivos es específico de AD y se accede a través de múltiples rutas de exportación. Cada ruta de exportación es asociado con un conjunto de opciones de exportación que determinan
qué instancias o clientes NFS tienen acceso al camino de exportación. Las opciones de exportación pueden especificar la IP de origen permitida direcciones y puertos, ya sea que el acceso sea de lectura/escritura o
solo lectura y cómo los usuarios y grupos acceden al estilo Unix.
Los derechos se reducen o aplastan para la red montada.
sistema de archivos.

Cuatro capas de seguridad para limitar el acceso a NFS:
• **Servicio IAM.** la creación instancias (clientes NFS), VCN y subredes; actualizar listas de seguridad; y creando montaje OCI destinos y objetos del sistema de archivos.
• **Lista de seguridad.** Utiliza rangos CIDR para limitar
qué instancias pueden conectarse al destino de montaje.
• **Opciones de exportación**. Esto utiliza direcciones IP, CIDR. rangos de bloques, permisos de acceso y calabaza raíz  Opciones para controlar el acceso en un sistema por archivo base.
• **Seguridad NFSv3 Unix** Esto controla qué Unix
Los usuarios pueden montar sistemas de archivos y actualizarlos o verlos.
archivos en el sistema de archivos FSS.

</aside>

---

### Tema: **Clonación de un volumen de bloque**

### Recordar

El servicio Block Volume **no admite** el cifrado de volúmenes con claves cifradas mediante el algoritmo Rivest-Shamir-Adleman (RSA). Cuando usted use sus propias claves, debe usar claves cifradas con el cifrado avanzado Algoritmo estándar (AES). Esta restricción se aplica a los volúmenes de bloque y los volúmenes de arranque.

### Notas

- Debido a que el clon es una copia del volumen de origen, tiene el mismo tamaño como volumen de origen, a menos que especifique un tamaño de volumen mayor al crear el clon.
- If the source volume is attached when you create a clone, you need to wait for the first clone operation to complete from the source volume before creating additional clones. If the source volume is detached, you can create up to ten clones from the same source volume simultaneously.
- Puede crear un clon para un volumen solo dentro de la misma región, dominio de disponibilidad y arrendamiento. Puede Clonar un volumen entre compartimentos si tiene los permisos de acceso necesarios para la operación.

## REDES VIRTUALES EN LA NUBE (VCN)

[Solución de problemas de conectividad y las VCN](https://docs.oracle.com/es-ww/iaas/Content/Network/Concepts/troubleshooting.htm)

Las VCN se dividen en subredes, **algunas de las cuales son privadas** y están aisladas entre sí. Los servicios de red OCI ofrecen servicios DHCP que asignan direcciones IP de los rangos de subred a instancias. OCI ofrece dos tipos de IP públicas, una temporal conocida como IP pública efímera y una IP estática conocida como IP reservada. Las IP privadas están disponibles en OCI de forma predeterminada en todas las tarjetas de interfaz de red virtual o vNIC.

The OCI network is referred to as a full software-defined layer 3 network.  

Una red virtual en la nube (VCN) es funcionalmente equivalente a una red local y es una red privada que se ejecuta en equipos de red de Oracle en varios centros de datos. Una VCN es un recurso regional que abarca todos los AD en una sola región y reside en un compartimento. Se pueden crear varias VCN en un compartimento determinado.

Se permite que el prefijo de red del bloque CIDR de VCN oscile entre /16 (más de 65 000 direcciones) y /30 (cuatro direcciones de host, pero tres están reservadas, por lo que solo se puede utilizar una). Oracle recomienda utilizar uno de los rangos de direcciones IP privadas especificados en IETF RFC1918, sección 3, donde la Autoridad de Números Asignados de Internet (IANA) ha reservado tres bloques de IP para Internet privadas según la Tabla 3-1.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9761aaee-332b-48f7-8404-118604a6eb44/e0fd2860-8b8b-4cba-a90a-b5a8d4e04d8e/Untitled.png)

Cuando se crea una VCN, se crean tres recursos de red obligatorios. Obtendrá una tabla de rutas predeterminada, una lista de seguridad y un conjunto de opciones de DHCP creadas. Las siguientes subsecciones ofrecen resúmenes de estos recursos. https://docs.oracle.com/en-us/iaas/Content/Network/Tasks/managingVNICs.htm#ariaid-title2
Tablas de ruta
Las tablas de rutas contienen reglas que determinan cómo se enruta el tráfico de red que entra o sale de las subredes de su VCN a través de puertas de enlace OCI o instancias informáticas especialmente configuradas. La tabla de rutas predeterminada creada al crear una VCN no tiene reglas de enrutamiento. Puede agregar reglas a la tabla de rutas predeterminada vacía o agregar sus propias tablas de rutas nuevas.
Listas de seguridad

[Reglas de seguridad](https://docs.oracle.com/es-ww/iaas/Content/Network/Concepts/securityrules.htm#stateful)

Las listas de seguridad contienen reglas de firewall para todas las instancias informáticas que utilizan la subred. Las reglas de entrada y salida especifican si ciertos tipos de tráfico están permitidos dentro y fuera de la VCN, respectivamente. El tipo de tráfico se basa en el protocolo y el puerto y una regla puede ser con o sin estado. Las reglas con estado permiten el seguimiento de la conexión y son las predeterminadas, pero se recomiendan sin estado si tiene grandes volúmenes de tráfico. **Las reglas de estado con seguimiento de conexión** permiten que el tráfico de respuesta abandone su red sin la necesidad de definir explícitamente una regla de salida para que coincida con una regla de entrada. Sin embargo, las reglas sin estado no permiten que el tráfico de respuesta abandone su red a menos que se defina una regla de salida. Una de las reglas de ingreso en la lista de seguridad predeterminada permite el tráfico desde cualquier lugar a instancias usando la subred en el puerto TCP 22. Esto admite el tráfico SSH entrante y es útil para conectarse a instancias informáticas de Linux.

[Virtual Network Interface Cards (VNICs)](https://docs.oracle.com/en-us/iaas/Content/Network/Tasks/managingVNICs.htm#ariaid-title2)

Opciones de DHCP
Los servicios DHCP proporcionan información de configuración para calcular la instancia en el momento del arranque. Puede influir sólo en un subconjunto de las ofertas de servicios DHCP configurando Opciones de DHCP. Estos operan a nivel de subred, pero en ausencia de múltiples opciones DHCP a nivel de subred, el conjunto predeterminado se aplica a todas las instancias informáticas creadas en la VCN.

SubRed https://docs.oracle.com/en-us/iaas/Content/Network/Concepts/overview.htm#network_landing

Una subred es una parte de su red o VCN que comprende un bloque CIDR contiguo que es un subconjunto del bloque CIDR de VCN. Cuando se crea una VCN más recursos relacionados a través de la consola en una región con tres AD, también se crean automáticamente tres subredes, una por AD con los bloques CIDR predeterminados no superpuestos de 10.0.0.0/24, 10.0.1.0/24 y 10.0.2.0/24. Estos bloques especifican un rango de 256 direcciones por subred. Esto deja más de 64 000 direcciones del bloque CIDR de VCN que pueden asignarse a nuevas subredes en su VCN. Los bloques CIDR asignados a subredes no deben superponerse entre sí. Las subredes regionales también están disponibles y abarcan todos los AD de una región. 

muestra una nueva subred que se creará en Lab VCN en el compartimento Lab, en el AD US-ASHBURN-AD-1 con el bloque CIDR 10.0.5.0/28. Esto es aceptable porque se trata de un subconjunto del bloque CIDR 10.0.0.0/16 asignado a la VCN. Si el formato del bloque CIDR no es válido, se realiza alguna verificación de validación y se le informa si hay problemas. Si se supera la verificación de validación de CIDR, verá el rango de IP enumerado debajo del bloque CIDR que ingresó, similar a este: Direcciones IP especificadas: 10.0.5.0–10.0.5.15 (16 direcciones IP).

Todos los VNIC en una subred determinada usan la misma tabla de ruta, listas de seguridad y opciones DHCP

Cuando crea una subred, por defecto se considera pública, lo que significa instancias en que las subred pueden tener direcciones IPv4 públicas y la comunicación por Internet es permitido con puntos finales IPv6.

Las direcciones IP públicas están prohibidas para instancias que utilizan subredes privadas, mientras que las subredes públicas permiten instancias con direcciones IP públicas. Utilice subredes públicas si necesita que los recursos que utilizan la subred sean accesibles desde Internet; de lo contrario, utilice subredes privadas.

Servidores físicos → NIC físicas → direcciones IP. → hipervisor OCI crea y administra NIC virtuales (vNIC), → residentes en una subred →  instancia informática recibe una vNIC principal de la subred en la que se crea la instancia informática y a esa vNIC se le asigna una dirección IP privada que está asociada con la instancia hasta que finalice la instancia. Se pueden agregar vNIC secundarias a la instancia informática y se pueden asociar direcciones IP públicas y privadas con estas vNIC.

Tras el lanzamiento de una instancia informática, se asigna una vNIC privada e inamovible a la instancia y se le asigna una dirección IP privada (que se analiza a continuación). Las vNIC secundarias se pueden asignar y eliminar de una instancia existente en cualquier momento. Una vNIC **secundaria** puede residir en cualquier subred de la VCN siempre que esté en el mismo AD que la vNIC primaria. Cada vNIC tiene un OCID, reside en una subred e incluye lo siguiente:
• Una dirección IP privada **principal** de la subred de la vNIC, asignada automáticamente por los servicios de red OCI o especificada por usted al crear la instancia.
• Un máximo de 31 direcciones IPv4 privadas **secundarias** opcionales de la subred de la vNIC, elegidas automáticamente o por usted. Para cada una de estas vNIC privadas secundarias opcionales, puede optar por que los servicios de red OCI creen y asignen una dirección IPv4 pública → 31 IPv4 publicas : **1 vNIC con 62 direcciones secundarias**
• Un nombre de host DNS ***opcional*** para cada dirección IP privada (que se analiza más adelante en este capítulo).
• Una dirección de control de acceso a medios (MAC), que es un identificador de dispositivo único asignado a una NIC.
• Una etiqueta VLAN utilizada opcionalmente por instancias bare metal.
• Un indicador para habilitar o verificar el origen y el destino enumerados en el encabezado de cada paquete de red que atraviesa la vNIC, descartando aquellos que no se ajusten a la dirección de origen o destino aceptada.

• Hasta 32 direcciones IPv6 opcionales. El direccionamiento IPv6 es compatible con todos regiones comerciales y gubernamentales. Para más información, ver [Direcciones IPv6](https://docs.oracle.com/en-us/iaas/Content/Network/Concepts/ipv6.htm#IPv6_Addresses).

¿COMO CREAR UNA vNIC SECUNDARIA?

Opcionalmente, se puede agregar una IP privada secundaria después de que se haya lanzado una instancia y debe provenir del bloque CIDR de la subred de la vNIC privada respectiva. Se puede mover una IP privada secundaria desde su vNIC en una instancia informática a una vNIC en otra instancia, siempre que ambas vNIC pertenezcan a la misma subred. Cualquier IP pública asignada a la IP privada secundaria se mueve con ella.

El proceso de creación de una VNIC secundaria la asocia automáticamente a la instancia. El proceso de desconectar una VNIC secundaria la elimina automáticamente.

TIP: Se deben cumplir varios requisitos previos antes de poder acceder a una instancia desde Internet. La subred en la que se crea debe ser una subred pública, con tablas de rutas y listas de seguridad configuradas adecuadamente, ubicada en una VCN con una puerta de enlace de Internet.

¿COMO SE CONFIGURA ADECUADAMENTE LA LISTA DE SEGURIDAD PARA ACCEDER DESDE INTERNET?

TIPO: A una vNIC en una subred pública se le asigna automáticamente una IP pública. No es obligatorio y puede eliminarse o desasignarse.

Puerta de enlace NAT
Una puerta de enlace de traducción de direcciones de red (NAT) permite que las instancias sin direcciones IP públicas accedan a Internet y al mismo tiempo protege la instancia del tráfico entrante de Internet. Cuando una instancia realiza una solicitud de un recurso de red fuera de la VCN, la puerta de enlace NAT realiza la solicitud en nombre de la instancia a Internet y reenvía la respuesta a la instancia.

NOTA Aún se puede acceder a las instancias sin direcciones IP públicas directamente desde otras instancias internas o hosts bastión que tengan ***una ruta a la dirección IP privada de la instancia.***

Cuando se crea una puerta de enlace en un compartimento específico, se le asigna una dirección IP pública. Esta es la dirección IP que los recursos de Internet ven como la dirección de la solicitud entrante. ???????

CONSEJO DEL EXAMEN El protocolo Border Gateway (BGP) es compatible con FastConnect, pero no con IPSec VPN que conecta redes externas a su VCN.

Cuando se crea un objeto DRG, se le asigna un OCID. Los DRG se pueden conectar o desconectar de una VCN. Una VCN solo puede tener un DRG asociado a la vez. Un DRG se puede conectar solo a una VCN a la vez, pero se puede desconectar de una VCN y conectar a otra. También se puede utilizar un DRG para proporcionar una ruta privada que no atraviese Internet entre VCN en diferentes regiones. Una vez que un DRG está conectado a una VCN, las tablas de rutas para la VCN o subredes específicas deben actualizarse para permitir que el tráfico fluya hacia el DRG.

https://docs.oracle.com/en-us/iaas/Content/Network/Tasks/managingpublicIPs.htm#Public_IP_Addresses#ariaid-title2

**Ciertos tipos de recursos en su arrendamiento están diseñados para ser accesibles directamente desde Internet y, por lo tanto, vienen automáticamente con una dirección IP pública. Por ejemplo: una puerta de enlace NAT o un equilibrador de carga público**. A otros tipos de recursos solo se puede acceder directamente si los configura para que así sea. Por ejemplo: instancias en su VCN.

En realidad, la asignación es a un objeto de IP privada en la instancia. La VNIC a la que está asignada la IP privada debe estar en una subred pública. Una instancia determinada puede tener varias VNIC secundarias y una VNIC determinada puede tener varias IP privadas secundarias. Por lo tanto, puede asignar a una instancia determinada varias IP públicas en una o más VNIC si lo desea.

Para que una instancia se comunique directamente con Internet, se requiere todo lo siguiente:

- La instancia debe estar en una subred pública.
- La instancia debe tener una dirección IP pública.
- La VCN de la instancia debe tener una puerta de enlace a Internet.
- La subred pública debe tener tablas de rutas y listas de seguridad configuradas en consecuencia.

Consejo

El emparejamiento público de Oracle Cloud Infrastructure FastConnect permite que su red local acceda a las direcciones IP públicas de los recursos en Oracle Cloud Infrastructure sin que el tráfico atraviese Internet.

Hay dos tipos de IP públicas:

Efímero: considérelo temporal y existente durante toda la vida de la instancia.
Reservado: considérelo persistente y existente más allá de la vida útil de la instancia a la que está asignado. Puedes desasignarlo y luego reasignarlo a otra instancia cuando lo desees. Excepción: IP públicas reservadas en balanceadores de carga públicos.

| Característica | IP públicas efímeras | IP públicas reservadas |
| --- | --- | --- |
| Asignación permitida | A la https://docs.oracle.com/en-us/iaas/Content/Network/Tasks/managingIPaddresses.htm#Private_IP_Addresses
Límites:
• Uno por https://docs.oracle.com/en-us/iaas/Content/Network/Tasks/managingVNICs.htm#Virtual_Network_Interface_Cards_VNICs
• Dos por instancia de máquina virtual y 16 por instancia bare metal | A una https://docs.oracle.com/en-us/iaas/Content/Network/Tasks/managingIPaddresses.htm#overview principal o secundaria
Límite: 32 por https://docs.oracle.com/en-us/iaas/Content/Network/Tasks/managingVNICs.htm#Virtual_Network_Interface_Cards_VNICs |
| Creación | Opcionalmente creado y asignado durante el lanzamiento de la instancia o creación de VNIC secundaria. Puede crear y asignar uno más adelante si el VNIC aún no tiene uno. | Usted crea uno en cualquier momento. A continuación, puede asignarlo cuando gustar.
Límite: puedes crear 50 por región |
| Desasignación | Puede anular su asignación en cualquier momento, lo que lo elimina. Podrías hacerlo esto si quien lanzó la instancia incluía una IP pública, pero No desea que la instancia tenga uno.
Cuando detiene una instancia, sus IP públicas efímeras permanecen asignado a la instancia. | Puede anular la asignación en cualquier momento, lo que lo devuelve a su grupo de IP públicas reservadas de arrendamiento. |
| Pasar a un recurso diferente | No se puede mover una IP pública efímera a una privada diferente IP. | Si se asigna a una IP privada secundaria: Si mueve la IP privada a una VNIC diferente (debe estar en la misma subred), el IP pública va con él.
Puede moverlo (anular la asignación y luego reasignarlo) en cualquier momento a otra IP privada en la misma región. Puede estar en una VCN diferente o dominio de disponibilidad. |
| Eliminación automática | Su vida útil está ligada a la vida útil de la IP privada. Automáticamente sin asignar y eliminado cuando:
• Se elimina su IP privada
• Su VNIC se separa o termina
• Su instancia termina | Nunca. Existe hasta que lo elimine. |
| Alcance | Dominio de disponibilidad | Regional (se puede asignar a una IP privada en cualquier dominio de disponibilidad de la región) |
| Compartimento y dominio de disponibilidad | Igual que las IP privadas | Puede ser diferente de las IP privada |

A DRG is a VCN-level device that extends your on-premises network into your VCN. It is important to think of a DRG as a gateway that provides a private path between discrete networks.

La ruta de red entre el CPE y el DRG puede ser un conjunto de túneles VPN IPSec redundantes o a través de FastConnect. Las VPN IPSec ofrecen comunicaciones cifradas de extremo a extremo, mejorando así la seguridad. Los túneles todavía circulan por redes públicas, lo que los hace más asequibles pero menos seguros que usar FastConnect. Cuando se configura una VPN IPSec, se crean dos túneles para lograr redundancia.
OCI proporciona FastConnect como un medio para crear una conexión privada dedicada de alta velocidad entre redes locales y OCI. FastConnect proporciona un rendimiento consistente, predecible, seguro y confiable. FastConnect admite los siguientes usos:
• El peering privado extiende su red local a una VCN y puede usarse para crear una nube híbrida. Se pueden realizar conexiones locales a las direcciones IP privadas de las instancias como si vinieran de instancias en la VCN, como en la conexión entre la Instancia1 AD1 y la Instancia1 AD3 descrita anteriormente. El emparejamiento privado también puede ocurrir entre instancias en VCN en otras regiones.

El emparejamiento público le permite conectarse desde recursos fuera de la VCN, como la red local, a servicios públicos de OCI, como el almacenamiento de objetos, sin atravesar Internet a través de 

### FastConnect.

FastConnect se actualiza utilizando varios modelos de conectividad:
• La colocación con Oracle permite conexiones cruzadas físicas directas entre su red y los dispositivos de borde FastConnect de Oracle.
• Utilizando un proveedor de red de Oracle o un socio de Exchange, puede configurar una conexión FastConnect desde su red a la red del proveedor o socio que tiene una conexión de gran ancho de banda en los dispositivos de borde FastConnect de Oracle.
• Usar un proveedor externo que no es un socio de FastConnect pero que generalmente es un proveedor de VPN MPLS que configura un circuito privado o dedicado entre su red local y los dispositivos perimetrales FastConnect de Oracle.

CONSEJO DEL EXAMEN El protocolo Border Gateway (BGP) es compatible con FastConnect, pero no con IPSec VPN que conecta redes externas a su VCN.

 DRG puerta de enlace de enrutador directo

- Una VCN solo puede tener un DRG asociado a la vez
- Los DRG se pueden conectar o desconectar de una VCN. .  .
- Un DRG se puede conectar solo a una VCN a la vez, pero se puede desconectar de una VCN y conectar a otra.
- También se puede utilizar un DRG para proporcionar una ruta privada que no atraviese Internet entre VCN en diferentes regiones
- Una vez que un DRG está conectado a una VCN, las tablas de rutas para la VCN o subredes específicas deben actualizarse para permitir que el tráfico fluya hacia el DRG.
- Cuando se crea un objeto DRG, se le asigna un OCID.
- 

NOTA Se puede usar una VPN IPSec para conectarse a su red IP OCI-Classic, o puede abrir una solicitud de servicio (SR) con Oracle para proporcionar una conexión entre la puerta de enlace privada de su red IP OCI-C y el DRG conectado a su VCN. La compatibilidad con la conexión de OCI-C a OCI tiene varias limitaciones, incluido el uso únicamente de direcciones IP privadas y bloques CIDR que no se superpongan, y el hecho de que esta conexión no está disponible en todas las regiones. También se puede utilizar una VPN IPSec para conectarse a otro proveedor de nube utilizando una VM Libreswan como CPE.

### puerta de enlace de servicio

Regla de tabla de rutas a 
3. Es posible que deba actualizar la lista de seguridad en su VCN para permitir el tráfico asociado con el servicio elegido. Por ejemplo, el servicio de almacenamiento de objetos requiere una regla de salida con estado para permitir el tráfico HTTPS.
4. Los tres pasos anteriores permitirán el acceso a todos los recursos en la VCN para acceder al almacenamiento de objetos. Es prudente utilizar políticas de IAM (que se analizan en el Capítulo 2) para limitar el acceso a depósitos de almacenamiento de objetos específicos. La siguiente regla permite a los miembros del grupo ESC_DBAs administrar el depósito de almacenamiento de objetos denominado DB_Backups.

PRECAUCIÓN La lista de seguridad predeterminada creada cuando se crea una VCN contiene una regla de salida con estado que permite el tráfico TCP para todos los puertos con tipo de destino CIDR. Al configurar una puerta de enlace de servicio para el almacenamiento de objetos, s**e requiere una regla de estado adicional con el servicio de tipo de destino**.

Un buen caso de uso para la puerta de enlace de servicios se relaciona con la lectura y escritura de copias de seguridad de bases de datos en el almacenamiento de objetos desde redes privadas. Una base de datos normalmente reside en una instancia informática en una subred privada. Puede realizar una copia de seguridad de la base de datos en un depósito de almacenamiento de objetos sin necesidad de direcciones IP públicas ni acceso a Internet mediante el uso de una puerta de enlace de servicio.

Puerta de enlace de intercambio de tráfico local (LPG)
Puede crear varias VCN con rangos de CIDR que no se superpongan en una región. Usando los bloques de IP reservados en la Tabla 3-1, puede tener vcn1R1 con CIDR 10.0.0.0/8 y vcn2R1 con CIDR 192.168.0.0/16, por ejemplo. Cada VCN tiene cero o más subredes públicas o privadas por AD con cero o más instancias informáticas con direcciones IP privadas y posiblemente algunas con IP públicas. Una instancia en una VCN puede conectarse a otra instancia en la misma VCN utilizando una IP pública o privada, pero solo puede conectarse a la IP pública de instancias en diferentes VCN (siempre que exista una puerta de enlace de Internet, entradas relevantes en la tabla de rutas y seguridad). listas están en su lugar).
Una puerta de enlace de intercambio de tráfico local (LPG) conecta VCN en la misma región incluso entre arrendamientospermite que las VCN de la misma región, independientemente del arrendamiento, actúen como pares y admite que las instancias de una VCN se conecten a instancias de otra VCN mediante direcciones IP privadas. Esto se conoce como **emparejamiento de VCN local** y requiere lo siguiente:
• Dos VCN en la **misma región** con rangos CIDR que no se superponen
• Una puerta de enlace de intercambio de tráfico local conectada en cada VCN
• Reglas de la tabla de rutas que permiten el flujo de tráfico a través de LPG entre subredes específicas en cada VCN
• La listas de seguridad enumera las reglas de entrada y salida que controlan el tráfico entre instancias de cada VCN.

## CONEXIÓN D E INTERCAMBIO DE TRAFICO REMOTO (DRG)

[Puertas de enlace de enrutamiento dinámico (DRG) (oracle.com)](https://docs.oracle.com/en-us/iaas/Content/Network/Tasks/managingDRGs.htm#Dynamic_Routing_Gateways_DRGs)
Mientras que el emparejamiento local conecta VCN en la misma región incluso entre arrendamientos, el emparejamiento remoto conecta VCN en el mismo arrendamiento entre regiones. El emparejamiento remoto permite que las instancias en VCN separadas regionalmente se comuniquen utilizando sus direcciones IP privadas. 

¿QUÉ RANGOS CIDR SON IDEALES? : VCN1 (10.0.0.0/16) and VCN2 (172.16.0.0/16)

- Se debe conectar un DRG a cada VCN remota que se vaya a emparejar.
- Reglas de la tabla de rutas que permiten el flujo de tráfico a través de los DRG entre subredes específicas en cada VCN.
- Listas de seguridad con reglas de entrada y salida para controlar el tráfico entre instancias de cada VCN
- Se crea una conexión de intercambio de tráfico remoto (RPC) en el DRG en ambas VCN separadas regionalmente.
- A una VCN se le asigna la función de solicitante, mientras que la otra es la de aceptador.
- El solicitante inicia la solicitud de intercambio de tráfico y especifica el OCID del RPC que pertenece al aceptador.
- Puede tener un máximo de diez RPC por arrendamiento

### LOAD BALANCER

<aside>
💡 CONSEJO PARA EL EXAMEN Un balanceador de carga privado requiere tres direcciones IP de
la subred asociada para:

- El balanceador de carga en espera
- El balanceador de carga principal
- para la IP privada flotante.
</aside>

[Visión general de Load Balancer](https://docs.oracle.com/es-ww/iaas/Content/Balance/Concepts/balanceoverview.htm)

 
Un equilibrador de carga acepta una red TCP o HTTP entrante
tráfico en una única dirección IP de la subred de host que solo es visible dentro de su VCN  y lo distribuye a un conjunto de backend que comprende uno o más procesos
instancias. En este contexto, las instancias informáticas son
conocidos como servidores backend. **Cada uno de estas  instancias residen en una subred pública o privada**

[Monitor OCI Load Balancer backend operations for DevOps](https://docs.oracle.com/en/learn/oci-load-balancer/index.html#introduction)

Con una subred regional, el servicio Load Balancer crea un equilibrador de carga principal y un equilibrador de carga en espera, cada uno en un dominio de disponibilidad (AD) diferente, para garantizar la accesibilidad incluso durante una interrupción del dominio de disponibilidad. 

Si crea **un equilibrador de carga en dos subredes específicas para el mismo dominio de disponibilidad(AD)**, una subred alojará el equilibrador de carga principal y la otra un equilibrador de carga en espera. Si el equilibrador de carga principal falla, la dirección IP pública cambia al equilibrador de carga secundario. El servicio trata los dos equilibradores de carga como equivalentes y no se puede especificar cuál es el "principal".

Si utiliza **subredes regionales** o específicas para el dominio de disponibilidad, cada equilibrador de carga requiere una dirección IP privada de su subred de host. El servicio Load Balancer proporciona una dirección IP pública flotante al equilibrador de carga principal. La dirección IP pública flotante no procede de las subredes backend.

### Balanceadores de carga públicos y privados

**EQUILIBRADOR DE CARGA PRIVADO**

Se crea un equilibrador de carga privado pasivo (en espera)
automáticamente para fines de conmutación por error y también recibe un
dirección IP privada flotante  es local para la subred del host.

el servicio solo necesita una subred para alojar los equilibradores de carga principal y en espera.

Los equilibradores de carga principal y en espera requieren cada uno una dirección IP privada adicional de la subred del host.

El equilibrador de carga puede ser regional o específico para el dominio de disponibilidad, según el ámbito de la subred del host
La dirección IP privada sirve como una dirección de alta disponibilidad de
el equilibrador de carga. La carga privada activa y pasiva
Los equilibradores están altamente disponibles dentro de un solo AD. Si el
El equilibrador de carga principal falla, el oyente dirige el tráfico a
Se mantiene el equilibrador de carga en espera y la disponibilidad.

Si las reglas de la lista de seguridad lo permiten, se puede utilizar un ***equilibrador de carga privado.***
accesible desde instancias dentro de la VCN *donde reside la subred del equilibrador de carga*

Si se produce una interrupción del dominio de disponibilidad, un equilibrador de carga privado creado en una subred regional dentro de una región de varios dominios de disponibilidad proporciona capacidad de failover. Un equilibrador de carga privado creado en una subred específica para el dominio de disponibilidad o en una subred regional dentro de una región de dominio de disponibilidad individual no tiene capacidad de conmutación por error en respuesta a una interrupción del dominio de disponibilidad.

<aside>
💡 Para aislar el equilibrador de carga de Internet y simplificar la postura de seguridad, se puede crear un equilibrador de carga privado.

</aside>

**Load Balancer Publico**

Se permite el tráfico entrante desde la Internet pública
puertos y protocolos se dirige a la IP pública flotante
dirección asociada con el equilibrador de carga activo. Si el
El equilibrador de carga en la subred S1 falla, el dispositivo pasivo en
La subred S3 se activa automáticamente.

<aside>
💡

- No puede especificar una subred privada para el equilibrador de carga público.
- Para garantizar la accesibilidad entre el equilibrador de carga público y sus backends basados en direcciones IP públicas, configure un gateway de NAT. Consulte [Gateway de NAT](https://docs.oracle.com/iaas/Content/Network/Tasks/NATgateway.htm) para obtener más información.
- La dirección IP pública flotante no procede de las subredes backend.
</aside>

<aside>
💡 El equilibrador de carga **público es un recurso regional** a diferencia de un equilibrador de carga privado, que es un recurso a nivel AD. En regiones con múltiples AD, es ***obligatorio*** para especificar subredes públicas en diferentes AD para balanceadores de carga activos y pasivos.

</aside>

**BACKENDS**

Si los servidores de backend tienen direcciones IP públicas, configure un gateway de NAT agregando reglas de ruta para conectar el equilibrador de carga público a sus servidores de backend basados en direcciones IP públicas.

Puede configurar servidores de backend como pools de instancias informáticas

### oyente (LISTENER)

Al momento de escribir este artículo, se pueden crear hasta 16 oyentes.

Puede configurar varios **listeners**  para una dirección IP para equilibrar la carga del tráfico de la capa 4 y la capa 7 (TCP y HTTP). Tanto el equilibrador de carga público como el privado pueden actuar como proxies inversos y direccionar el tráfico de datos a cualquier servidor de backend al que se pueda acceder desde la VCN.

Cada oyente en un balanceador de carga define un conjunto de propiedades que incluyen una combinación única de
protocolo (HTTP o TCP) y número de puerto. Tráfico web (HTTP) también se conoce como capa de aplicación o capa 7
(del modelo OSI) Mientras que el tráfico TCP como capa de transporte o tráfico de capa 4.
Como mínimo, un oyente requiere un protocolo y un puerto. Su balanceador de carga puede manejar el tráfico SSL entrante si marca la casilla Usar SSL y proporciona  INformación relevante del certificado. El tráfico SSL puede ser manejado con los siguientes tres mecanismos:
• Terminación SSL: El tráfico SSL finaliza en el equilibrador de carga. Tráfico entre la carga balanceador y el conjunto de backend no está cifrado.
• Túnel SSL: disponible para balanceadores carga TCP , el tráfico SSL se pasa al conjunto de fondo.
• SSL de extremo a extremo El tráfico SSL entrante es terminado en el balanceador de carga y un nuevo SSL
Se crea la conexión con el conjunto backend.

También puede especificar una duración de tiempo de inactividad que desconectará una conexión si el tiempo entre dos operaciones sucesivas de E/S de red de envío o recepción se superado durante la fase de solicitud-respuesta HTTP.
Una vez que se aprovisiona un balanceador de carga a través del consola, se pueden definir oyentes adicionales, así como estas propiedades adicionales que reducen el número de 
Se requieren equilibradores de carga y oyentes:
• Nombre de host o nombre de host virtual que usted define
esta propiedad y asignarla a un HTTP o HTTPS
(SSL habilitado) oyente. Al momento de escribir este artículo, hasta 16
Se pueden asignar nombres de host virtuales a un oyente.y a menudo corresponden a nombres de aplicaciones.
Los nombres de host también pueden estar respaldados por DNS que
resolver en la dirección IP del equilibrador de carga.
• Reglas de ruta de ruta utilizadas para enrutar el tráfico HTTP
a diferentes conjuntos de backend en función de la coincidencia de
Patrón de URL en una solicitud entrante. Por ejemplo,
Las solicitudes con el patrón /login pueden enrutarse a
el backend de gestión de identidad establecido mientras
Las solicitudes con el patrón /apex pueden enrutarse a
el conjunto de servidores de aplicaciones.
• Conjuntos de reglas definidos en el nivel del balanceador de carga y
puede ser utilizado por múltiples oyentes de la carga
balancín. Los conjuntos de reglas agregan, modifican o eliminan mensajes entrantes.
Encabezados de solicitud HTTP. Ejemplos de cómo se establecen las reglas
mejorar la seguridad incluye eliminar los encabezados de depuración
de solicitudes y prevención de dominios externos
de incrustar su sitio en un iframe. backend
Los servidores también pueden ser notificados de la terminación SSL por
agregar información específica de la aplicación a un
encabezado de solicitud en el oyente del balanceador de carga.
Conjunto de backend
Un equilibrador de carga es un dispositivo de red que, en última instancia,
enruta el tráfico a uno o más servidores accesibles
instancias informáticas (llamadas servidores backend) que residen
en cualquier subred de la VCN. Un conjunto de backend es lógico
agrupación de servidores backend y distribución del tráfico
política. La Figura 3-15 muestra un conjunto de backend con dos
instancias informáticas (servidor web1 y servidor web2) y
sus compartimentos, direcciones IP, puertos de escucha locales
(que puede ser diferente del oyente del balanceador de carga
puerto) y un peso. Es una buena práctica difundir el backend
establecer instancias en múltiples AD para admitir alta
disponibilidad

[Let users launch compute instances](https://docs.oracle.com/en-us/iaas/Content/Identity/policiescommon/commonpolicies.htm#)

**Type of access:** Ability to do everything with instances launched into the cloud network and subnets in compartment XYZ, and attach/detach any existing volumes that already exist in compartment ABC. The first statement also lets the group create and manage instance images in compartment ABC. If the group doesn't need to attach or detach volumes, you can delete the `volume-family` statement.

**Where to create the policy:** The easiest approach is to put this policy in the tenancy. If you want the admins of the individual compartments (ABC and XYZ) to have control over the individual policy statements for their compartments, see [Policy Attachment](https://docs.oracle.com/en-us/iaas/Content/Identity/policieshow/how-policies-work.htm#Policy3).

Copy

```
Allow group InstanceLaunchers to manage instance-family in compartment ABC
Allow group InstanceLaunchers to read app-catalog-listing in tenancy
Allow group InstanceLaunchers to use volume-family in compartment ABC
Allow group InstanceLaunchers to use virtual-network-family in compartment XYZ
```
