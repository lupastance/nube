# 3️⃣ Modelos de despliegue en la nube

## 3.1. Introducción

En los temas anteriores hemos estudiado qué es el Cloud Computing y los diferentes modelos de servicio que podemos encontrar: IaaS, PaaS y SaaS.

Sin embargo, todavía nos queda responder a otra pregunta importante:

**¿Dónde se encuentra la infraestructura que proporciona los servicios cloud y quién tiene acceso y control sobre ella?**

Una organización puede utilizar servidores de un proveedor externo, construir su propia infraestructura privada o combinar ambas posibilidades. La elección dependerá de factores como el presupuesto, la seguridad, la normativa, el control necesario sobre los datos y la capacidad técnica de la organización.

Para clasificar estas diferentes posibilidades se utilizan los **modelos de despliegue de la nube**.

Según la clasificación del NIST (National Institute of Standards and Technology), existen cuatro modelos principales:

- Nube pública (*Public Cloud*).
- Nube privada (*Private Cloud*).
- Nube híbrida (*Hybrid Cloud*).
- Nube comunitaria (*Community Cloud*).

Es importante no confundir los modelos de despliegue con los modelos de servicio:

| Modelos de servicio | Modelos de despliegue |
|---|---|
| IaaS | Pública |
| PaaS | Privada |
| SaaS | Híbrida |
| | Comunitaria |

Los modelos de servicio indican **qué ofrece el proveedor y qué gestiona el cliente**. Los modelos de despliegue indican **cómo se organiza y para quién está destinada la infraestructura cloud**.

Por tanto, un servicio IaaS puede formar parte de una nube pública o privada. Lo mismo ocurre con otros servicios.

---

## 3.2. Nube pública (Public Cloud)

### ¿Qué es?

La nube pública es un modelo en el que la infraestructura informática pertenece a un proveedor externo que ofrece sus recursos y servicios a diferentes clientes a través de Internet o de conexiones de red privadas.

Algunos de los proveedores más conocidos son:

- Amazon Web Services (AWS).
- Microsoft Azure.
- Google Cloud Platform (GCP).
- Oracle Cloud Infrastructure.
- IBM Cloud.

Estos proveedores disponen de enormes centros de procesamiento de datos (CPD) repartidos por distintas regiones del mundo.

En lugar de comprar servidores físicos, una empresa puede contratar máquinas virtuales, almacenamiento, bases de datos o aplicaciones directamente al proveedor.

Por ejemplo, una pequeña empresa que necesita alojar una página web puede contratar una máquina virtual en AWS sin tener que comprar un servidor, instalarlo en sus oficinas ni mantener físicamente sus componentes.

<figure>
<img src="https://lupastance.github.io/nube/assets/3-public-cloud.png" alt="Representación de una nube pública" />
</figure>

### ¿Cómo funciona?

En una nube pública, el proveedor es responsable de construir, mantener y administrar los centros de datos donde se encuentran los recursos informáticos.

Los clientes contratan los recursos que necesitan y acceden a ellos mediante Internet, redes privadas o herramientas de administración proporcionadas por el proveedor.

Una característica importante es que la infraestructura física puede ser compartida por múltiples clientes. Sin embargo, esto no significa que los clientes puedan acceder libremente a los datos o recursos de los demás.

Los proveedores utilizan mecanismos de aislamiento, control de acceso y virtualización para separar los entornos de cada organización.

Por ejemplo, dos empresas pueden tener máquinas virtuales alojadas en el mismo servidor físico sin tener acceso a los sistemas ni a los datos de la otra.

### Características principales

**1. Infraestructura gestionada por un proveedor**

El proveedor se encarga de mantener los edificios, servidores físicos, sistemas de alimentación eléctrica, refrigeración y redes que forman parte de sus centros de datos.

**2. Recursos compartidos**

La infraestructura física puede ser utilizada por numerosos clientes, aunque sus recursos y datos se mantienen aislados mediante mecanismos tecnológicos y de seguridad.

**3. Escalabilidad**

Es posible aumentar o reducir los recursos contratados según las necesidades de cada momento. Por ejemplo, una tienda online puede ampliar temporalmente su capacidad durante una campaña comercial.

**4. Pago por uso**

Muchos servicios permiten pagar en función del consumo, aunque también existen suscripciones, reservas de recursos y tarifas fijas.

**5. Acceso desde diferentes ubicaciones**

Los servicios pueden utilizarse desde distintos lugares y dispositivos siempre que exista conectividad y se disponga de los permisos correspondientes.

### Ventajas

- **Menor inversión inicial:** no es necesario comprar servidores ni construir un centro de datos propio.
- **Escalabilidad:** permite adaptar los recursos a las necesidades del negocio.
- **Disponibilidad:** los grandes proveedores cuentan con infraestructuras diseñadas para ofrecer servicios de forma continuada.
- **Mantenimiento físico externalizado:** el cliente no necesita reparar ni sustituir los servidores del proveedor.
- **Gran variedad de servicios:** se pueden contratar bases de datos, redes, almacenamiento, inteligencia artificial, máquinas virtuales y muchos otros recursos.

### Desventajas

- **Dependencia del proveedor:** una organización puede depender de las herramientas y tecnologías de una empresa externa.
- **Costes variables:** un consumo elevado o una configuración incorrecta puede generar facturas inesperadas.
- **Menor control físico:** el cliente no decide directamente dónde se encuentran los servidores ni puede acceder físicamente a ellos.
- **Dependencia de la conectividad:** muchos servicios necesitan una conexión de red para funcionar correctamente.
- **Consideraciones legales:** es necesario conocer dónde se almacenan y procesan los datos y qué obligaciones legales se aplican.

### Ejemplos de uso

- Una startup que necesita desplegar rápidamente una aplicación.
- Una tienda online que experimenta grandes variaciones de tráfico.
- Una empresa que necesita almacenar copias de seguridad fuera de sus instalaciones.
- Una plataforma de streaming que debe atender a millones de usuarios.

---

## 3.3. Nube privada (Private Cloud)

### ¿Qué es?

La nube privada es un modelo de despliegue en el que la infraestructura cloud está destinada exclusivamente a una organización.

A diferencia de la nube pública, donde el proveedor ofrece sus recursos a diferentes clientes, en una nube privada los recursos están reservados para una única organización.

Esta infraestructura puede estar ubicada:

- En las propias instalaciones de la organización.
- En un centro de datos externo.
- En las instalaciones de un proveedor especializado que aloja la infraestructura de forma exclusiva para el cliente.

Por tanto, una nube privada no tiene por qué encontrarse físicamente dentro de la empresa.

<figure>
<img src="https://lupastance.github.io/nube/assets/3-private-cloud.png" alt="Representación de una nube privada" />
</figure>

### ¿Cómo funciona?

Una organización dispone de una infraestructura de servidores, almacenamiento y redes que utiliza para proporcionar recursos informáticos a sus propios departamentos, trabajadores o aplicaciones.

Para gestionar estos recursos puede utilizar tecnologías de virtualización y plataformas de administración cloud.

Por ejemplo, un hospital podría disponer de una infraestructura privada donde ejecutar sus aplicaciones internas y almacenar información médica.

Los diferentes departamentos podrían solicitar máquinas virtuales, almacenamiento o servicios sin tener que comprar y configurar un servidor físico para cada necesidad.

### Características principales

**1. Uso exclusivo**

La infraestructura está destinada a una única organización. Esto permite establecer políticas específicas de acceso, administración y seguridad.

**2. Mayor control**

La organización puede decidir cómo configurar los recursos, qué sistemas utilizar y qué políticas de seguridad aplicar, dentro de las posibilidades de su infraestructura.

**3. Personalización**

La infraestructura puede adaptarse a las necesidades técnicas y organizativas de la empresa.

**4. Responsabilidad sobre la infraestructura**

Dependiendo de cómo esté alojada y gestionada, la organización puede asumir una parte importante del mantenimiento, la administración y la seguridad.

**5. Capacidad limitada por los recursos disponibles**

La escalabilidad depende de la capacidad de la infraestructura instalada o contratada. Para ampliar considerablemente los recursos puede ser necesario adquirir nuevos servidores o contratar capacidad adicional.

### ¿Qué tecnologías permiten construir una nube privada?

Existen diferentes herramientas para crear y administrar infraestructuras privadas.

Algunas de las más conocidas son:

- **OpenStack:** plataforma de código abierto para construir y gestionar infraestructuras cloud.
- **VMware Cloud Foundation:** conjunto de tecnologías para construir y administrar infraestructuras privadas y entornos cloud.
- **Proxmox VE:** plataforma de virtualización que permite gestionar máquinas virtuales y contenedores.
- **Microsoft Azure Local:** solución para ejecutar servicios de infraestructura y determinados servicios de Azure en entornos propios o ubicaciones locales.

Estas herramientas permiten administrar recursos informáticos desde una plataforma centralizada.

### Ventajas

- **Mayor control:** la organización puede decidir cómo se configura y administra la infraestructura.
- **Personalización:** permite adaptar los sistemas a necesidades concretas.
- **Aislamiento:** los recursos están destinados a una única organización.
- **Control de la ubicación:** puede facilitar que los datos permanezcan en determinadas instalaciones o ubicaciones geográficas.
- **Adaptación normativa:** puede resultar útil cuando existen requisitos específicos de seguridad, privacidad o cumplimiento legal.

### Desventajas

- **Mayor inversión inicial:** puede ser necesario adquirir servidores, almacenamiento, redes y licencias.
- **Mantenimiento:** alguien debe encargarse de administrar, actualizar y mantener la infraestructura.
- **Necesidad de personal especializado:** requiere conocimientos técnicos para gestionar los sistemas.
- **Escalabilidad más limitada:** ampliar la infraestructura puede requerir tiempo y nuevas inversiones.
- **Responsabilidad sobre la seguridad:** la organización debe proteger y mantener correctamente los componentes que gestiona.

### Ejemplos de uso

- Un banco que necesita controlar determinados sistemas internos.
- Un hospital que dispone de aplicaciones e información especialmente sensible.
- Una administración pública con requisitos específicos de control sobre sus sistemas.
- Una gran empresa que necesita una infraestructura adaptada a sus aplicaciones internas.

**Importante:** utilizar servidores propios no significa automáticamente tener una nube privada. Para hablar de nube privada deben existir características propias del Cloud Computing, como la provisión de recursos bajo demanda, la agrupación de recursos y la capacidad de ofrecer servicios de forma flexible. Una sala con varios servidores tradicionales no es necesariamente una nube privada.

---

## 3.4. Nube híbrida (Hybrid Cloud)

### ¿Qué es?

La nube híbrida combina dos o más infraestructuras cloud diferentes, normalmente una nube privada y una nube pública, que permanecen como entornos independientes pero están conectados para permitir el intercambio de datos o la utilización conjunta de recursos.

Su principal objetivo es aprovechar las ventajas de ambos modelos.

Una organización puede mantener determinados sistemas en su infraestructura privada y utilizar los servicios de un proveedor público para otras necesidades.

<figure>
<img src="https://lupastance.github.io/nube/assets/3-hybrid-cloud.png" alt="Representación de una nube híbrida" />
</figure>

### ¿Cómo funciona?

Imaginemos una universidad que dispone de una infraestructura privada donde almacena expedientes académicos, información administrativa y otros datos sensibles.

Al mismo tiempo, necesita ofrecer servicios digitales a miles de estudiantes.

En lugar de alojar absolutamente todo en sus instalaciones, puede utilizar servicios de nube pública para proporcionar:

- Una plataforma de videoconferencias.
- Una página web institucional.
- Un sistema de distribución de contenidos.
- Servicios de almacenamiento temporal.
- Aplicaciones que experimentan grandes variaciones de uso.

Ambos entornos pueden comunicarse mediante conexiones de red, mecanismos de autenticación y sistemas de integración.

De esta forma, la universidad mantiene determinados sistemas bajo su control y aprovecha la capacidad de los proveedores públicos para otras necesidades.

### Características principales

**1. Combinación de infraestructuras**

Integra entornos privados y públicos, que pueden pertenecer a diferentes proveedores o utilizar tecnologías distintas.

**2. Interconexión**

Los entornos deben poder comunicarse de forma controlada. Para ello se utilizan redes privadas virtuales (VPN), conexiones dedicadas, APIs y otros mecanismos de integración.

**3. Distribución de cargas de trabajo**

Cada aplicación o servicio puede ejecutarse en el entorno que mejor se adapte a sus necesidades.

**4. Flexibilidad**

La organización puede decidir qué recursos mantiene en su infraestructura privada y cuáles utiliza desde la nube pública.

**5. Mayor complejidad**

Es necesario administrar diferentes entornos, controlar las comunicaciones y mantener políticas de seguridad coherentes.

### Ventajas

- **Flexibilidad:** permite elegir dónde ejecutar cada aplicación.
- **Control de datos sensibles:** determinados datos y sistemas pueden permanecer en entornos privados.
- **Escalabilidad:** se pueden utilizar recursos públicos cuando la capacidad privada resulta insuficiente.
- **Optimización de costes:** permite aprovechar la infraestructura propia y contratar recursos externos cuando sea necesario.
- **Continuidad del negocio:** puede facilitar estrategias de recuperación ante desastres y distribución de servicios.

### Desventajas

- **Complejidad técnica:** integrar diferentes infraestructuras puede ser complicado.
- **Seguridad:** hay que proteger las comunicaciones y controlar los accesos entre entornos.
- **Administración:** se necesitan conocimientos para gestionar diferentes plataformas.
- **Costes de integración:** pueden aparecer gastos relacionados con conexiones, licencias, herramientas y mantenimiento.
- **Dependencia de la conectividad:** determinados servicios necesitan comunicarse entre ambos entornos.

### Ejemplos de uso

**Universidad**

Mantiene los expedientes académicos en una infraestructura privada y utiliza servicios públicos para videoconferencias y alojamiento de su página web.

**Tienda online**

Mantiene sus sistemas de gestión interna en una infraestructura privada y utiliza recursos de nube pública para atender los picos de visitas durante campañas comerciales.

**Empresa sanitaria**

Almacena determinados datos y aplicaciones en una infraestructura privada y utiliza servicios públicos para tareas de análisis o procesamiento que no requieren trasladar información identificativa.

---

## 3.5. Nube comunitaria (Community Cloud)

### ¿Qué es?

La nube comunitaria es un modelo de despliegue en el que la infraestructura es compartida por varias organizaciones que tienen intereses, necesidades o requisitos comunes.

A diferencia de la nube pública, donde el servicio está disponible para clientes de diferentes sectores y características, la nube comunitaria está diseñada para atender a un grupo concreto de organizaciones.

Estas organizaciones pueden pertenecer al mismo sector, compartir obligaciones legales o necesitar servicios tecnológicos similares.

<figure>
<img src="https://lupastance.github.io/nube/assets/3-community-cloud.png" alt="Representación de una nube comunitaria" />
</figure>

### ¿Cómo funciona?

Varias organizaciones acuerdan compartir una infraestructura tecnológica para reducir costes, aprovechar recursos y establecer políticas comunes.

La infraestructura puede ser gestionada:

- Por las propias organizaciones participantes.
- Por una de las organizaciones en representación del resto.
- Por un proveedor externo especializado.

Por ejemplo, varios hospitales podrían compartir una plataforma cloud diseñada específicamente para sus necesidades, con requisitos comunes de seguridad, disponibilidad y protección de información sanitaria.

En lugar de que cada hospital construya su propia infraestructura, todos utilizan una plataforma común.

### Características principales

**1. Uso compartido por una comunidad concreta**

Los recursos están destinados a varias organizaciones que comparten determinados objetivos o necesidades.

**2. Requisitos comunes**

La infraestructura se diseña teniendo en cuenta las necesidades del grupo: seguridad, normativa, disponibilidad, interoperabilidad o administración.

**3. Costes compartidos**

Los gastos de infraestructura, mantenimiento y administración pueden distribuirse entre las organizaciones participantes.

**4. Gestión compartida o externalizada**

Las organizaciones pueden gestionar la plataforma conjuntamente o contratar a un proveedor para que se encargue de ella.

**5. Acceso restringido**

No está destinada a cualquier usuario o empresa, sino a los miembros de la comunidad autorizada.

### Ventajas

- **Reducción de costes:** varias organizaciones comparten los gastos.
- **Servicios especializados:** la infraestructura puede adaptarse a las necesidades de un sector concreto.
- **Colaboración:** facilita el intercambio de información y recursos entre organizaciones.
- **Políticas comunes:** permite establecer criterios compartidos de seguridad y administración.
- **Aprovechamiento de recursos:** evita que cada organización tenga que construir una infraestructura independiente.

### Desventajas

- **Gestión compleja:** es necesario establecer acuerdos sobre quién administra la infraestructura.
- **Reparto de costes:** pueden surgir desacuerdos sobre cuánto debe aportar cada organización.
- **Dependencia entre participantes:** los cambios o problemas de una organización pueden afectar al funcionamiento conjunto.
- **Menor flexibilidad:** las decisiones deben tener en cuenta las necesidades de todos los participantes.
- **Menor disponibilidad comercial:** es un modelo menos habitual que la nube pública.

### Ejemplos de uso

- Varios hospitales que comparten una plataforma tecnológica.
- Diferentes universidades que utilizan una infraestructura común para investigación.
- Organismos públicos que comparten servicios de almacenamiento y procesamiento.
- Varias entidades financieras que utilizan una plataforma común con requisitos de seguridad específicos.

---

## 3.6. Comparación de los modelos de despliegue

Después de estudiar los cuatro modelos, podemos resumir sus principales diferencias:

| Característica | Pública | Privada | Híbrida | Comunitaria |
|---|---|---|---|---|
| Usuarios | Diferentes clientes | Una organización | Una organización que combina entornos | Organizaciones de una comunidad |
| Infraestructura | Proveedor externo | Uso exclusivo | Combinación de entornos | Compartida por la comunidad |
| Control | Principalmente proveedor | Organización o proveedor contratado | Distribuido | Compartido o externalizado |
| Inversión inicial | Generalmente baja | Generalmente alta | Variable | Compartida |
| Escalabilidad | Alta | Depende de la infraestructura | Alta si integra recursos públicos | Depende de los recursos compartidos |
| Personalización | Según el proveedor | Alta | Variable | Adaptada a la comunidad |
| Complejidad | Generalmente menor para el cliente | Depende de la gestión | Alta | Media o alta |

No existe un modelo que sea siempre mejor que los demás.

La elección dependerá de las necesidades de cada organización.

Por ejemplo, una startup que necesita comenzar con pocos recursos puede encontrar muy interesante la nube pública. Sin embargo, una organización que necesita controlar una infraestructura muy específica puede preferir una nube privada.

Una empresa que necesita ambas cosas puede optar por una arquitectura híbrida.

### ¿Cómo elegir el modelo adecuado?

Antes de elegir un modelo de despliegue, conviene analizar diferentes factores:

**Presupuesto**

¿La organización dispone de dinero para comprar y mantener infraestructura propia o prefiere pagar por recursos externos?

**Seguridad y privacidad**

¿Se manejan datos especialmente sensibles? ¿Existen requisitos específicos sobre su almacenamiento y procesamiento?

**Escalabilidad**

¿La demanda de recursos es constante o puede variar considerablemente?

**Control**

¿Es necesario controlar directamente la configuración y administración de la infraestructura?

**Personal técnico**

¿La organización dispone de personal cualificado para mantener sus propios sistemas?

**Disponibilidad**

¿Es necesario que los servicios estén disponibles desde diferentes ubicaciones y durante todo el día?

---

## 3.7. Conceptos relacionados: multicloud y nube híbrida

Es frecuente encontrar los términos *multicloud* y *hybrid cloud* utilizados como si fueran equivalentes, pero no significan exactamente lo mismo.

### ¿Qué es multicloud?

Una estrategia multicloud consiste en utilizar servicios de dos o más proveedores de nube pública.

Por ejemplo, una empresa puede utilizar:

- Amazon Web Services para alojar sus aplicaciones.
- Microsoft Azure para determinados servicios empresariales.
- Google Cloud para análisis de datos.

El objetivo puede ser aprovechar las ventajas de cada proveedor, reducir la dependencia de una única empresa o utilizar servicios especializados.

### Diferencia entre multicloud e híbrida

| Nube híbrida | Multicloud |
|---|---|
| Combina diferentes tipos de infraestructura, por ejemplo privada y pública. | Utiliza servicios de varios proveedores cloud. |
| Puede utilizar un único proveedor público junto con una infraestructura privada. | Puede utilizar varios proveedores públicos sin disponer de nube privada. |
| Busca integrar entornos diferentes. | Busca aprovechar servicios de diferentes proveedores. |

Una organización puede utilizar una estrategia híbrida y multicloud al mismo tiempo.

Por ejemplo, puede mantener una infraestructura privada en sus instalaciones, utilizar AWS para alojar aplicaciones y Google Cloud para procesar datos.

---

## 3.8. Resumen del tema

Los modelos de despliegue permiten clasificar cómo se organiza y utiliza la infraestructura cloud.

- **Nube pública:** un proveedor ofrece infraestructura y servicios a diferentes clientes.
- **Nube privada:** la infraestructura está destinada exclusivamente a una organización.
- **Nube híbrida:** combina diferentes entornos, habitualmente privados y públicos, que se encuentran conectados.
- **Nube comunitaria:** varias organizaciones con intereses comunes comparten una infraestructura.

También debemos recordar que:

- Los modelos de despliegue no son lo mismo que IaaS, PaaS y SaaS.
- Una nube privada no tiene por qué estar físicamente en las instalaciones de la empresa.
- Una nube pública puede ofrecer mecanismos de aislamiento y seguridad entre clientes.
- Una infraestructura híbrida necesita mecanismos de comunicación e integración.
- Multicloud significa utilizar varios proveedores cloud y no implica necesariamente tener una nube privada.

La decisión sobre qué modelo utilizar dependerá de factores económicos, técnicos, organizativos y legales.

---

# ✍️ Actividades del Tema 3

## Actividad 1. Identificación de modelos de despliegue

**Objetivo:** reconocer los cuatro modelos de despliegue y distinguir sus características.

Lee las siguientes situaciones e indica qué modelo de despliegue representa cada una: pública, privada, híbrida o comunitaria.

1. Una startup necesita alojar su página web y contrata una máquina virtual a un proveedor externo. No dispone de servidores propios.
2. Un banco dispone de una infraestructura informática dedicada exclusivamente a sus aplicaciones internas.
3. Una universidad mantiene los expedientes académicos en sus propios sistemas y utiliza servicios cloud externos para las videoconferencias.
4. Varios hospitales comparten una plataforma tecnológica diseñada para gestionar determinados servicios sanitarios.
5. Una tienda online contrata recursos cloud adicionales durante las campañas comerciales y reduce su consumo cuando termina el periodo de mayor actividad.
6. Una administración pública dispone de una infraestructura privada y utiliza servicios de un proveedor externo para determinadas aplicaciones.
7. Tres universidades acuerdan compartir una infraestructura informática para desarrollar proyectos de investigación.
8. Una empresa utiliza exclusivamente servicios de Microsoft Azure para alojar sus aplicaciones.

Para cada caso, explica brevemente qué característica te ha permitido identificar el modelo.

## Actividad 2. Comparación de modelos

Completa la siguiente tabla:

| Característica | Pública | Privada | Híbrida | Comunitaria |
|---|---|---|---|---|
| ¿Quién utiliza la infraestructura? | | | | |
| ¿Quién puede gestionarla? | | | | |
| ¿Cómo se reparten los costes? | | | | |
| ¿Qué ventajas ofrece? | | | | |
| ¿Qué inconvenientes presenta? | | | | |
| ¿En qué tipo de organización puede resultar interesante? | | | | |

Después, responde:

1. ¿Qué modelo suele requerir una menor inversión inicial?
2. ¿Qué modelo permite reservar la infraestructura para una única organización?
3. ¿Qué modelo permite combinar infraestructura propia y servicios externos?
4. ¿Qué modelo permite compartir una infraestructura entre organizaciones con necesidades comunes?
5. ¿Qué modelo puede resultar más complejo de administrar cuando integra diferentes entornos?

## Actividad 3. Elegir el modelo adecuado

**Objetivo:** aplicar los conocimientos a situaciones reales.

Lee los siguientes casos y recomienda el modelo de despliegue más adecuado. Justifica tu respuesta.

**Caso A. Una pequeña empresa**

Una empresa acaba de comenzar su actividad. Tiene cinco trabajadores y necesita una página web, correo electrónico y almacenamiento de documentos. No dispone de personal especializado en administración de servidores y quiere evitar grandes inversiones iniciales.

**Caso B. Una entidad bancaria**

Una entidad financiera necesita ejecutar aplicaciones internas que gestionan información especialmente sensible. Dispone de un departamento informático propio y quiere mantener un elevado control sobre su infraestructura.

**Caso C. Una universidad**

Una universidad dispone de sistemas propios para gestionar expedientes académicos, pero necesita ofrecer plataformas de aprendizaje, videoconferencias y almacenamiento a miles de estudiantes.

**Caso D. Una red de hospitales**

Varios hospitales de diferentes localidades quieren compartir una plataforma informática para gestionar determinados servicios administrativos y sanitarios. Todos deben cumplir requisitos similares de seguridad y protección de datos.

Para cada caso, responde:

1. ¿Qué modelo de despliegue recomendarías?
2. ¿Qué necesidades de la organización justifican tu elección?
3. ¿Qué ventajas tendría ese modelo?
4. ¿Qué inconvenientes podría presentar?
5. ¿Consideras que existe algún modelo alternativo que también podría funcionar?

## Actividad 4. Investigación de proveedores cloud

**Objetivo:** identificar proveedores reales y relacionar sus servicios con los modelos de despliegue.

Investiga los siguientes proveedores y tecnologías:

- Amazon Web Services (AWS).
- Microsoft Azure.
- Google Cloud Platform.
- OpenStack.
- Proxmox VE.

Para cada uno, busca información y responde:

1. ¿Qué es y para qué sirve?
2. ¿Qué empresa u organización lo desarrolla o mantiene?
3. ¿Permite utilizar servicios de nube pública, privada o ambos?
4. ¿Qué tipo de organizaciones podrían utilizarlo?
5. ¿Qué ventajas ofrece?
6. ¿Qué requisitos técnicos pueden ser necesarios para utilizarlo?

Presenta los resultados en una tabla comparativa.

**Importante:** no todos los elementos de la lista son proveedores de nube pública. OpenStack y Proxmox VE son tecnologías que pueden utilizarse para construir o administrar infraestructuras propias.

## Actividad 5. ¿Híbrida o multicloud?

**Objetivo:** diferenciar dos conceptos que suelen confundirse.

Indica si las siguientes situaciones describen una estrategia híbrida, multicloud o ambas.

1. Una empresa mantiene servidores propios y utiliza AWS para alojar su página web.
2. Una empresa utiliza AWS y Google Cloud para ejecutar diferentes aplicaciones, sin disponer de infraestructura privada.
3. Una organización mantiene una infraestructura privada, utiliza Azure para alojar aplicaciones y Google Cloud para analizar datos.
4. Una empresa utiliza dos regiones diferentes de AWS para distribuir sus servicios.
5. Una universidad mantiene sus bases de datos en una infraestructura privada y utiliza Microsoft Azure para determinados servicios educativos.

Justifica todas las respuestas.

Después, responde:

- ¿Es posible utilizar varios proveedores cloud sin tener una nube híbrida?
- ¿Es posible tener una nube híbrida utilizando únicamente un proveedor público?
- ¿Qué ventajas puede aportar una estrategia multicloud?
- ¿Qué dificultades puede generar?

## Actividad 6. Debate: ¿Dónde deberían estar nuestros datos?

**Objetivo:** reflexionar sobre las implicaciones de utilizar diferentes modelos de despliegue.

Imagina que trabajas en una empresa que debe decidir dónde almacenar la información de sus clientes.

Un grupo defiende utilizar exclusivamente una nube pública porque resulta económica y permite ampliar los recursos fácilmente.

Otro grupo prefiere construir una nube privada porque considera que ofrece mayor control sobre los datos.

Organizad un debate en clase.

Cada grupo deberá preparar argumentos relacionados con:

- Seguridad y privacidad.
- Costes iniciales y mantenimiento.
- Disponibilidad.
- Escalabilidad.
- Control de la infraestructura.
- Dependencia de proveedores.
- Cumplimiento de la normativa.

Al finalizar, cada alumno deberá redactar una conclusión personal indicando qué modelo elegiría y por qué.

## Actividad 7. Diseña la infraestructura cloud de una organización

**Objetivo:** integrar los conocimientos del tema mediante un caso práctico.

Una empresa ficticia llamada **TechMarket** quiere modernizar toda su infraestructura informática.

La empresa dispone de:

- Una tienda online que recibe visitas de clientes de todo el mundo.
- Una base de datos con información de clientes y pedidos.
- Un sistema interno de gestión empresarial.
- Una plataforma de almacenamiento de documentos.
- Un departamento informático formado por cuatro trabajadores.
- Un presupuesto limitado.

Además, durante determinadas épocas del año, como Navidad o el Black Friday, la tienda online recibe muchas más visitas de lo habitual.

La dirección de la empresa solicita un informe donde se proponga un modelo de despliegue cloud.

El informe debe incluir:

1. **Análisis de necesidades:** identifica qué servicios necesita la empresa y cuáles son sus principales problemas.
2. **Modelo de despliegue:** recomienda nube pública, privada, híbrida o comunitaria.
3. **Justificación:** explica por qué has elegido ese modelo y qué alternativas has descartado.
4. **Seguridad:** indica cómo protegerías los datos y quién debería tener acceso a ellos.
5. **Escalabilidad:** explica cómo respondería la infraestructura ante un aumento de visitas.
6. **Costes:** identifica qué gastos tendría que asumir la empresa.
7. **Conclusión:** resume las ventajas e inconvenientes de tu propuesta.

Puedes utilizar diagramas, esquemas o herramientas de dibujo para representar la infraestructura.

**Entrega:** documento PDF o presentación explicativa.

---

## Actividad 8. Cuestionario de repaso

Responde a las siguientes preguntas:

1. ¿Cuáles son los cuatro modelos de despliegue definidos por el NIST?
2. ¿Qué diferencia existe entre nube pública y nube privada?
3. ¿Una nube privada tiene que estar ubicada físicamente en las instalaciones de una empresa? Razona la respuesta.
4. ¿Qué significa que una infraestructura sea compartida por varios clientes?
5. ¿Qué diferencia existe entre nube híbrida y nube comunitaria?
6. ¿Por qué una nube híbrida puede resultar interesante para una universidad?
7. ¿Qué ventajas ofrece una nube pública a una startup?
8. ¿Qué problemas puede encontrar una organización al administrar una nube privada?
9. ¿Qué significa el término multicloud?
10. ¿Es posible utilizar una estrategia híbrida y multicloud al mismo tiempo? Explica cómo.

---

## Actividad 9. Pregunta de reflexión

Imagina que tienes que crear una empresa tecnológica desde cero.

Dispones de un presupuesto limitado y necesitas ofrecer servicios digitales a clientes de diferentes países.

¿Construirías tu propia infraestructura o contratarías servicios de un proveedor cloud?

Explica qué modelo de despliegue elegirías, qué factores tendrías en cuenta y cómo cambiaría tu decisión si la empresa creciera considerablemente durante los próximos cinco años.

No existe una única respuesta correcta: se valorará la capacidad de argumentación y la coherencia de la propuesta.