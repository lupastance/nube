# 2️⃣ Modelos de servicios en la nube

![Cloud](assets/2-intro.png){align="right"}

Vamos a desmenuzar los modelos de servicio en la nube: qué son, en qué se diferencian, responsabilidades, usos típicos, problemas habituales y prácticas de aula con soluciones.

Este tema es central para que entendamos qué nivel de control y de responsabilidad tiene según la elección del servicio y por qué una organización escogería uno u otro.

!!!tip "Objetivos del tema"

- Definir y diferenciar IaaS, PaaS y SaaS con claridad.
- Comprender qué gestiona el proveedor y qué gestiona el cliente en cada modelo.
- Identificar casos de uso, ventajas e inconvenientes prácticos.
- Conocer servicios y tecnologías relacionadas (contenedores, serverless).
- Realizar prácticas guiadas: desplegar una VM (IaaS), desplegar una app en PaaS y usar/administrar un SaaS.

---

## Definiciones y visión general del ☁️ Cloud Computing

Actualmente disponemos de 3 modelos diferentes a la hora de gestionar un proyecto en la nube. Entre las opciones disponibles tenemos las siguientes:

**IaaS**<br>Infrastructure as a Service (Infraestructura como Servicio).
    
    - El proveedor ofrece infraestructura virtualizada 👉 máquinas virtuales, redes virtuales, almacenamiento en bloque/objeto, balanceadores, direcciones IP.
    
    - El cliente controla OS, middleware, runtimes, aplicaciones y datos. El proveedor controla hardware físico, virtualización, y parte de la red física.

    - Casos típicos 👉 migración de servidores on-premise, entornos de pruebas, clusters de cálculo, hosts para bases de datos o aplicaciones que requieren control detallado.

**PaaS**<br>Platform as a Service (Plataforma como Servicio)

    - El proveedor facilita una plataforma completa para desarrollar, ejecutar y escalar aplicaciones sin gestionar la infraestructura subyacente. Incluye runtime, servicios gestionados (bases de datos, colas), escalado automático.

    - El cliente se centra en código y datos ❌ no gestiona OS ni la capa de runtime subyacente 👇

    - Casos típicos 👉 equipos de desarrollo que quieren enfocarse en el producto sin administrar servidores (APIs, apps web, microservicios simples).

!!!warning "¿Qué es la capa de runtime subyacente?"
    La capa de runtime es el entorno de ejecución que permite que una aplicación funcione: incluye el sistema operativo, los intérpretes de lenguajes de programación, las librerías necesarias, las máquinas virtuales (como la JVM para Java o el CLR para .NET), frameworks y gestores de dependencias.

**SaaS**<br>Software as a Service (Software como servicio)

    - 🟢 Ventajas: cero operaciones, uso inmediato, actualizaciones por parte del proveedor, coste predecible por usuario.

    - 🔴 Inconvenientes: poca personalización, dependencia del proveedor, cuestiones de privacidad y compliance.

### ¿Cuál elegir?

Criterios para elegir entre **IaaS** /// **PaaS** /// **SaaS**

- **Necesidad de control**: si necesitas kernel tweak, drivers o configuraciones especiales 👉 IaaS.
- **Velocidad de desarrollo / time to market**: PaaS o SaaS.
- **Personal disponible**: si no hay personal de SysAdmin 👉 PaaS o SaaS.
- **Requisitos regulatorios**: si debes controlar físicamente la ubicación de datos, quizá nube privada o IaaS con control de región.
- **Coste**: corto plazo PaaS o SaaS suelen ser más baratos. A largo plazo y a gran escala IaaS optimizado puede ser mejor
- **Escalado impredecible**: PaaS/SaaS facilitan el autoscaling.