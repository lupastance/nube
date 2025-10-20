# 3️⃣ Modelos de despliegue en la Nube

Hasta ahora hemos visto los modelos de servicio (qué gestiona el proveedor y qué gestiona el cliente). Pero también es importante entender cómo se despliega la nube: dónde están los servidores, quién tiene el control de la infraestructura y cómo se accede a los recursos.

Aquí entran en juego los modelos de despliegue definidos por NIST:

  * Nube pública
  * Nube privada
  * Nube híbrida
  * Nube comunitaria

## Nube pública

La nube pública es propiedad de un proveedor externo (Amazon, Google, Microsoft, etc.) que ofrece sus recursos a múltiples clientes a través de Internet.

!!!note "Ventajas"
    Escalabilidad prácticamente ilimitada.
    Pago por uso.
    Sin necesidad de inversión inicial.

!!!error "Desventajas"
    Menor control sobre dónde están físicamente los datos.
    Riesgos de seguridad y cumplimiento normativo.

👉 Ejemplo: Gmail, AWS, Microsoft Azure.

## Nube privada

La infraestructura de la nube se dedica a un único cliente u organización. Puede estar ubicada en las instalaciones de la propia empresa (on-premise) o en un centro de datos externo, pero siempre gestionada de manera privada.

!!!note "Ventajas"
    Mayor control sobre la seguridad y ubicación de los datos.
    Cumple con requisitos regulatorios estrictos.

!!!error "Desventajas"
    Coste elevado (hardware, mantenimiento).
    Menor flexibilidad y escalabilidad frente a la nube pública.

👉 Ejemplo: una entidad bancaria que monta su propia nube interna con OpenStack.


## Nube híbrida

Combina la nube privada y la nube pública, de modo que una organización puede usar lo mejor de cada una según sus necesidades.

!!!note "Ventajas"
    Flexibilidad: datos sensibles en la nube privada, aplicaciones escalables en la pública.
    Optimización de costes.

!!!error "Desventajas"
    Mayor complejidad técnica.
    Requiere integración y gestión avanzada.

👉 Ejemplo: una universidad que guarda expedientes académicos en nube privada y usa nube pública para Moodle y videoconferencias.

## Nube comunitaria

Infraestructura compartida por varias organizaciones con intereses comunes (misma industria, regulaciones, misión). Puede ser gestionada por ellas mismas o por un proveedor externo...

!!!note "Ventajas"
    Coste compartido entre varias entidades.
    Servicios adaptados a necesidades comunes.

!!!error "Desventajas"
    Menos extendida que otros modelos.
    Complejidad en la gestión compartida.

👉 Ejemplo: hospitales que comparten una nube comunitaria para historiales médicos cumpliendo normativa sanitaria.

## Comparación visual

|Modelo|Quién lo gestiona|Escalabilidad|Coste|Ejemplo típico|
|-|-|-|-|-|
|Pública|Proveedor externo|Muy alta	Bajo inicial|pago por uso|Gmail, AWS|
|Privada|Empresa/cliente|Media|Alto, inversión propia|Nube interna bancaria|
|Híbrida|Cliente + proveedor|Alta|Variable|Universidad (expedientes privados, Moodle público)|
|Comunitaria|Varias entidades|Media|Compartido|Red de hospitales|

## ✍️ Actividades del Tema 3

Actividad 8 – Clasificación de casos
Indica qué modelo de despliegue corresponde a los siguientes casos:

Un hospital quiere máxima seguridad para historiales médicos.

Una startup que empieza con poco presupuesto y necesita escalar rápido.

Una universidad con datos sensibles pero también con plataformas abiertas a estudiantes.

Varias ONG que comparten un mismo servicio en la nube para reducir costes.

(Solución orientativa: 1 → Privada, 2 → Pública, 3 → Híbrida, 4 → Comunitaria)

Actividad 9 – Debate
¿Creéis que en el futuro predominará la nube pública o las empresas tenderán a usar nubes privadas e híbridas? Argumentad con ejemplos actuales (Google, Facebook, gobiernos, etc.).

Actividad 10 – Investigación guiada
Busca un proveedor que ofrezca nube privada, otro que ofrezca nube pública y un caso real de nube híbrida. Expón en clase qué modelo usa y por qué.