# 2️⃣ Modelos de servicios en la nube

![Cloud](assets/2-intro.png){align="right"}

En el tema anterior hemos estudiado los fundamentos de la computación en la nube y las ventajas que ofrece frente a una infraestructura tradicional. Ahora vamos a profundizar en una de las decisiones más importantes cuando una organización utiliza servicios cloud: **¿qué parte de la infraestructura queremos administrar nosotros y qué parte queremos delegar en el proveedor?**

No todas las empresas necesitan administrar servidores, instalar sistemas operativos o configurar redes. Algunas necesitan controlar hasta el último detalle de su infraestructura, mientras que otras prefieren concentrarse exclusivamente en desarrollar aplicaciones o utilizar un programa ya existente.

Para responder a estas necesidades existen diferentes modelos de servicio. Los tres modelos clásicos son:

- **IaaS (Infrastructure as a Service):** Infraestructura como Servicio.
- **PaaS (Platform as a Service):** Plataforma como Servicio.
- **SaaS (Software as a Service):** Software como Servicio.

Cada modelo ofrece un nivel diferente de control, flexibilidad y responsabilidad. Comprender estas diferencias nos permitirá seleccionar la solución más adecuada para cada proyecto.

## Objetivos del tema

Al finalizar esta unidad, deberás ser capaz de:

- Definir y diferenciar los modelos IaaS, PaaS y SaaS.
- Identificar qué componentes administra el proveedor y cuáles corresponden al cliente.
- Reconocer servicios reales de cada modelo.
- Analizar las ventajas, limitaciones y casos de uso de cada alternativa.
- Comprender el modelo de responsabilidad compartida y su relación con la seguridad.
- Comparar soluciones cloud teniendo en cuenta el control, el mantenimiento, los costes y la dependencia del proveedor.
- Comprender cómo se relacionan los contenedores y las tecnologías serverless con los modelos de servicio.
- Justificar técnicamente la elección de un modelo de servicio para una necesidad empresarial.

---

## 2.1. ¿Qué es un modelo de servicio en la nube?

Un modelo de servicio describe **qué recursos o capacidades proporciona el proveedor cloud y qué responsabilidades conserva el cliente**.

Para comprenderlo, imaginemos que una empresa necesita poner en funcionamiento una aplicación web para gestionar sus pedidos.

Tiene varias posibilidades:

1. Alquilar una máquina virtual, instalar un sistema operativo y configurar todos los componentes necesarios.
2. Utilizar una plataforma que permita publicar la aplicación sin administrar directamente el servidor.
3. Contratar una aplicación de gestión de pedidos que ya esté desarrollada y lista para utilizarse.

Las tres opciones pueden cubrir una necesidad empresarial parecida, pero el trabajo que debe realizar la empresa es muy diferente.

| Modelo | ¿Qué contrata el cliente? | ¿En qué se centra? |
|---|---|---|
| IaaS | Recursos de infraestructura virtualizados | Administrar sistemas y aplicaciones |
| PaaS | Una plataforma para desarrollar y ejecutar aplicaciones | Desarrollar, configurar y mantener la aplicación |
| SaaS | Una aplicación terminada | Utilizar y administrar el servicio |

### 2.1.1. La idea de las capas tecnológicas

Una aplicación informática depende de diferentes componentes. Aunque normalmente solo vemos la interfaz de usuario, por debajo existe una infraestructura completa.

Podemos representar las capas de una aplicación web de la siguiente forma:

```text
┌──────────────────────────────────┐
│          Aplicación web          │
├──────────────────────────────────┤
│       Código y dependencias      │
├──────────────────────────────────┤
│      Runtime y middleware        │
├──────────────────────────────────┤
│        Sistema operativo         │
├──────────────────────────────────┤
│     Virtualización y redes       │
├──────────────────────────────────┤
│      Hardware e instalaciones    │
└──────────────────────────────────┘
```

Por ejemplo, una aplicación desarrollada con Node.js necesita código JavaScript, dependencias, un entorno de ejecución, recursos de memoria y CPU, comunicaciones de red y una infraestructura sobre la que funcionar.

En una solución IaaS, el cliente administra muchas de estas capas. En una solución PaaS, el proveedor se ocupa de más componentes. En SaaS, el proveedor entrega directamente la aplicación terminada.

**Cuanto más alto es el nivel de abstracción del servicio, menos infraestructura necesita administrar directamente el cliente.** Esto no significa que desaparezcan todas sus responsabilidades: la gestión de usuarios, los permisos, los datos y el uso correcto del servicio siguen siendo importantes.

### 2.1.2. No debemos confundir servicio con tecnología

IaaS, PaaS y SaaS son modelos de servicio, no marcas comerciales ni tecnologías concretas.

Por ejemplo:

- Amazon EC2 es un servicio de máquinas virtuales que encaja en el modelo IaaS.
- Azure App Service es una plataforma gestionada para desplegar aplicaciones web, generalmente asociada a PaaS.
- Gmail es un ejemplo de SaaS.

Una misma empresa cloud puede ofrecer servicios de diferentes modelos. Por eso, no debemos clasificar a AWS, Azure o Google Cloud como si fueran exclusivamente IaaS, PaaS o SaaS.

---

## 2.2. IaaS: Infrastructure as a Service

**IaaS significa Infraestructura como Servicio.** El proveedor ofrece recursos informáticos virtualizados que el cliente puede utilizar para construir su propia infraestructura.

En lugar de comprar un servidor físico, instalarlo en una sala y mantenerlo, una organización puede contratar una máquina virtual en la nube y utilizarla como si fuera un servidor propio.

El proveedor mantiene la infraestructura física y la capa de virtualización. El cliente conserva un elevado grado de control sobre el sistema operativo, las aplicaciones y la configuración del entorno.

### 2.2.1. ¿Qué recursos proporciona IaaS?

Los servicios IaaS pueden ofrecer distintos tipos de recursos:

- **Computación:** máquinas virtuales con CPU y memoria asignadas.
- **Almacenamiento:** discos virtuales, almacenamiento de objetos y otros recursos persistentes.
- **Redes virtuales:** redes privadas, subredes, rutas y reglas de comunicación.
- **Direcciones IP:** direcciones públicas o privadas según el servicio.
- **Seguridad de red:** reglas de filtrado, grupos de seguridad y cortafuegos gestionados.
- **Balanceo de carga:** distribución del tráfico entre diferentes servidores.
- **Copias de seguridad e imágenes:** herramientas para recuperar o reproducir sistemas.

No todos estos componentes tienen que contratarse conjuntamente. Una de las ventajas de la nube es que podemos construir una infraestructura adaptada a nuestras necesidades.

### 2.2.2. ¿Qué administra el cliente?

Cuando contratamos una máquina virtual IaaS, normalmente somos responsables de instalar, configurar y mantener el sistema operativo invitado y los componentes que ejecutamos en él.

Entre las tareas habituales se encuentran:

- Instalar y actualizar Linux o Windows Server.
- Crear usuarios y configurar permisos.
- Instalar servidores web como Apache o Nginx.
- Instalar runtimes como Node.js, PHP o Java.
- Configurar bases de datos autoadministradas.
- Gestionar los servicios que se ejecutan en la máquina.
- Configurar el cortafuegos del sistema operativo.
- Aplicar actualizaciones de seguridad.
- Monitorizar el consumo de recursos.
- Realizar y comprobar copias de seguridad.
- Proteger las credenciales y las claves de acceso.

El proveedor puede ofrecer herramientas para automatizar muchas de estas tareas, pero la responsabilidad de administrarlas sigue correspondiendo al cliente cuando forman parte de su entorno.

### 2.2.3. ¿Qué administra el proveedor?

El proveedor se ocupa de las capas físicas y de la infraestructura que permite ofrecer los recursos virtualizados.

Por ejemplo:

- Los edificios, instalaciones y centros de datos.
- Los servidores físicos y sus componentes.
- La alimentación eléctrica y la refrigeración.
- La infraestructura de red física.
- La capa de virtualización.
- El mantenimiento del hardware y de la infraestructura subyacente.

El reparto exacto depende del servicio contratado. El proveedor también puede ofrecer servicios adicionales de monitorización, copias de seguridad o administración, pero no debemos asumir que están incluidos automáticamente en una máquina virtual básica.

### 2.2.4. Ejemplo real: Amazon EC2

[Amazon EC2](https://aws.amazon.com/ec2/) es un servicio de AWS que permite ejecutar instancias de computación en la nube.

Imaginemos que queremos publicar una aplicación web en una máquina virtual Linux.

El proceso general sería:

1. Elegir una región y una zona de disponibilidad.
2. Seleccionar una imagen de sistema operativo.
3. Elegir el tipo de instancia según las necesidades de CPU y memoria.
4. Configurar el almacenamiento.
5. Establecer las reglas de acceso a la red.
6. Iniciar la máquina virtual.
7. Instalar y configurar el software necesario.
8. Publicar la aplicación y comprobar su funcionamiento.
9. Mantener el sistema actualizado y supervisar sus recursos.

El proveedor administra la infraestructura física y la virtualización. Nosotros debemos configurar correctamente el sistema operativo y la aplicación.

Por ejemplo, si dejamos un servicio administrativo accesible desde Internet sin las restricciones adecuadas, no podemos asumir que AWS lo protegerá automáticamente.

### 2.2.5. Ventajas de IaaS

- **Control:** permite elegir y configurar el sistema operativo y gran parte del software.
- **Flexibilidad:** podemos adaptar los recursos a los requisitos de la aplicación.
- **Compatibilidad:** facilita migrar aplicaciones existentes que necesitan una configuración concreta.
- **Escalabilidad:** es posible aumentar o reducir recursos según las necesidades.
- **Automatización:** podemos crear infraestructuras mediante scripts y herramientas de infraestructura como código.
- **Acceso a recursos especializados:** determinados proyectos necesitan configuraciones de CPU, memoria, almacenamiento o red muy concretas.

### 2.2.6. Inconvenientes de IaaS

- **Mayor responsabilidad técnica:** el cliente debe administrar y mantener el sistema operativo y las aplicaciones.
- **Necesidad de conocimientos:** se requieren competencias de administración de sistemas, redes y seguridad.
- **Riesgo de errores de configuración:** una mala configuración puede provocar interrupciones o exponer información.
- **Costes difíciles de controlar:** los recursos olvidados, el almacenamiento y el tráfico pueden generar gastos inesperados.
- **Mantenimiento continuo:** las actualizaciones y la monitorización no desaparecen por utilizar la nube.

### 2.2.7. ¿Cuándo elegir IaaS?

IaaS resulta especialmente apropiado cuando necesitamos un alto grado de control.

Ejemplos:

- Migrar un servidor local a la nube sin modificar demasiado su funcionamiento.
- Instalar una aplicación heredada que requiere un sistema operativo específico.
- Crear un entorno de laboratorio para practicar administración de sistemas.
- Configurar una base de datos que necesita parámetros especiales y que vamos a administrar nosotros.
- Desplegar una arquitectura con varios servidores y una red personalizada.

Desde el punto de vista de SMR, IaaS está muy relacionado con la administración de sistemas operativos, redes, servicios, actualizaciones y seguridad.

---

## 2.3. PaaS: Platform as a Service

**PaaS significa Plataforma como Servicio.** El proveedor ofrece un entorno gestionado para desarrollar, desplegar y ejecutar aplicaciones sin que el cliente tenga que administrar directamente la infraestructura subyacente.

En lugar de preparar una máquina virtual, instalar un sistema operativo y configurar el entorno de ejecución, el desarrollador puede centrarse en el código de su aplicación y en los datos que utiliza.

El proveedor administra la infraestructura y buena parte de la plataforma, aunque el cliente sigue siendo responsable de su aplicación y de utilizar correctamente los servicios.

### 2.3.1. ¿Qué proporciona una plataforma PaaS?

Una plataforma PaaS puede incluir:

- Entornos de ejecución para diferentes lenguajes.
- Herramientas para desplegar aplicaciones.
- Integración con repositorios de código.
- Gestión de versiones y configuración de la aplicación.
- Herramientas de monitorización y registros.
- Opciones de escalado.
- Integración con bases de datos y otros servicios gestionados.
- Certificados HTTPS y configuración de dominios, según la plataforma.
- Mecanismos para gestionar variables de entorno y secretos.

No todos los productos PaaS incluyen las mismas funciones. Es necesario revisar las características del servicio concreto.

### 2.3.2. ¿Qué es el runtime?

El *runtime* o entorno de ejecución es el conjunto de componentes que permite ejecutar una aplicación.

Por ejemplo, una aplicación desarrollada con Node.js necesita un runtime capaz de interpretar y ejecutar JavaScript en el entorno del servidor.

Otros ejemplos son:

- PHP para ejecutar aplicaciones desarrolladas con PHP.
- Java y una máquina virtual Java para ejecutar aplicaciones Java.
- .NET para aplicaciones que utilizan este ecosistema.
- Python para aplicaciones desarrolladas con este lenguaje.

En una solución IaaS, normalmente debemos instalar y mantener el runtime en nuestra máquina virtual. En una plataforma PaaS, el proveedor puede encargarse de proporcionar y mantener ese entorno de ejecución.

Esto reduce el trabajo de administración, pero también puede limitar las versiones disponibles, las opciones de configuración y el acceso a determinados componentes del sistema.

### 2.3.3. ¿Cómo funciona un despliegue PaaS?

Imaginemos que un equipo desarrolla una API REST con Node.js y quiere publicarla en Internet.

El flujo de trabajo puede ser el siguiente:

```text
Desarrollador
     |
     v
Código de la aplicación
     |
     v
Repositorio Git
     |
     v
Plataforma PaaS
     |
     +--> Preparación del entorno
     |
     +--> Instalación de dependencias
     |
     +--> Ejecución de la aplicación
     |
     v
Aplicación accesible por HTTPS
```

Según la plataforma, el despliegue puede realizarse conectando un repositorio, subiendo un paquete o utilizando herramientas de línea de comandos.

La plataforma prepara el entorno y ejecuta la aplicación. El desarrollador sigue teniendo que mantener el código, resolver errores y proteger los datos y las credenciales que utiliza.

### 2.3.4. Ejemplos de servicios PaaS

Algunos ejemplos que podemos estudiar son:

- [Azure App Service](https://azure.microsoft.com/products/app-service/): permite alojar aplicaciones web y API en una plataforma gestionada.
- [Google App Engine](https://cloud.google.com/appengine): ofrece un entorno gestionado para ejecutar aplicaciones.
- [Heroku](https://www.heroku.com/): facilita el despliegue y la administración de aplicaciones.
- AWS ofrece distintas opciones de plataformas gestionadas, cuya clasificación depende de las características concretas del servicio.

Una consideración importante: no todo servicio que simplifica un despliegue es necesariamente PaaS en todos sus aspectos. Hay servicios híbridos y productos que combinan características de varios modelos.

### 2.3.5. Ventajas de PaaS

- **Rapidez de desarrollo:** permite centrarse en programar en lugar de preparar servidores.
- **Menor carga administrativa:** reduce las tareas de mantenimiento de la infraestructura.
- **Despliegues más sencillos:** facilita publicar nuevas versiones de una aplicación.
- **Escalabilidad:** determinadas plataformas pueden ajustar recursos automáticamente.
- **Integración:** puede simplificar el uso de bases de datos, registros y otros servicios.
- **Colaboración:** facilita que varios desarrolladores trabajen sobre una aplicación y su proceso de despliegue.

### 2.3.6. Inconvenientes de PaaS

- **Menor control:** el cliente no puede modificar libremente todas las capas de la plataforma.
- **Limitaciones técnicas:** puede haber restricciones en los lenguajes, versiones, dependencias o configuraciones admitidas.
- **Dependencia del proveedor:** una aplicación puede utilizar funciones específicas de la plataforma y resultar difícil trasladarla.
- **Costes variables:** el escalado, el tráfico y los servicios asociados pueden aumentar la factura.
- **Restricciones de ejecución:** algunas plataformas limitan la duración de los procesos, el acceso al sistema de archivos o determinados tipos de tareas.
- **Responsabilidad sobre la aplicación:** los errores del código y muchas decisiones de seguridad siguen siendo responsabilidad del desarrollador.

### 2.3.7. ¿Cuándo elegir PaaS?

PaaS suele ser una buena opción cuando una organización quiere desarrollar y desplegar aplicaciones sin dedicar demasiados recursos a administrar servidores.

Ejemplos:

- Publicar una API REST.
- Desplegar una aplicación web empresarial.
- Crear un backend para una aplicación móvil.
- Desarrollar un prototipo que debe estar disponible rápidamente.
- Ejecutar una aplicación que necesita una base de datos gestionada.

Para DAM, este modelo es especialmente interesante porque conecta directamente el desarrollo de aplicaciones con el despliegue y la operación de servicios en la nube.

### 2.3.8. ¿GitHub Pages es PaaS?

GitHub Pages permite publicar sitios web estáticos a partir de archivos HTML, CSS y JavaScript. Es un ejemplo útil para aprender a publicar una web sin administrar un servidor.

Sin embargo, no debe confundirse con una plataforma que ejecute cualquier backend. GitHub Pages no ejecuta directamente una API propia de Node.js, un servidor PHP o una aplicación Java del lado del servidor.

Es importante distinguir entre publicar archivos estáticos y ejecutar una aplicación que necesita procesamiento en el servidor.

---

## 2.4. SaaS: Software as a Service

**SaaS significa Software como Servicio.** El proveedor ofrece una aplicación terminada que el cliente puede utilizar a través de Internet, normalmente mediante un navegador o una aplicación cliente.

En este modelo, la organización no necesita instalar y mantener por su cuenta toda la infraestructura necesaria para ejecutar el software.

Ejemplos cotidianos son el correo electrónico web, las herramientas colaborativas, los sistemas de gestión empresarial y las plataformas de relación con clientes.

### 2.4.1. ¿Qué administra el proveedor?

El proveedor suele encargarse de:

- Mantener la infraestructura física y virtual.
- Administrar el sistema operativo y la plataforma.
- Mantener y actualizar la aplicación.
- Corregir errores del producto.
- Desplegar nuevas versiones.
- Mantener los componentes internos necesarios para ofrecer el servicio.

La distribución concreta de responsabilidades depende de las condiciones del servicio.

### 2.4.2. ¿Qué administra el cliente?

Aunque el software esté gestionado por el proveedor, la organización usuaria conserva responsabilidades importantes:

- Crear y desactivar cuentas de usuario.
- Asignar roles y permisos.
- Configurar opciones de seguridad.
- Proteger las credenciales de acceso.
- Gestionar la información que almacena y comparte.
- Determinar quién puede acceder a los documentos.
- Cumplir las obligaciones legales que le correspondan.
- Revisar las condiciones de conservación y exportación de datos.
- Administrar licencias y suscripciones.

Por ejemplo, una empresa puede utilizar una aplicación SaaS perfectamente mantenida por su proveedor y, aun así, exponer información confidencial si configura incorrectamente los permisos de sus documentos.

### 2.4.3. Ejemplos de SaaS

| Servicio | Uso principal |
|---|---|
| Gmail | Correo electrónico |
| Google Workspace | Correo, documentos y colaboración |
| Microsoft 365 | Productividad y colaboración |
| Salesforce | Gestión de clientes |
| Trello | Organización de tareas y proyectos |
| Canva | Diseño y creación de contenido |

La lista es ilustrativa. Las funcionalidades y los modelos comerciales pueden cambiar con el tiempo.

### 2.4.4. Ventajas de SaaS

- **Puesta en marcha rápida:** normalmente basta con crear una cuenta y configurar el servicio.
- **Menos mantenimiento técnico:** el proveedor administra la aplicación y su infraestructura.
- **Acceso desde diferentes dispositivos:** muchos servicios funcionan mediante navegador.
- **Actualizaciones centralizadas:** el proveedor mantiene el producto.
- **Colaboración:** permite compartir información y trabajar simultáneamente.
- **Costes iniciales reducidos:** no es necesario adquirir y mantener una infraestructura propia para utilizar el software.

### 2.4.5. Inconvenientes de SaaS

- **Menor control técnico:** el cliente no puede modificar libremente el funcionamiento interno de la aplicación.
- **Dependencia del proveedor:** un cambio de condiciones o la interrupción del servicio puede afectar al negocio.
- **Privacidad y protección de datos:** es necesario conocer dónde y cómo se procesan los datos y qué obligaciones corresponden a cada parte.
- **Limitaciones de personalización:** solo se pueden configurar las opciones disponibles.
- **Costes recurrentes:** las suscripciones pueden aumentar al crecer el número de usuarios o las necesidades.
- **Migración:** exportar los datos y trasladar los procesos a otro proveedor puede resultar complicado.
- **Dependencia de la conectividad:** muchos servicios necesitan una conexión a Internet para funcionar con normalidad.

### 2.4.6. ¿Cuándo elegir SaaS?

SaaS es adecuado cuando una organización necesita una aplicación existente y no desea desarrollar ni mantener su propia solución.

Ejemplos:

- Correo electrónico corporativo.
- Videoconferencias y colaboración.
- Gestión de tareas.
- CRM para administrar clientes.
- Herramientas de contabilidad.
- Plataformas de gestión documental.

No tiene sentido desarrollar y mantener un sistema de correo propio si una solución SaaS cubre las necesidades de la organización a un coste y con unas condiciones aceptables.

Sin embargo, la decisión debe considerar también la privacidad, los requisitos legales, la continuidad del servicio y la posibilidad de recuperar los datos si se cambia de proveedor.

---

## 2.5. Modelo de responsabilidad compartida

Uno de los conceptos más importantes de la computación en la nube es el **modelo de responsabilidad compartida**.

Utilizar un servicio cloud no significa que el proveedor sea responsable de todos los aspectos de seguridad. Las responsabilidades se distribuyen entre el proveedor y el cliente según el servicio contratado.

El proveedor protege la infraestructura y los componentes que administra. El cliente debe proteger los recursos, las aplicaciones, los datos y los accesos que se encuentran bajo su responsabilidad.

### 2.5.1. Comparación entre IaaS, PaaS y SaaS

El siguiente esquema es una simplificación didáctica de los modelos clásicos. El reparto exacto depende de las condiciones y funcionalidades del servicio concreto.

| Componente o tarea | IaaS | PaaS | SaaS |
|---|---|---|---|
| Centro de datos y hardware | Proveedor | Proveedor | Proveedor |
| Infraestructura de red física | Proveedor | Proveedor | Proveedor |
| Virtualización | Proveedor | Proveedor | Proveedor |
| Sistema operativo subyacente | Cliente | Proveedor | Proveedor |
| Runtime y plataforma subyacente | Cliente | Proveedor | Proveedor |
| Aplicación | Cliente | Cliente | Proveedor |
| Configuración de usuarios y permisos | Cliente | Cliente | Cliente |
| Uso autorizado y gestión de datos | Cliente | Cliente | Cliente |

En SaaS, el proveedor mantiene la aplicación, pero el cliente debe configurar los usuarios, los permisos y las opciones de seguridad que le correspondan. La tabla no implica que todos los productos SaaS permitan acceder a las mismas opciones.

### 2.5.2. Ejemplos de incidentes

**Caso 1: una máquina virtual sin actualizar**

Una empresa utiliza una máquina virtual Linux y no instala actualizaciones de seguridad durante meses.

La responsabilidad de mantener el sistema operativo invitado corresponde normalmente al cliente. Que la máquina esté alojada en AWS no significa que el sistema operativo se actualice automáticamente.

**Caso 2: una aplicación PaaS con una vulnerabilidad**

Una empresa despliega una aplicación web en una plataforma gestionada, pero el código contiene un error que permite acceder a información de otros usuarios.

Aunque el proveedor mantenga la infraestructura, la empresa sigue siendo responsable de corregir los errores de su aplicación y de proteger adecuadamente los datos.

**Caso 3: documentos compartidos públicamente en un SaaS**

Una organización utiliza una suite de productividad y configura un documento confidencial para que cualquier persona con el enlace pueda acceder.

El proveedor mantiene la plataforma, pero la configuración de los permisos y el uso de la información son responsabilidades que la organización debe gestionar.

### 2.5.3. La seguridad no desaparece al subir a la nube

En cualquier modelo debemos considerar, entre otras, las siguientes medidas:

- Utilizar contraseñas robustas y autenticación multifactor.
- Aplicar el principio de mínimo privilegio.
- Mantener actualizados los componentes que administramos.
- Proteger las claves y los secretos.
- Cifrar la información cuando corresponda.
- Revisar los registros de actividad.
- Establecer políticas de copias de seguridad y recuperación.
- Comprobar periódicamente los permisos y accesos.
- Planificar la recuperación ante incidentes.

La diferencia entre los modelos no es que uno sea seguro y otro inseguro. La diferencia está en qué componentes podemos controlar y qué tareas debemos realizar nosotros.

---

## 2.6. ¿Cómo elegir entre IaaS, PaaS y SaaS?

No existe un modelo que sea siempre mejor que los demás. La elección depende de las necesidades técnicas, económicas y organizativas.

### 2.6.1. Criterios de decisión

**1. Nivel de control**

Si necesitamos modificar el sistema operativo, instalar software especial o configurar servicios de forma muy específica, IaaS puede ser la opción más apropiada.

Si no necesitamos controlar esas capas, PaaS o SaaS pueden reducir el trabajo de administración.

**2. Velocidad de desarrollo**

Cuando el objetivo es publicar una aplicación rápidamente, PaaS puede simplificar el despliegue.

Si ya existe una aplicación comercial que cubre todas las necesidades, SaaS puede evitar el desarrollo desde cero.

**3. Personal disponible**

Una organización con personal especializado en sistemas puede asumir la administración de una infraestructura IaaS.

Si el equipo es pequeño y se centra en desarrollar software, PaaS puede reducir la carga operativa.

**4. Requisitos de seguridad y cumplimiento normativo**

La organización debe conocer qué datos procesa, qué obligaciones tiene y qué controles necesita.

No debemos asumir que IaaS garantiza por sí solo un mayor cumplimiento normativo, ni que SaaS impide cumplirlo. Hay que evaluar el servicio, su configuración, sus garantías contractuales y las obligaciones aplicables.

**5. Costes**

No debemos comparar únicamente el precio mensual del servicio.

En IaaS también hay que considerar el tiempo de administración, las actualizaciones, las copias de seguridad y la monitorización. En PaaS y SaaS hay que considerar las suscripciones, los límites, el consumo y los costes asociados a la evolución del proyecto.

**6. Escalabilidad**

PaaS suele facilitar el escalado de las aplicaciones porque muchas tareas están integradas en la plataforma.

IaaS también puede escalar, aunque puede requerir más configuración. SaaS permite utilizar una aplicación gestionada, pero las posibilidades de escalado dependen del proveedor y del plan contratado.

**7. Dependencia del proveedor**

Una solución que utiliza funciones muy específicas de un proveedor puede ser más difícil de trasladar.

Este riesgo puede aparecer en los tres modelos, aunque sus consecuencias y el esfuerzo de migración serán diferentes.

### 2.6.2. Tabla comparativa

| Criterio | IaaS | PaaS | SaaS |
|---|---|---|---|
| Control técnico | Alto | Intermedio | Limitado a la configuración disponible |
| Administración de servidores | Elevada | Reducida | Normalmente no corresponde al cliente |
| Personalización | Alta | Depende de la plataforma | Depende de la aplicación |
| Rapidez de puesta en marcha | Variable | Generalmente alta | Generalmente muy alta |
| Conocimientos de sistemas | Elevados | Moderados | Menores, aunque hay que administrar el servicio |
| Desarrollo de aplicaciones propias | Sí | Sí, es uno de sus usos principales | No suele ser necesario |
| Administración del código propio | Cliente | Cliente | El proveedor mantiene el producto |
| Ejemplo | Amazon EC2 | Azure App Service | Gmail |

Esta comparación es orientativa. Los servicios reales pueden incorporar funciones que no encajan exactamente en una sola categoría.

### 2.6.3. El coste total de propiedad

El coste de un servicio cloud no es únicamente lo que aparece en la factura del proveedor.

El **coste total de propiedad**, o TCO (*Total Cost of Ownership*), considera los gastos necesarios para utilizar y mantener una solución durante un periodo determinado.

Podemos incluir:

- Coste de computación, almacenamiento y red.
- Licencias y suscripciones.
- Tiempo de administración y mantenimiento.
- Desarrollo y adaptación de aplicaciones.
- Copias de seguridad y recuperación.
- Monitorización y seguridad.
- Formación del personal.
- Migración y posibles costes de salida.

Por ejemplo, IaaS puede tener un precio de infraestructura atractivo, pero exigir muchas horas de administración. PaaS puede reducir esas horas, aunque cobrar más por determinadas capacidades gestionadas. SaaS puede evitar el desarrollo de una aplicación, pero su suscripción puede aumentar a medida que crece la organización.

**No existe una regla universal según la cual IaaS, PaaS o SaaS sea siempre más barato.** Hay que comparar soluciones que satisfagan las mismas necesidades y considerar todos sus costes relevantes.

---

## 2.7. Tecnologías relacionadas: contenedores y serverless

Además de los tres modelos clásicos, existen tecnologías que han cambiado la manera de empaquetar, desplegar y ejecutar aplicaciones.

Es importante comprender que **contenedores y serverless no son modelos equivalentes a IaaS, PaaS y SaaS**. Son tecnologías o formas de ofrecer y ejecutar servicios que pueden utilizarse dentro de diferentes arquitecturas cloud.

### 2.7.1. Contenedores

Un contenedor permite ejecutar una aplicación con sus dependencias dentro de un entorno aislado.

Por ejemplo, una aplicación Node.js puede necesitar una versión concreta del runtime y varias bibliotecas. En lugar de instalar todo manualmente en cada máquina, podemos definir una imagen que incluya los componentes necesarios para ejecutar la aplicación.

Docker es una de las tecnologías más conocidas para crear y ejecutar contenedores.

#### Conceptos fundamentales

- **Imagen:** plantilla que contiene los archivos y componentes necesarios para crear un contenedor.
- **Contenedor:** instancia en ejecución de una imagen.
- **Registro de imágenes:** servicio que almacena imágenes para su distribución.
- **Dockerfile:** archivo de instrucciones utilizado para construir una imagen.
- **Volumen:** mecanismo para mantener datos fuera del ciclo de vida del contenedor.
- **Red de contenedores:** mecanismo para permitir la comunicación entre contenedores.

#### Ejemplo de uso

Un desarrollador puede preparar una aplicación y empaquetarla en una imagen Docker. Esa imagen puede ejecutarse en su ordenador, en una máquina virtual o en un servicio gestionado de contenedores.

Esto facilita reproducir entornos, pero no elimina todas las tareas de administración.

Si ejecutamos Docker en una máquina virtual propia, seguimos siendo responsables de administrar el sistema operativo, Docker, las actualizaciones y la seguridad de la infraestructura.

En cambio, si utilizamos una plataforma gestionada que se ocupa del plano de control y de la infraestructura de ejecución, parte de esas responsabilidades puede recaer en el proveedor.

#### Relación con IaaS y PaaS

Podemos encontrar diferentes escenarios:

- Instalar Docker en una máquina virtual propia: la infraestructura suele encajar en IaaS.
- Utilizar una plataforma que construye y ejecuta contenedores sin que administramos los servidores subyacentes: puede encajar en PaaS.
- Utilizar una aplicación SaaS que internamente se ejecuta en contenedores: el usuario final no necesita administrar esos contenedores.

La tecnología utilizada internamente no determina por sí sola el modelo de servicio que recibe el cliente.

### 2.7.2. Serverless

Serverless es un enfoque que permite ejecutar código o utilizar servicios sin tener que administrar directamente los servidores subyacentes.

El término puede resultar engañoso: **los servidores siguen existiendo; lo que cambia es quién se ocupa de su administración y cuánto control necesita el usuario sobre ellos**.

Una modalidad conocida es FaaS (*Function as a Service*), que permite ejecutar funciones en respuesta a eventos.

Ejemplos de eventos:

- Recibir una petición HTTP.
- Subir un archivo a un almacenamiento.
- Recibir un mensaje en una cola.
- Procesar un evento generado por otra aplicación.
- Ejecutar una tarea programada.

#### Ejemplo: procesar una imagen

Imaginemos una aplicación que permite subir fotografías. Cuando se carga una imagen, queremos generar automáticamente una versión reducida.

Podríamos construir una arquitectura de este tipo:

```text
Usuario sube una imagen
          |
          v
Almacenamiento cloud
          |
          v
Se genera un evento
          |
          v
Función serverless
          |
          v
Se crea una miniatura
          |
          v
Se guarda el resultado
```

La función se ejecuta cuando se produce el evento, sin que tengamos que mantener un servidor dedicado exclusivamente a esa tarea.

#### Ejemplo real: AWS Lambda

[AWS Lambda](https://aws.amazon.com/lambda/) permite ejecutar código en respuesta a eventos y peticiones compatibles.

El desarrollador sigue teniendo que escribir y mantener el código, gestionar los permisos y proteger los datos. El proveedor se ocupa de la infraestructura de ejecución según las condiciones del servicio.

#### Ventajas de serverless

- Reduce la necesidad de administrar servidores.
- Puede ajustarse a cargas de trabajo variables.
- Facilita construir aplicaciones orientadas a eventos.
- Permite pagar según el uso en determinados modelos de facturación.
- Se integra con otros servicios cloud.

#### Inconvenientes de serverless

- Puede haber límites de duración, memoria y configuración.
- El comportamiento y los costes dependen de la carga de trabajo.
- La depuración puede resultar más compleja en sistemas distribuidos.
- La arquitectura puede depender de servicios específicos del proveedor.
- No todos los procesos son adecuados para una ejecución por eventos.

Serverless es especialmente útil para tareas puntuales, procesamiento de eventos y determinados componentes de aplicaciones. No sustituye automáticamente a todos los servidores o aplicaciones tradicionales.

---

## 2.8. Casos prácticos

En esta sección vamos a aplicar los conceptos anteriores a situaciones reales.

### Caso 1. Una empresa necesita migrar un servidor antiguo

Una empresa dispone de una aplicación que funciona en Linux y necesita una configuración concreta del sistema operativo. No quiere modificar la aplicación y dispone de personal de administración de sistemas.

**Modelo recomendado: IaaS.**

Una máquina virtual permite mantener un entorno similar al existente y conservar un control elevado sobre el sistema operativo y los servicios.

La empresa tendrá que asumir el mantenimiento del sistema operativo, las actualizaciones, la configuración de seguridad y la monitorización.

### Caso 2. Un equipo quiere publicar una API REST

Un equipo de desarrollo ha creado una API con Node.js. Quiere publicarla rápidamente y no desea dedicar tiempo a mantener servidores.

**Modelo recomendado: PaaS.**

Una plataforma gestionada puede proporcionar el runtime, facilitar los despliegues y reducir la carga de administración.

El equipo sigue siendo responsable del código, las dependencias, los datos, los permisos y la configuración de su aplicación.

### Caso 3. Un centro necesita correo electrónico corporativo

Un centro educativo necesita cuentas de correo, calendario y herramientas de colaboración. No quiere instalar y mantener servidores propios para prestar estos servicios.

**Modelo recomendado: SaaS.**

Una suite de productividad puede cubrir esas necesidades con una aplicación ya desarrollada.

El centro debe administrar las cuentas, los permisos, la seguridad de acceso y el uso de los datos de acuerdo con sus obligaciones.

### Caso 4. Una empresa necesita procesar archivos automáticamente

Una aplicación recibe archivos y debe generar un informe cada vez que se sube uno nuevo.

Una arquitectura basada en eventos y funciones serverless puede ser una buena alternativa, si el volumen de trabajo, los requisitos y las limitaciones del servicio lo permiten.

En este caso estamos eligiendo una forma de ejecutar una parte de la aplicación, no sustituyendo necesariamente toda la arquitectura por un único modelo de servicio.

---

## 2.9. Actividades

### Actividad 1. Clasificación de servicios

Investiga los siguientes servicios y clasifícalos según el modelo de servicio que mejor describa la experiencia que recibe el cliente:

- Amazon EC2.
- Azure App Service.
- Gmail.
- Google App Engine.
- Microsoft 365.
- AWS Lambda.
- GitHub Pages.
- Salesforce.

Para cada servicio, responde:

1. ¿Qué ofrece?
2. ¿Qué necesita administrar el cliente?
3. ¿Qué tareas realiza el proveedor?
4. ¿Qué conocimientos técnicos son necesarios para utilizarlo?
5. ¿Qué ventajas e inconvenientes presenta?
6. ¿Por qué lo clasificarías en ese modelo?

**Importante:** algunos servicios, como AWS Lambda o GitHub Pages, requieren una explicación más precisa que una clasificación simple. Justifica el modelo atendiendo a lo que administra el cliente y a lo que proporciona el servicio.

### Actividad 2. Responsabilidades y seguridad

Lee las siguientes situaciones e indica si la responsabilidad corresponde principalmente al cliente, al proveedor o si está compartida.

1. El sistema operativo de una máquina virtual IaaS no recibe actualizaciones.
2. El hardware físico del centro de datos falla.
3. Una aplicación PaaS contiene una vulnerabilidad en el código.
4. Una empresa configura incorrectamente los permisos de un documento en una aplicación SaaS.
5. Un usuario comparte sus credenciales con otra persona.
6. Una organización no comprueba si puede exportar sus datos antes de cancelar una suscripción.
7. Una aplicación almacena una clave secreta directamente en el código fuente.
8. El proveedor publica una actualización de la aplicación SaaS que mantiene.

Para cada caso, explica la razón de tu respuesta y propone una medida preventiva cuando sea posible.

### Actividad 3. Elección del modelo

Una empresa ficticia necesita resolver tres necesidades:

- Alojar una aplicación antigua que requiere una versión específica de Linux.
- Publicar una nueva API desarrollada con Node.js.
- Disponer de correo electrónico y calendario para todos sus trabajadores.

Elabora una tabla con las siguientes columnas:

| Necesidad | Modelo propuesto | Servicio de ejemplo | Responsabilidades del cliente | Justificación |
|---|---|---|---|---|

No es suficiente con indicar IaaS, PaaS o SaaS. Debes justificar por qué el modelo elegido es adecuado y mencionar alguna alternativa posible.

### Actividad 4. Comparación económica

Dos soluciones permiten alojar una misma aplicación.

- La solución A ofrece una máquina virtual económica, pero requiere que el equipo administre el sistema operativo, el runtime, las actualizaciones y las copias de seguridad.
- La solución B ofrece una plataforma gestionada con un precio de servicio superior, pero reduce parte del trabajo de administración.

Responde:

1. ¿Qué solución podría tener un menor coste de infraestructura?
2. ¿Cuál podría requerir menos horas de administración?
3. ¿Qué otros costes deberíamos tener en cuenta?
4. ¿Qué información necesitaríamos para comparar ambas soluciones?
5. ¿Podemos afirmar que una es siempre más barata que la otra? Justifica tu respuesta.

No necesitas inventar precios. El objetivo es aprender a identificar las variables que intervienen en una comparación de costes.

### Actividad 5. Debate: dependencia de SaaS

Una empresa utiliza una aplicación SaaS para almacenar todos sus documentos y gestionar sus procesos internos.

Debatid las siguientes cuestiones:

- ¿Qué ocurre si el proveedor deja de prestar el servicio?
- ¿Qué riesgos aparecen si resulta difícil exportar los datos?
- ¿Qué medidas se pueden adoptar para reducir la dependencia?
- ¿Es razonable utilizar SaaS para todos los procesos de una empresa?
- ¿Qué criterios deberían utilizarse para decidir qué información se almacena en cada servicio?

Cada grupo debe presentar una conclusión argumentada.

---

## 2.10. Práctica integradora: diseñar una solución cloud

### Escenario

Una pequeña empresa quiere modernizar su infraestructura. Actualmente utiliza un servidor local para una aplicación interna y herramientas independientes para gestionar sus documentos.

La empresa desea:

- Mantener una aplicación antigua que necesita una configuración específica.
- Desarrollar una nueva aplicación web.
- Utilizar correo y documentos compartidos.
- Reducir las tareas de mantenimiento que no aportan valor directo al negocio.
- Mantener un nivel adecuado de seguridad y controlar los costes.

### Objetivo

Diseñar una propuesta de servicios cloud que responda a las necesidades de la empresa, justificando la elección de cada modelo y las responsabilidades asociadas.

### Parte A. Análisis de necesidades

Identifica las necesidades técnicas y organizativas.

Para cada una, indica si requiere infraestructura configurable, una plataforma de desarrollo o una aplicación terminada.

### Parte B. Selección de servicios

Propón una solución para cada necesidad.

Puedes utilizar servicios reales de AWS u otros proveedores. No es necesario contratar servicios ni introducir datos de pago.

### Parte C. Responsabilidad compartida

Explica quién se encarga de:

- Mantener el sistema operativo.
- Actualizar el entorno de ejecución.
- Mantener el código de la aplicación.
- Administrar los usuarios.
- Proteger los datos.
- Controlar los costes.
- Gestionar las copias de seguridad.

Adapta las respuestas a cada servicio elegido.

### Parte D. Seguridad y riesgos

Identifica al menos tres riesgos y propone medidas para reducirlos.

Puedes considerar el acceso no autorizado, la pérdida de datos, los errores de configuración, la dependencia del proveedor o los costes imprevistos.

### Parte E. Conclusiones

Prepara una breve memoria técnica con:

1. Descripción de las necesidades.
2. Servicios seleccionados y justificación.
3. Tabla de responsabilidades.
4. Riesgos y medidas preventivas.
5. Costes que deberían investigarse antes de implantar la solución.
6. Limitaciones de la propuesta.

La memoria puede presentarse como documento Markdown, informe o exposición breve, según las indicaciones del profesor.

## 2.11. Resumen del tema

Los modelos IaaS, PaaS y SaaS representan diferentes maneras de consumir recursos y capacidades informáticas a través de la nube.

- **IaaS:** proporciona infraestructura virtualizada. El cliente dispone de mucho control y asume una parte importante de la administración del sistema.
- **PaaS:** proporciona una plataforma gestionada para desarrollar y ejecutar aplicaciones. Reduce la administración de la infraestructura, pero el cliente sigue siendo responsable de su código y de los datos que gestiona.
- **SaaS:** proporciona una aplicación terminada. El proveedor mantiene el software, mientras que el cliente administra los usuarios, los permisos, la información y el uso que hace del servicio.

La elección depende de las necesidades de control, los conocimientos disponibles, el tiempo de desarrollo, los requisitos de seguridad, los costes y la dependencia del proveedor.

El modelo de responsabilidad compartida nos recuerda que contratar un servicio cloud no elimina todas las obligaciones del cliente. Debemos comprender qué componentes administra el proveedor y qué medidas tenemos que aplicar nosotros.

Por último, los contenedores y las tecnologías serverless permiten construir y desplegar aplicaciones de formas diferentes, pero no deben confundirse con los modelos clásicos de servicio.

!!!tip
    La idea fundamental que debemos recordar es que no elegimos un modelo únicamente por su tecnología o por su precio: lo elegimos porque distribuye el control, el trabajo y las responsabilidades de una forma adecuada para las necesidades del proyecto.**
<!-- 
## Preguntas de repaso

1. ¿Qué diferencia fundamental existe entre IaaS, PaaS y SaaS?
2. ¿Qué responsabilidades conserva el cliente al contratar una máquina virtual IaaS?
3. ¿Qué es un runtime y qué ventaja ofrece una plataforma PaaS respecto a su administración?
4. ¿Por qué utilizar SaaS no elimina la responsabilidad sobre los datos?
5. ¿En qué consiste el modelo de responsabilidad compartida?
6. ¿Qué factores deben considerarse al comparar los costes de IaaS y PaaS?
7. ¿Por qué Docker no es, por sí mismo, un modelo de servicio cloud?
8. ¿Qué significa serverless y por qué no implica que no existan servidores?
9. ¿Qué riesgos puede tener una dependencia excesiva de un proveedor SaaS?
10. Una empresa necesita controlar el sistema operativo de una aplicación, desarrollar una API y contratar correo electrónico. ¿Qué modelos elegirías para cada necesidad y por qué? -->

---