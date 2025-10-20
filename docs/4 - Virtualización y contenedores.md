# 4️⃣ Virtualización y Contenedores

Imagina que tienes un servidor físico en una habitación del instituto. En él instalas Linux y montas un servidor web para tus alumnos. Todo va bien hasta que alguien más necesita usar el mismo servidor, pero con una versión diferente de PHP, o incluso otro sistema operativo. Antes, eso implicaba tener otro equipo físico, con todo su coste y mantenimiento.

La virtualización vino a romper esa barrera. Con ella, un solo servidor físico puede transformarse en decenas de servidores virtuales que funcionan de forma independiente. Cada uno con su sistema operativo, su red y sus aplicaciones.

Y cuando ya creíamos que eso era lo más eficiente, apareció Docker con los contenedores, que llevaron el concepto aún más lejos: ahora ni siquiera necesitas un sistema operativo completo para cada instancia.
Los contenedores son más ligeros, más rápidos y más fáciles de desplegar.

La nube moderna —desde Amazon Web Services hasta Google Cloud o Azure— no existiría sin la virtualización y los contenedores. Entender estas tecnologías es como abrir la puerta a lo que realmente ocurre dentro de cualquier servicio cloud.

## ¿Qué es la virtualización?

La virtualización es una tecnología que permite ejecutar múltiples sistemas operativos sobre un mismo hardware físico, compartiendo los recursos de forma controlada.

Cada sistema operativo “invitado” (guest) cree tener acceso exclusivo al hardware, pero en realidad el hipervisor se encarga de repartir CPU, memoria, disco y red entre ellos.

En otras palabras: la virtualización crea máquinas dentro de máquinas.

### Tipos de hipervisores

Existen dos grandes tipos de hipervisores:

!!!note "Tipo 1 (bare metal): se instalan directamente sobre el hardware"

👉 Ejemplos: VMware ESXi, Microsoft Hyper-V, Xen, KVM.

Usados en centros de datos y nubes públicas.

!!!note "Tipo 2 (hosted): se instalan como una aplicación dentro de un sistema operativo"

👉 Ejemplos: VirtualBox, VMware Workstation.

Usados en entornos educativos o de pruebas.

!!!error
    En el aula, cuando creáis una máquina virtual en VirtualBox, estáis usando un hipervisor tipo 2.

### Beneficios de la virtualización

- **Aislamiento**: cada VM tiene su propio entorno.
- **Eficiencia**: se aprovechan mejor los recursos del hardware.
- **Facilidad de copia y despliegue**: puedes clonar VMs en segundos.
- **Recuperación ante fallos**: las VMs pueden moverse o restaurarse fácilmente.
- **Escalabilidad**: base de toda la infraestructura de IaaS.

## Qué son los contenedores

Los contenedores no virtualizan hardware, sino el entorno de ejecución.
Comparten el mismo kernel del sistema operativo, pero aíslan procesos, librerías y dependencias.

Cada contenedor ejecuta una aplicación o servicio en un entorno controlado, asegurando que funciona igual en cualquier lugar: en tu portátil, en el aula o en la nube.

Piensa en los contenedores como “cajas” portátiles que llevan dentro tu aplicación y todo lo que necesita para funcionar.

### Diferencias entre máquinas virtuales y contenedores

|Característica|Máquinas Virtuales|Contenedores|
|-|-|-|
|Aislamiento|Total (hardware simulado)|Parcial (kernel compartido)|
|Sistema operativo|Completo por VM|Compartido|
|Peso|Pesado (GBs)|Ligero (MBs)|
|Tiempo de arranque|Minutos|Segundos|
|Ejemplo|VirtualBox, VMware|Docker, Podman, LXC|

!!!tip "En la práctica"
    una máquina virtual es como una casa entera, un contenedor es como una habitación dentro de un edificio compartido.

## Docker: el estándar de facto

Docker revolucionó la informática en 2013.
Su lema implícito podría ser: “Funciona en mi máquina... y en todas las demás”.

Con Docker, empaquetas una aplicación, sus dependencias y su entorno en una imagen inmutable. Luego la ejecutas en cualquier sistema con Docker Engine y funcionará exactamente igual.

Ejemplo básico:

!!!warning "Descargar imagen de nginx"

```bash
docker pull nginx
```

!!!tip "Ejecutar un contenedor"
```bash
docker run -d -p 8080:80 nginx
```

En segundos, tienes un servidor web funcionando en el puerto 8080. Sin instalación manual, sin conflictos de versiones, sin dolores de cabeza.

### Ecosistema Docker

- **Dockerfile**: receta para construir imágenes personalizadas.
- **Docker Hub**: repositorio público de imágenes.
- **Docker Compose**: herramienta para orquestar varios contenedores (por ejemplo, una app web + base de datos).
- **Docker Swarm / Kubernetes**: sistemas de orquestación para gestionar cientos de contenedores.

## Virtualización y contenedores en la nube

En la nube moderna, los proveedores combinan ambas tecnologías:

- La infraestructura base (IaaS) está compuesta de máquinas virtuales sobre hipervisores tipo 1.
- Los servicios intermedios (PaaS) se ejecutan sobre contenedores orquestados con Kubernetes.

Algunos servicios SaaS incluso se ofrecen directamente como contenedores en la nube.

- AWS EC2 = IaaS sobre hipervisores.
- AWS ECS o Google Cloud Run = PaaS basado en contenedores.

## Conceptos clave de orquestación

Cuando tienes cientos de contenedores, necesitas automatizar su gestión.
Ahí entra Kubernetes: el sistema que Google creó para coordinar, reiniciar, escalar y distribuir contenedores de forma automática.

Conceptos básicos:

- **Pod**: grupo de uno o más contenedores que se ejecutan juntos.
- **Node**: máquina física o virtual donde se ejecutan pods.
- **Cluster**: conjunto de nodos gestionados como una sola unidad.
- **Service**: punto de acceso estable a un conjunto de pods.

Kubernetes convierte un conjunto de servidores en una “nube dentro de la nube”.

## Ejemplo narrativo: una mini nube en el aula

Imaginad formáis parte del “cloud del aula”. Cada VM representa un nodo del clúster. Algunos alojan servicios web, otros bases de datos, y otros se encargan del monitoreo o del almacenamiento compartido.

Con Docker y VirtualBox, estáis reproduciendo a pequeña escala el mismo principio que usa Amazon o Google:
👉 una red de máquinas virtuales que ejecutan contenedores distribuidos.

## 🧮 Actividades prácticas

🔹 Actividad 1 – Virtualización

Cada alumno crea una máquina virtual con Debian Server sin entorno gráfico.
Debe instalar y configurar un servicio sencillo (por ejemplo, nginx).
Entrega: documentación con los pasos y pantallazo del servicio corriendo.

🔹 Actividad 2 – Contenedor Docker

En la misma máquina, instalan Docker y levantan un contenedor nginx:

docker run -d -p 8080:80 nginx


Comprobación: acceder a http://localhost:8080 y ver la página por defecto.

🔹 Actividad 3 – Creación de imagen personalizada

Cada alumno crea su propio Dockerfile con un pequeño servicio (por ejemplo, una página HTML o API sencilla).
Entrega: Dockerfile + prueba de ejecución.

🔹 Actividad 4 – Comparativa

Debate en clase:

¿Qué arranca más rápido?

¿Qué ocupa menos espacio?

¿En qué casos usarías VM y en cuáles contenedor?

🔹 Actividad 5 – Conexión entre compañeros

El contenedor de un alumno debe poder recibir peticiones desde la VM de otro.
Esto simula interacción entre servicios en una red cloud.