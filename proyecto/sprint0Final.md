# Sprint 0 — Planificación del Proyecto y Definición del Sprint #1

**Proyecto:** SIGVA — Sistema Integral de Gestión de Vuelos y Venta de Pasajes

**Enunciado:** N.º 2 — Sistema integral web (y app móvil) para una aerolínea nacional

**Rol de la comisión:** Análisis y Management

**Materia:** Administración de Proyectos de Software — Segundo Cuatrimestre 2026

**Fecha de entrega del Sprint 0:** lunes 21/09/2026

**Integrantes:**
- Bertotto Tomás
- Blanco Oscar
- Cid Nicolás


---

# Parte 1 — User Stories

## 1.1. Consideraciones generales

En este apartado presentamos los *user stories* que componen el *product backlog*, dando una descripción de cada una. Posteriormente, para los *stories* atacados en el Sprint #1, presentamos su separación en tareas y los criterios de aceptación asociados.

A diferencia de un proyecto real hecho con Scrum, donde los *stakeholders* representados por el *Product Owner* son quienes establecen el *business value* de cada story, aquí fuimos nosotros quienes lo establecimos, para que la especificación quede completa.

**Formato de las user stories.** Cada story se escribe desde el punto de vista del usuario con el formato *Como [rol] / Quiero [objetivo] / De forma que [beneficio]*, procurando cumplir el modelo **INVEST**: tan independientes entre sí como sea posible, negociables, con valor para el usuario o para la aerolínea, estimables, pequeñas (menos de 3 semanas-hombre) y testeables mediante criterios de aceptación objetivos.

**Actores del sistema**: *Administrador de la aerolínea*, *Empleado de mostrador* y *Pasajero*. Para las stories técnicas se utiliza el rol *Miembro del equipo de desarrollo*.

### Supuestos y aclaraciones del análisis

Del análisis del enunciado surgen las siguientes definiciones, que se tomaron como base del backlog y deberán validarse con la aerolínea:

1. **Vuelo y salida.** Un *vuelo* (p. ej. AR1450 Bahía Blanca → Aeroparque) es una programación que opera ciertos días de la semana en un horario fijo, dentro de un período del año. Cada operación concreta en una fecha se denomina *salida*. La disponibilidad de asientos, la venta y la ocupación se calculan **por salida** (vuelo + fecha), lo que permite cumplir con los reportes "por vuelo, clase y fecha".
2. **Período de disponibilidad.** El "período del año en que el vuelo estará disponible para la venta" se interpreta como el rango de fechas (desde / hasta) en el que el vuelo opera y puede comprarse.
3. **Vuelos nocturnos.** Si la hora de llegada es menor o igual a la de partida, se interpreta que el vuelo llega al día siguiente (se indica "+1").
4. **Límite de compra.** El máximo de 9 pasajes por transacción equivale a 9 pasajeros, todos en la misma salida y la misma clase.
5. **Empleados de mostrador.** El enunciado exige una interfaz específica para este rol, pero no detalla sus funciones. Se asume que el mostrador consulta vuelos y disponibilidad, vende pasajes y asiste a pasajeros con su documentación.
6. **Pagos.** Se integrará una pasarela de pagos externa (en modo *sandbox* durante el desarrollo); el sistema no almacena los datos completos de las tarjetas.

---

## 1.2. Product Backlog

### 1 — Base técnica y acceso al sistema

#### Preparación de la infraestructura del proyecto

> **User story 1:**
> - **Como:** Miembro del equipo de desarrollo
> - **Quiero:** Preparar la infraestructura del proyecto (repositorio, entorno de desarrollo, integración continua y entorno de demostración)
> - **De forma que:** El equipo cuente con una base técnica común y verificable para trabajar de manera ágil durante todos los sprints
>
> **Story points:** 5 — **Business value:** 8

#### Diseño e implementación del modelo de datos

> **User story 2:**
> - **Como:** Miembro del equipo de desarrollo
> - **Quiero:** Diseñar e implementar el modelo de datos del sistema (aeropuertos, vuelos, salidas, clases, tarifas, usuarios, pasajeros, compras, pasajes y pagos)
> - **De forma que:** Todas las funcionalidades se apoyen sobre una estructura de datos consistente y extensible
>
> **Story points:** 8 — **Business value:** 8

#### Inicio de sesión y control de acceso por rol

> **User story 3:**
> - **Como:** Usuario del sistema (administrador, empleado de mostrador o pasajero)
> - **Quiero:** Iniciar sesión con mis credenciales y acceder únicamente a la interfaz y a las funciones de mi rol
> - **De forma que:** Las operaciones críticas de la aerolínea queden protegidas y cada usuario tenga una experiencia acorde a su perfil
>
> **Story points:** 5 — **Business value:** 13

#### Registro de pasajeros

> **User story 4:**
> - **Como:** Pasajero
> - **Quiero:** Crear una cuenta en la plataforma con mis datos personales y un email de contacto
> - **De forma que:** Pueda comprar pasajes y recibir en mi email la documentación y las novedades de mis vuelos
>
> **Story points:** 3 — **Business value:** 8

#### Gestión de cuentas de empleados

> **User story 5:**
> - **Como:** Administrador de la aerolínea
> - **Quiero:** Crear, modificar y dar de baja las cuentas de los empleados de mostrador y de otros administradores
> - **De forma que:** Solo el personal autorizado acceda a las interfaces internas de la aerolínea
>
> **Story points:** 3 — **Business value:** 5

### 2 — Administración de vuelos

#### Gestión de aeropuertos

> **User story 6:**
> - **Como:** Administrador de la aerolínea
> - **Quiero:** Registrar y mantener los aeropuertos en los que opera la aerolínea
> - **De forma que:** Pueda seleccionarlos como origen y destino al definir los vuelos, evitando errores de carga
>
> **Story points:** 2 — **Business value:** 5

#### Creación de vuelos

> **User story 7:**
> - **Como:** Administrador de la aerolínea
> - **Quiero:** Crear un vuelo indicando días de la semana en que opera, horario de partida y de llegada, aeropuerto de origen y destino, período del año en que estará disponible para la venta, capacidad en Economy y Primera Clase y precio por clase
> - **De forma que:** La oferta de vuelos quede registrada y disponible para ser vendida
>
> **Story points:** 8 — **Business value:** 13

#### Modificación de vuelos

> **User story 8:**
> - **Como:** Administrador de la aerolínea
> - **Quiero:** Modificar los datos de un vuelo existente (horarios, días de operación, período, capacidad y precios)
> - **De forma que:** La oferta se adapte a cambios operativos o comerciales sin perder el historial de la información
>
> **Story points:** 5 — **Business value:** 8

#### Cancelación de vuelos

> **User story 9:**
> - **Como:** Administrador de la aerolínea
> - **Quiero:** Cancelar un vuelo completo o una salida puntual en una fecha determinada
> - **De forma que:** Deje de ofrecerse a la venta y quede registrada la cancelación para informar a los pasajeros afectados
>
> **Story points:** 3 — **Business value:** 8

#### Listado y consulta de vuelos

> **User story 10:**
> - **Como:** Administrador de la aerolínea
> - **Quiero:** Visualizar el listado de vuelos y consultar el detalle de cada uno con sus salidas
> - **De forma que:** Pueda supervisar la oferta de vuelos de manera centralizada y acceder rápidamente a su gestión
>
> **Story points:** 3 — **Business value:** 5

###  3 — Búsqueda y compra de pasajes

#### Búsqueda de vuelos

> **User story 11:**
> - **Como:** Pasajero
> - **Quiero:** Buscar vuelos indicando aeropuerto de origen, destino y fecha de viaje
> - **De forma que:** El sistema me muestre las opciones disponibles según fechas y horarios para planificar mi viaje
>
> **Story points:** 8 — **Business value:** 13

#### Filtrado y ordenamiento de resultados

> **User story 12:**
> - **Como:** Pasajero
> - **Quiero:** Filtrar los resultados de búsqueda por clase, franja horaria y precio, y ordenarlos
> - **De forma que:** Encuentre rápidamente la opción que mejor se ajusta a mis necesidades
>
> **Story points:** 3 — **Business value:** 5

#### Selección de vuelo, clase y cantidad de pasajes

> **User story 13:**
> - **Como:** Pasajero
> - **Quiero:** Seleccionar una salida de los resultados, la clase (Economy o Primera) y la cantidad de pasajes, hasta un máximo de 9 por transacción
> - **De forma que:** Pueda armar mi compra conociendo el precio total antes de pagar
>
> **Story points:** 3 — **Business value:** 8

#### Carga de datos de los pasajeros

> **User story 14:**
> - **Como:** Pasajero
> - **Quiero:** Ingresar los datos personales de cada pasajero incluido en la compra
> - **De forma que:** Cada pasaje electrónico se emita a nombre de la persona que viaja
>
> **Story points:** 5 — **Business value:** 8

#### Reserva temporal de asientos

> **User story 15:**
> - **Como:** Pasajero
> - **Quiero:** Que los asientos que seleccioné queden reservados durante un tiempo limitado mientras completo la compra
> - **De forma que:** No pierda mi lugar y nunca se vendan más pasajes que la capacidad del avión, aun con compras simultáneas
>
> **Story points:** 8 — **Business value:** 13

#### Consulta de mis compras

> **User story 16:**
> - **Como:** Pasajero
> - **Quiero:** Consultar desde la web el historial de mis compras y el estado de mis pasajes
> - **De forma que:** Tenga centralizada la información de mis viajes y pueda volver a descargar mi documentación
>
> **Story points:** 3 — **Business value:** 5

###  4 — Pagos y documentación del viaje

#### Pago y registro de la transacción

> **User story 17:**
> - **Como:** Pasajero
> - **Quiero:** Ingresar la información de pago de mi compra a través de un medio seguro
> - **De forma que:** La transacción quede registrada y mis pasajes queden emitidos
>
> **Story points:** 8 — **Business value:** 13

#### Manejo de pagos rechazados

> **User story 18:**
> - **Como:** Pasajero
> - **Quiero:** Ser informado claramente si mi pago es rechazado o falla, y poder reintentarlo sin volver a cargar mi compra
> - **De forma que:** Un problema con el medio de pago no me haga perder los pasajes que había seleccionado
>
> **Story points:** 5 — **Business value:** 8

#### Envío de pasajes electrónicos y factura

> **User story 19:**
> - **Como:** Pasajero
> - **Quiero:** Recibir automáticamente por email los pasajes electrónicos y la factura una vez confirmado el pago
> - **De forma que:** Disponga de la documentación de mi viaje sin trámites adicionales
>
> **Story points:** 8 — **Business value:** 13

###  5 — Control de ocupación

#### Reportes de ocupación

> **User story 20:**
> - **Como:** Administrador de la aerolínea
> - **Quiero:** Consultar reportes de ocupación por vuelo, clase y fecha
> - **De forma que:** Pueda evaluar el rendimiento de cada ruta y tomar decisiones sobre capacidad, precios y frecuencias
>
> **Story points:** 8 — **Business value:** 8

#### Exportación de reportes

> **User story 21:**
> - **Como:** Administrador de la aerolínea
> - **Quiero:** Exportar los reportes de ocupación en formato PDF y CSV
> - **De forma que:** La información pueda compartirse o analizarse fuera de la plataforma
>
> **Story points:** 3 — **Business value:** 3

###  6 — Notificaciones

#### Alertas por cambios de horario y cancelaciones

> **User story 22:**
> - **Como:** Pasajero
> - **Quiero:** Recibir un email cuando cambie el horario de un vuelo para el que compré pasajes o cuando sea cancelado
> - **De forma que:** Me entere a tiempo y pueda reorganizar mi viaje
>
> **Story points:** 5 — **Business value:** 8

###  7 — Atención en mostrador

#### Consulta de vuelos y disponibilidad en mostrador

> **User story 23:**
> - **Como:** Empleado de mostrador
> - **Quiero:** Consultar vuelos, horarios y asientos disponibles por clase en tiempo real
> - **De forma que:** Pueda informar con precisión a los pasajeros que se acercan al mostrador
>
> **Story points:** 3 — **Business value:** 5

#### Venta de pasajes en mostrador

> **User story 24:**
> - **Como:** Empleado de mostrador
> - **Quiero:** Vender pasajes a un pasajero en el mostrador, cargando sus datos y registrando el pago
> - **De forma que:** Los pasajeros que no compran por internet también puedan adquirir sus pasajes
>
> **Story points:** 5 — **Business value:** 8

#### Búsqueda de pasajes y reenvío de documentación

> **User story 25:**
> - **Como:** Empleado de mostrador
> - **Quiero:** Buscar los pasajes de un pasajero por documento o código de reserva y reenviarle su pasaje electrónico
> - **De forma que:** Pueda resolver en el momento las consultas y problemas de documentación en el aeropuerto
>
> **Story points:** 3 — **Business value:** 5

###  8 — Aplicación móvil para pasajeros

#### Búsqueda de vuelos desde la app

> **User story 26:**
> - **Como:** Pasajero
> - **Quiero:** Buscar vuelos por origen, destino y fecha desde la aplicación móvil
> - **De forma que:** Pueda consultar opciones de viaje desde cualquier lugar
>
> **Story points:** 5 — **Business value:** 8

#### Compra de pasajes desde la app

> **User story 27:**
> - **Como:** Pasajero
> - **Quiero:** Iniciar sesión y comprar pasajes (selección, datos de pasajeros y pago) desde la aplicación móvil
> - **De forma que:** Pueda concretar mi compra desde el teléfono sin necesidad de una computadora
>
> **Story points:** 8 — **Business value:** 8

#### Notificaciones push

> **User story 28:**
> - **Como:** Pasajero
> - **Quiero:** Recibir notificaciones en mi teléfono sobre cambios de horario, cancelaciones y confirmación de mis compras
> - **De forma que:** Esté al tanto de las novedades de mis vuelos sin tener que abrir la aplicación
>
> **Story points:** 5 — **Business value:** 5

#### Descarga de tickets electrónicos desde la app

> **User story 29:**
> - **Como:** Pasajero
> - **Quiero:** Visualizar y descargar mis tickets electrónicos desde la aplicación móvil
> - **De forma que:** Tenga siempre disponible la documentación de mis vuelos en mi teléfono
>
> **Story points:** 3 — **Business value:** 8

---

## 1.3. Resumen del Product Backlog

| ID | User Story | SP | BV | BV/SP | Sprint |
|----|------------|---:|---:|------:|:------:|
| US-01 | Preparación de la infraestructura del proyecto | 5 | 8 | 1,60 | 1 |
| US-02 | Diseño e implementación del modelo de datos | 8 | 8 | 1,00 | 1 |
| US-03 | Inicio de sesión y control de acceso por rol | 5 | 13 | 2,60 | 1 |
| US-04 | Registro de pasajeros | 3 | 8 | 2,67 | 2 |
| US-05 | Gestión de cuentas de empleados | 3 | 5 | 1,67 | 3 |
| US-06 | Gestión de aeropuertos | 2 | 5 | 2,50 | 1 |
| US-07 | Creación de vuelos | 8 | 13 | 1,63 | 1 |
| US-08 | Modificación de vuelos | 5 | 8 | 1,60 | 1 |
| US-09 | Cancelación de vuelos | 3 | 8 | 2,67 | 1 |
| US-10 | Listado y consulta de vuelos | 3 | 5 | 1,67 | 1 |
| US-11 | Búsqueda de vuelos | 8 | 13 | 1,63 | 2 |
| US-12 | Filtrado y ordenamiento de resultados | 3 | 5 | 1,67 | 3 |
| US-13 | Selección de vuelo, clase y cantidad de pasajes | 3 | 8 | 2,67 | 2 |
| US-14 | Carga de datos de los pasajeros | 5 | 8 | 1,60 | 2 |
| US-15 | Reserva temporal de asientos | 8 | 13 | 1,63 | 2 |
| US-16 | Consulta de mis compras | 3 | 5 | 1,67 | 3 |
| US-17 | Pago y registro de la transacción | 8 | 13 | 1,63 | 2 |
| US-18 | Manejo de pagos rechazados | 5 | 8 | 1,60 | 3 |
| US-19 | Envío de pasajes electrónicos y factura | 8 | 13 | 1,63 | 3 |
| US-20 | Reportes de ocupación | 8 | 8 | 1,00 | 3 |
| US-21 | Exportación de reportes | 3 | 3 | 1,00 | 4 |
| US-22 | Alertas por cambios de horario y cancelaciones | 5 | 8 | 1,60 | 3 |
| US-23 | Consulta de vuelos y disponibilidad en mostrador | 3 | 5 | 1,67 | 4 |
| US-24 | Venta de pasajes en mostrador | 5 | 8 | 1,60 | 4 |
| US-25 | Búsqueda de pasajes y reenvío de documentación | 3 | 5 | 1,67 | 4 |
| US-26 | App: búsqueda de vuelos | 5 | 8 | 1,60 | 4 |
| US-27 | App: compra de pasajes | 8 | 8 | 1,00 | 4 |
| US-28 | App: notificaciones push | 5 | 5 | 1,00 | 4 |
| US-29 | App: descarga de tickets electrónicos | 3 | 8 | 2,67 | 4 |
| **TOTAL** | **29 User Stories** | **144** | **233** | — | — |

---

## 1.4. Planificación del proyecto en sprints


### Criterios utilizados

1. **Dependencias técnicas y funcionales.** Una story solo se planifica cuando las stories de las que depende ya fueron asignadas a un sprint anterior o al mismo. Las principales dependencias son:

| User Story | Depende de |
|------------|-----------|
| Todas | US-01 (infraestructura), US-02 (modelo de datos) |
| Funcionalidades con acceso restringido | US-03 (inicio de sesión y roles) |
| US-07 Creación de vuelos | US-06 (aeropuertos) |
| US-08, US-09, US-10, US-11 | US-07 (debe haber vuelos cargados) |
| US-13 → US-14 → US-15 → US-17 | Flujo de compra: búsqueda (US-11) y registro de pasajeros (US-04) |
| US-18, US-19, US-16 | US-17 (debe existir una compra pagada) |
| US-22 Alertas por email | US-08, US-09 (cambios y cancelaciones) y US-17 (pasajeros con pasajes) |
| US-20 → US-21 | Ventas registradas (US-17) |
| US-23, US-24, US-25 | US-05 (cuentas de empleados) y flujo de compra/pago (US-11 a US-19) |
| US-26 a US-29 (App) | Servicios de búsqueda, compra, notificaciones y pasajes ya construidos para la web |

2. **Relación valor/esfuerzo (BV/SP).** Entre las stories cuyas dependencias están resueltas, se priorizan las de mayor BV/SP (por ejemplo, US-03, US-06 y US-09 en el Sprint #1, y US-04 y US-13 en el Sprint #2).

3. **Velocidad del equipo (*velocity*).** Como todavía no hay datos históricos, se toma una velocidad inicial de **35 a 40 SP por sprint**, que se deriva de la capacidad en horas del equipo (ver Parte 2). Al cerrar el Sprint #1 se compararán las horas estimadas con las reales de cada US y, con esa información, se recalibrará la estimación del Sprint #2.

---

# Parte 2 — Definición del Sprint #1

## 2.1. Sprint Backlog

**Objetivo del sprint:** *al finalizar el Sprint #1, un administrador puede iniciar sesión en la plataforma web y gestionar la oferta de vuelos de la aerolínea: registrar aeropuertos y crear, modificar, cancelar y consultar vuelos con sus salidas.*

En esta sección se identifican los *user stories* seleccionados para esta iteración y, para cada uno, su división en tareas estimadas en horas y sus criterios de aceptación.

---

### Preparación de la infraestructura del proyecto (US-01)

> - **Como:** Miembro del equipo de desarrollo
> - **Quiero:** Preparar la infraestructura del proyecto (repositorio, entorno de desarrollo, integración continua y entorno de demostración)
> - **De forma que:** El equipo cuente con una base técnica común y verificable para trabajar de manera ágil durante todos los sprints

**Tareas:**

- Seleccionar y justificar el stack tecnológico (frontend web, backend, base de datos y app móvil): 6 horas
- Inicializar el repositorio con estructura de carpetas, rama principal protegida y guía de contribución: 4 horas
- Configurar el entorno de desarrollo (linter, formateador y convenciones de código): 4 horas
- Configurar el pipeline de integración continua (compilación y pruebas automáticas en cada *pull request*): 8 horas
- Preparar la base de datos local y el entorno de demostración donde se despliega el incremento: 6 horas
- Redactar la guía de instalación y puesta en marcha (README): 2 horas

**Total:** 30 horas

**Criterios de aceptación:**

1. La rama principal del repositorio está protegida: solo admite cambios mediante *pull request* aprobado por al menos otro integrante.
2. Un integrante puede clonar el proyecto y ejecutarlo en un equipo limpio siguiendo únicamente el README.
3. El pipeline de integración continua se ejecuta automáticamente en cada *pull request* (compilación y pruebas) y bloquea la integración si falla.
4. El stack tecnológico elegido está documentado junto con la justificación de cada elección.
5. Existe un entorno de demostración accesible por ambas comisiones donde está desplegada la última versión de la rama principal.

---

### Diseño e implementación del modelo de datos (US-02)

> - **Como:** Miembro del equipo de desarrollo
> - **Quiero:** Diseñar e implementar el modelo de datos del sistema (aeropuertos, vuelos, salidas, clases, tarifas, usuarios, pasajeros, compras, pasajes y pagos)
> - **De forma que:** Todas las funcionalidades se apoyen sobre una estructura de datos consistente y extensible

**Tareas:**

- Relevar los requerimientos de información a partir del enunciado y de los supuestos del análisis: 6 horas
- Elaborar el modelo conceptual (entidades, atributos y relaciones del dominio): 10 horas
- Elaborar el modelo lógico (tablas, claves primarias y foráneas, tipos de datos, normalización): 12 horas
- Elaborar el modelo físico (índices, restricciones de integridad) y los scripts de creación y migración: 12 horas
- Preparar el script de datos de prueba (aeropuertos, administrador inicial, vuelos, salidas y pasajes vendidos de ejemplo): 6 horas
- Validar el modelo junto a la comisión de Análisis y Management: 4 horas
- Documentar el modelo (diagrama entidad-relación y diccionario de datos): 6 horas

**Total:** 56 horas

**Criterios de aceptación:**

1. El modelo representa todas las entidades del dominio: aeropuertos, vuelos (días de operación, horarios, ruta y período de disponibilidad), salidas, capacidad y precio por clase, usuarios y roles, pasajeros, compras, pasajes, pagos y facturas.
2. El modelo distingue el *vuelo* (programación) de la *salida* (operación en una fecha), de forma que la disponibilidad y la ocupación puedan calcularse por vuelo, clase y fecha.
3. El modelo representa los estados de un vuelo (activo, cancelado), de una salida (programada, cancelada) y de una compra (reservada, confirmada, vencida, rechazada).
4. Los scripts permiten recrear el esquema completo desde cero y cargar los datos de prueba con un único comando.
5. El diagrama entidad-relación y el diccionario de datos están documentados y validados por la comisión de Análisis y Management, que deja constancia de la validación.

---

### Inicio de sesión y control de acceso por rol (US-03)

> - **Como:** Usuario del sistema (administrador, empleado de mostrador o pasajero)
> - **Quiero:** Iniciar sesión con mis credenciales y acceder únicamente a la interfaz y a las funciones de mi rol
> - **De forma que:** Las operaciones críticas de la aerolínea queden protegidas y cada usuario tenga una experiencia acorde a su perfil

**Tareas:**

- Implementar el inicio y cierre de sesión con emisión y validación del token de sesión: 8 horas
- Implementar el almacenamiento seguro de contraseñas (hash con sal) y la creación de la cuenta de administrador inicial: 3 horas
- Implementar el control de autorización por rol en el backend: 8 horas
- Implementar las rutas protegidas y los menús condicionados por rol en el frontend: 6 horas
- Testear los flujos de autenticación y autorización: 4 horas

**Total:** 29 horas

**Criterios de aceptación:**

1. Un usuario registrado puede iniciar sesión con email y contraseña. Si alguno de los dos datos es incorrecto, se muestra un mensaje genérico que no indica cuál falló.
2. Las contraseñas se almacenan con hash y sal; en ningún caso se guardan en texto plano.
3. Existen los roles administrador, empleado de mostrador y pasajero, y cada usuario solo ve el menú y las pantallas de su rol.
4. El backend rechaza las peticiones sin sesión válida (código 401) y las que no corresponden al rol del usuario (código 403).
5. El usuario puede cerrar sesión, y la sesión expira automáticamente tras 30 minutos de inactividad.
6. Las pruebas cubren como mínimo: inicio de sesión correcto, inicio de sesión incorrecto, acceso permitido y acceso denegado por rol.

---

### Gestión de aeropuertos (US-06)

> - **Como:** Administrador de la aerolínea
> - **Quiero:** Registrar y mantener los aeropuertos en los que opera la aerolínea
> - **De forma que:** Pueda seleccionarlos como origen y destino al definir los vuelos, evitando errores de carga

**Tareas:**

- Implementar los servicios de alta, modificación, baja lógica y listado de aeropuertos: 5 horas
- Implementar la pantalla de gestión de aeropuertos en la interfaz del administrador: 5 horas
- Testear la gestión de aeropuertos: 2 horas

**Total:** 12 horas

**Criterios de aceptación:**

1. El administrador puede dar de alta un aeropuerto indicando código IATA (3 letras, único), nombre, ciudad y provincia.
2. El sistema rechaza un código IATA repetido o con formato inválido e informa el error.
3. El administrador puede modificar los datos de un aeropuerto y desactivarlo. No se permite desactivar un aeropuerto que sea origen o destino de un vuelo activo.
4. Los aeropuertos desactivados no se ofrecen al crear o modificar vuelos.
5. Solo los usuarios con rol administrador acceden a esta funcionalidad.

---

### Creación de vuelos (US-07)

> - **Como:** Administrador de la aerolínea
> - **Quiero:** Crear un vuelo indicando días de la semana en que opera, horario de partida y de llegada, aeropuerto de origen y destino, período del año en que estará disponible para la venta, capacidad en Economy y Primera Clase y precio por clase
> - **De forma que:** La oferta de vuelos quede registrada y disponible para ser vendida

**Tareas:**

- Diseñar el prototipo del formulario de alta de vuelo y validarlo con la comisión de Análisis y Management: 6 horas
- Implementar el servicio de alta de vuelo con persistencia en la base de datos: 12 horas
- Implementar la generación de las salidas del vuelo a partir de sus días de operación y su período de disponibilidad: 8 horas
- Implementar las validaciones de negocio: 8 horas
- Implementar la pantalla de creación de vuelo en la interfaz del administrador: 10 horas
- Testear el flujo de creación (casos válidos y de error): 6 horas

**Total:** 50 horas

**Criterios de aceptación:**

1. El administrador puede crear un vuelo con: número de vuelo (único), días de la semana en que opera (selección múltiple), hora de partida, hora de llegada, aeropuerto de origen y de destino (elegidos entre los registrados), período de disponibilidad (fecha desde y hasta), cantidad de asientos en Economy y en Primera Clase y precio del pasaje en cada clase.
2. El sistema valida antes de guardar que todos los campos obligatorios estén completos, que el origen sea distinto del destino, que haya al menos un día de operación, que la fecha hasta no sea anterior a la fecha desde ni la fecha desde anterior al día actual, que la capacidad total sea mayor a 0 y que cada clase con asientos tenga un precio mayor a 0.
3. Si la hora de llegada es menor o igual a la de partida, el sistema interpreta que el vuelo llega al día siguiente y lo indica con "+1".
4. Ante un dato inválido, el vuelo no se guarda y el sistema señala el campo con error y el motivo.
5. Al guardar, el vuelo queda en estado *Activo* y se generan sus salidas. Por ejemplo, un vuelo que opera lunes y viernes con período del 01/11/2026 al 30/11/2026 genera 9 salidas.
6. Solo los usuarios con rol administrador acceden a esta funcionalidad.

---

### Modificación de vuelos (US-08)

> - **Como:** Administrador de la aerolínea
> - **Quiero:** Modificar los datos de un vuelo existente (horarios, días de operación, período, capacidad y precios)
> - **De forma que:** La oferta se adapte a cambios operativos o comerciales sin perder el historial de la información

**Tareas:**

- Implementar el servicio de modificación de vuelos, incluyendo el control de capacidad contra pasajes vendidos y el recálculo de salidas futuras: 10 horas
- Implementar el registro del historial de cambios del vuelo: 5 horas
- Implementar la pantalla de edición de vuelo en la interfaz del administrador: 8 horas
- Testear el flujo de modificación (incluye los rechazos por capacidad y la advertencia por salidas con ventas): 6 horas

**Total:** 29 horas

**Criterios de aceptación:**

1. El administrador puede editar todos los datos de un vuelo activo excepto su número, y el cambio se guarda recién después de una confirmación explícita.
2. Se aplican las mismas validaciones que en la creación del vuelo.
3. Los cambios afectan solo a las salidas futuras; las salidas ya realizadas no se modifican.
4. El sistema impide reducir la capacidad de una clase por debajo de los pasajes ya vendidos en alguna salida futura e indica la salida en conflicto (verificable con los datos de prueba).
5. Si el cambio de días de operación o de período deja sin efecto salidas que tienen pasajes vendidos, el sistema lo advierte y pide confirmación; al confirmar, esas salidas pasan a estado *Cancelada*.
6. Cada modificación queda registrada en el historial con fecha, hora, usuario responsable, valor anterior y valor nuevo, y el historial puede consultarse desde el detalle del vuelo.

---

### Cancelación de vuelos (US-09)

> - **Como:** Administrador de la aerolínea
> - **Quiero:** Cancelar un vuelo completo o una salida puntual en una fecha determinada
> - **De forma que:** Deje de ofrecerse a la venta y quede registrada la cancelación para informar a los pasajeros afectados

**Tareas:**

- Implementar el servicio de cancelación de un vuelo completo (todas sus salidas futuras) o de una salida puntual, con el cambio de estado correspondiente: 8 horas
- Implementar la confirmación con advertencia, que informa la cantidad de pasajes vendidos afectados: 5 horas
- Incorporar la acción de cancelar en el listado y el detalle del vuelo: 4 horas
- Testear el flujo de cancelación (con y sin pasajes vendidos, vuelo completo y salida puntual): 4 horas

**Total:** 21 horas

**Criterios de aceptación:**

1. El administrador puede cancelar un vuelo completo o una única salida futura, previa confirmación explícita.
2. El mensaje de confirmación informa cuántos pasajes vendidos se ven afectados por la cancelación.
3. Tras la cancelación, el vuelo o la salida se muestran con estado *Cancelado* en el listado y en el detalle, y no admiten modificaciones posteriores.
4. La cancelación no elimina registros: se conservan los datos del vuelo, la fecha y hora de cancelación y el usuario responsable.
5. No es posible cancelar salidas cuya fecha ya pasó.
6. Solo los usuarios con rol administrador acceden a esta funcionalidad.

---

### Listado y consulta de vuelos (US-10)

> - **Como:** Administrador de la aerolínea
> - **Quiero:** Visualizar el listado de vuelos y consultar el detalle de cada uno con sus salidas
> - **De forma que:** Pueda supervisar la oferta de vuelos de manera centralizada y acceder rápidamente a su gestión

**Tareas:**

- Implementar el servicio de listado de vuelos con paginación, filtros y ordenamiento: 8 horas
- Implementar la vista de listado en la interfaz del administrador: 7 horas
- Implementar la vista de detalle del vuelo (datos, salidas e historial) con sus acciones: 5 horas
- Testear el listado, los filtros y el tiempo de respuesta con un volumen de datos de prueba: 3 horas

**Total:** 23 horas

**Criterios de aceptación:**

1. El listado muestra, paginado de a 20 registros, el número de vuelo, origen, destino, horario de partida y llegada, días de operación, período de disponibilidad y estado.
2. El listado se puede filtrar por estado, aeropuerto de origen y aeropuerto de destino, y ordenar por número de vuelo, ruta u horario de partida.
3. El detalle del vuelo muestra todos sus datos (incluidas capacidades y precios por clase), sus salidas con asientos vendidos y disponibles por clase, y su historial de cambios.
4. Desde el detalle se accede a las acciones *Modificar* y *Cancelar*, disponibles solo si el vuelo está activo.
5. Con al menos 100 vuelos cargados, el listado responde en menos de 2 segundos.

---

## 2.2. Resumen del Sprint #1

| User Story | SP | BV | Horas estimadas |
|------------|---:|---:|----------------:|
| US-01: Preparación de la infraestructura del proyecto | 5 | 8 | 30 |
| US-02: Diseño e implementación del modelo de datos | 8 | 8 | 56 |
| US-03: Inicio de sesión y control de acceso por rol | 5 | 13 | 29 |
| US-06: Gestión de aeropuertos | 2 | 5 | 12 |
| US-07: Creación de vuelos | 8 | 13 | 50 |
| US-08: Modificación de vuelos | 5 | 8 | 29 |
| US-09: Cancelación de vuelos | 3 | 8 | 21 |
| US-10: Listado y consulta de vuelos | 3 | 5 | 23 |
| **TOTAL SPRINT #1** | **39** | **68** | **250** |


## 2.3. Definición de Terminado (*Definition of Done*)

Una User Story del Sprint #1 se considera terminada cuando:

1. Todas sus tareas están completas y su código está integrado en la rama principal mediante un *pull request* revisado por otro integrante.
2. El pipeline de integración continua finaliza exitosamente (compilación y pruebas automatizadas).
3. La comisión de Análisis y Management verificó que se cumplen **todos** sus criterios de aceptación.
4. El incremento está desplegado en el entorno de demostración y puede mostrarse en la demo del 06/10.
5. La documentación asociada (README, modelo de datos, decisiones técnicas) está actualizada.

---