# Sprint 0 — Planificación del Proyecto y Product Backlog

**Proyecto:** SIGVA — Sistema Integral de Gestión de Vuelos y Venta de Pasajes (Aerolínea Nacional)
**Enunciado:** N.º 2 — Sistema de gestión de vuelos y venta de pasajes para una aerolínea nacional
**Rol de la comisión:** Análisis y Management
**Alcance:** Web (administradores, empleados de mostrador, pasajeros) + App móvil (pasajeros)

---

## PARTE 1: PLANIFICACIÓN DEL PROYECTO Y PRODUCT BACKLOG

### 1.1. Lista del Product Backlog

A continuación se presentan las User Stories (US) que componen el Product Backlog, cubriendo el alcance global del sistema. Para cada una se define su título, su definición formal mediante el formato *Como / Quiero / De forma que*, su estimación relativa en Story Points (SP) y el Business Value (BV) otorgado, en representación de los stakeholders de la aerolínea.

La escala de Story Points utilizada es la secuencia de Fibonacci (1, 2, 3, 5, 8, 13), donde 1 representa el menor esfuerzo relativo y 13 el mayor. El Business Value se valora en la escala (3, 5, 8, 13), priorizando el impacto comercial y estratégico de cada funcionalidad para la aerolínea.

---

#### Categoría A: Infraestructura y plataforma técnica

##### US-01: Preparación de la infraestructura del proyecto

- **Como:** Miembro del equipo de desarrollo
- **Quiero:** Preparar la infraestructura del proyecto (repositorio, entorno de desarrollo, pipeline de integración continua y configuración de herramientas)
- **De forma que:** El equipo disponga de una base técnica sólida, repetible y verificable para trabajar de manera ágil durante todos los sprints
- **Story Points:** 5
- **Business Value:** 8

##### US-02: Diseño del modelo de datos

- **Como:** Miembro del equipo de desarrollo
- **Quiero:** Diseñar el modelo de datos del sistema que contemple vuelos, rutas, aeropuertos, clases, pasajes, compras y pagos
- **De forma que:** Todas las funcionalidades del sistema se apoyen sobre una estructura de datos consistente, normalizada y extensible
- **Story Points:** 8
- **Business Value:** 8

##### US-03: Autenticación y control de roles

- **Como:** Usuario (administrador, empleado de mostrador o pasajero)
- **Quiero:** Registrarme e iniciar sesión de forma segura, accediendo únicamente a las funcionalidades habilitadas para mi rol
- **De forma que:** La información y las operaciones críticas del sistema estén protegidas y cada tipo de usuario cuente con una experiencia acorde a su perfil
- **Story Points:** 5
- **Business Value:** 13

---

#### Categoría B: Gestión de vuelos (Administradores)

##### US-04: Creación de un vuelo

- **Como:** Administrador de la aerolínea
- **Quiero:** Crear un vuelo indicando días de operación, horarios de partida y llegada, aeropuerto de origen y destino, período de venta del año, capacidad por clase y precios
- **De forma que:** La oferta de vuelos quede registrada en el sistema y disponible para la venta conforme a la política comercial definida
- **Story Points:** 8
- **Business Value:** 13

##### US-05: Modificación de un vuelo

- **Como:** Administrador de la aerolínea
- **Quiero:** Modificar los datos de un vuelo existente (horarios, ruta, período de venta, capacidad, precios)
- **De forma que:** La oferta de vuelos se pueda ajustar ante cambios operativos o comerciales de la aerolínea, manteniendo el historial de la información
- **Story Points:** 5
- **Business Value:** 8

##### US-06: Cancelación de un vuelo

- **Como:** Administrador de la aerolínea
- **Quiero:** Cancelar un vuelo programado
- **De forma que:** El vuelo deje de ofrecerse a la venta y los pasajeros afectados puedan ser notificados oportunamente
- **Story Points:** 3
- **Business Value:** 8

##### US-07: Listado y consulta de vuelos (vista administrador)

- **Como:** Administrador de la aerolínea
- **Quiero:** Visualizar el listado de todos los vuelos con sus datos principales y consultar el detalle de cada uno
- **De forma que:** Pueda supervisar la oferta de vuelos de manera rápida y centralizada
- **Story Points:** 3
- **Business Value:** 5

---

#### Categoría C: Búsqueda de vuelos (Pasajeros)

##### US-08: Búsqueda de vuelos

- **Como:** Pasajero
- **Quiero:** Buscar vuelos indicando aeropuerto de origen, destino y fecha
- **De forma que:** El sistema me muestre las opciones disponibles según fecha y horario para planificar mi viaje
- **Story Points:** 8
- **Business Value:** 13

##### US-09: Filtrado y ordenamiento de resultados de búsqueda

- **Como:** Pasajero
- **Quiero:** Aplicar filtros (clase, rango horario, precio) y ordenar los resultados de la búsqueda
- **De forma que:** Pueda refinar rápidamente las opciones y elegir el vuelo que mejor se ajuste a mis necesidades
- **Story Points:** 5
- **Business Value:** 8

---

#### Categoría D: Compra de pasajes (Pasajeros)

##### US-10: Selección de vuelo, clase y cantidad de pasajes

- **Como:** Pasajero
- **Quiero:** Seleccionar un vuelo disponible, la clase (Economy o Primera) y la cantidad de pasajes (hasta 9 por transacción)
- **De forma que:** Pueda armar mi compra antes de completar el pago
- **Story Points:** 3
- **Business Value:** 5

##### US-11: Registro de los datos de los pasajeros

- **Como:** Pasajero
- **Quiero:** Ingresar los datos personales de cada pasajero incluido en la compra
- **De forma que:** Los pasajes emitidos correspondan correctamente a cada pasajero y sean válidos para el viaje
- **Story Points:** 5
- **Business Value:** 8

##### US-12: Confirmación de la compra de pasajes

- **Como:** Pasajero
- **Quiero:** Confirmar la compra de los pasajes seleccionados y obtener el detalle de la transacción
- **De forma que:** Mi compra quede registrada y pueda avanzar al pago de manera segura
- **Story Points:** 8
- **Business Value:** 13

##### US-13: Reserva temporal de cupos con control de concurrencia

- **Como:** Pasajero
- **Quiero:** Que el sistema reserve temporalmente los cupos de mi selección mientras completo el pago
- **De forma que:** Se evite la sobreventa de asientos aun cuando otros pasajeros estén comprando el mismo vuelo de forma simultánea
- **Story Points:** 8
- **Business Value:** 13

---

#### Categoría E: Pagos

##### US-14: Procesamiento de pagos

- **Como:** Pasajero
- **Quiero:** Realizar el pago de mi compra ingresando los datos de mi medio de pago a través de una pasarela segura
- **De forma que:** La transacción se registre correctamente y mi compra quede confirmada
- **Story Points:** 8
- **Business Value:** 13

##### US-15: Manejo de errores y reintentos de pago

- **Como:** Pasajero
- **Quiero:** Que el sistema maneje de forma correcta los fallos de la pasarela de pagos y me permita reintentar sin perder mi selección
- **De forma que:** Ante una falla transitoria mi compra no se pierda y pueda concretarse sin inconvenientes
- **Story Points:** 5
- **Business Value:** 8

---

#### Categoría F: Emails y notificaciones

##### US-16: Envío automático de pasaje electrónico y factura

- **Como:** Pasajero
- **Quiero:** Recibir por email el pasaje electrónico y la factura de mi compra automáticamente tras la confirmación del pago
- **De forma que:** Disponga de la documentación de mi viaje sin trámites adicionales
- **Story Points:** 8
- **Business Value:** 13

##### US-17: Notificación de cambios de horario y cancelaciones

- **Como:** Pasajero
- **Quiero:** Ser notificado por email cuando un vuelo que tengo comprado sufra un cambio de horario o sea cancelado
- **De forma que:** Esté informado oportunamente y pueda reorganizar mis planes
- **Story Points:** 5
- **Business Value:** 8

##### US-18: Gestión de preferencias de notificación

- **Como:** Pasajero
- **Quiero:** Configurar mis preferencias de notificación (email, app) en mi perfil
- **De forma que:** Reciba únicamente la información que me interesa y por el canal que prefiero
- **Story Points:** 2
- **Business Value:** 3

---

#### Categoría G: Control de ocupación y reportes (Administradores)

##### US-19: Consulta de reportes de ocupación

- **Como:** Administrador de la aerolínea
- **Quiero:** Consultar reportes de ocupación por vuelo, clase y fecha
- **De forma que:** Pueda monitorear la venta de pasajes y tomar decisiones comerciales u operativas fundamentadas
- **Story Points:** 8
- **Business Value:** 8

##### US-20: Exportación de reportes de ocupación

- **Como:** Administrador de la aerolínea
- **Quiero:** Exportar los reportes de ocupación en formatos estándar (PDF/CSV)
- **De forma que:** La información pueda ser compartida o analizada fuera de la plataforma
- **Story Points:** 3
- **Business Value:** 5

---

#### Categoría H: Empleados de mostrador

##### US-21: Consulta de vuelos y disponibilidad (mostrador)

- **Como:** Empleado de mostrador
- **Quiero:** Consultar vuelos, horarios y disponibilidad de asientos en tiempo real
- **De forma que:** Poda atender a los pasajeros que se presentan en el aeropuerto con información actualizada
- **Story Points:** 3
- **Business Value:** 5

##### US-22: Atención al pasajero y venta en mostrador

- **Como:** Empleado de mostrador
- **Quiero:** Vender pasajes, emitir pasajes electrónicos y gestionar los datos de los pasajeros desde el módulo de mostrador
- **De forma que:** Los pasajeros puedan concretar sus viajes incluso sin reserva previa, con la misma calidad que la venta remota
- **Story Points:** 8
- **Business Value:** 8

---

#### Categoría I: Aplicación móvil (Pasajeros)

##### US-23: Búsqueda y compra de pasajes desde la App móvil

- **Como:** Pasajero
- **Quiero:** Buscar vuelos y comprar pasajes desde la aplicación móvil con una experiencia adaptada al dispositivo
- **De forma que:** Pueda gestionar mis viajes desde cualquier lugar, de forma simple e inmediata
- **Story Points:** 13
- **Business Value:** 8

##### US-24: Notificaciones push en la App móvil

- **Como:** Pasajero
- **Quiero:** Recibir notificaciones push en mi teléfono sobre cambios de horario, cancelaciones y el estado de mis compras
- **De forma que:** Esté al tanto de novedades de mis vuelos sin necesidad de abrir la aplicación
- **Story Points:** 5
- **Business Value:** 5

##### US-25: Visualización y descarga de tickets desde la App móvil

- **Como:** Pasajero
- **Quiero:** Visualizar y descargar mis pasajes electrónicos desde la aplicación móvil
- **De forma que:** Tenga siempre disponible la documentación de mis vuelos en mi dispositivo
- **Story Points:** 5
- **Business Value:** 8

---

#### Resumen del Product Backlog

| ID | User Story | SP | BV |
|----|------------|----|----|
| US-01 | Preparación de la infraestructura del proyecto | 5 | 8 |
| US-02 | Diseño del modelo de datos | 8 | 8 |
| US-03 | Autenticación y control de roles | 5 | 13 |
| US-04 | Creación de un vuelo | 8 | 13 |
| US-05 | Modificación de un vuelo | 5 | 8 |
| US-06 | Cancelación de un vuelo | 3 | 8 |
| US-07 | Listado y consulta de vuelos (admin) | 3 | 5 |
| US-08 | Búsqueda de vuelos | 8 | 13 |
| US-09 | Filtrado y ordenamiento de resultados | 5 | 8 |
| US-10 | Selección de vuelo, clase y cantidad | 3 | 5 |
| US-11 | Registro de datos de pasajeros | 5 | 8 |
| US-12 | Confirmación de compra de pasajes | 8 | 13 |
| US-13 | Reserva temporal de cupos (concurrencia) | 8 | 13 |
| US-14 | Procesamiento de pagos | 8 | 13 |
| US-15 | Manejo de errores y reintentos de pago | 5 | 8 |
| US-16 | Envío de pasaje electrónico y factura | 8 | 13 |
| US-17 | Notificación de cambios y cancelaciones | 5 | 8 |
| US-18 | Preferencias de notificación | 2 | 3 |
| US-19 | Reportes de ocupación | 8 | 8 |
| US-20 | Exportación de reportes | 3 | 5 |
| US-21 | Consulta de vuelos (mostrador) | 3 | 5 |
| US-22 | Atención y venta en mostrador | 8 | 8 |
| US-23 | App móvil: búsqueda y compra | 13 | 8 |
| US-24 | App móvil: notificaciones push | 5 | 5 |
| US-25 | App móvil: tickets electrónicos | 5 | 8 |
| **TOTAL** | **25 User Stories** | **147** | **—** |

---

### 1.2. Planificación General en Sprints

El proyecto se desarrolla con metodología Scrum en **cuatro sprints de dos semanas** cada uno, más el sprint inicial (Sprint 0) aquí documentado. La planificación de cada sprint se fundamenta en tres criterios: **priorización por Business Value** (se atiende primero lo que mayor impacto económico y estratégico genera), **dependencias técnicas** (funcionalidades que requieren de cimientos previos) y **esfuerzo estimado** (balanceando la carga para no exceder la capacidad del equipo).

La asignación se detalla a continuación:

| Sprint | Enfoque | User Stories | SP | BV | Fundamentación |
|--------|---------|--------------|----|----|----------------|
| **#1** | Infraestructura y Administración de vuelos | US-01 a US-07 (7 US) | 37 | 63 | Sentar las bases técnicas (infraestructura, modelo de datos, seguridad) sin las cuales no es posible ninguna funcionalidad posterior, y habilitar el módulo de administración de vuelos, puerta de entrada del flujo comercial completo. |
| **#2** | Búsqueda, compra y pagos | US-08 a US-15 (8 US) | 50 | 81 | Atacar el núcleo transaccional del negocio (buscar, comprar y pagar). Máximo BV por sprint ya que genera el ingreso de la aerolínea; depende del modelo de datos y la infraestructura del Sprint 1. |
| **#3** | Notificaciones, reportes y mostrador | US-16 a US-22 (7 US) | 37 | 49 | Complementar la operación: envío de pasajes y facturas, alertas por cambios/cancelaciones, reportes de ocupación para la toma de decisiones y la atención presencial en mostrador. Depende de la compra y los pagos del Sprint 2. |
| **#4** | Aplicación móvil e integración final | US-23 a US-25 (3 US) | 23 | 21 | Publicar la App móvil para pasajeros sobre la funcionalidad ya construida en la plataforma web, e integrar y estabilizar el producto completo para la entrega final. Cargas menores que permiten absorber desvíos acumulados. |
| **TOTAL** | — | **25 US** | **147** | **214** | — |

**Justificación del orden:**

1. **Sprint 1 – Infraestructura + Administración de vuelos:** Las US-01 a US-03 son prerrequisitos técnicos ineludibles (no existe funcionalidad sin base de datos, infraestructura y seguridad). Las US-04 a US-07 entregan valor temprano al administrador (crear, modificar, cancelar y consultar vuelos), que es el punto de partida del negocio: sin vuelos ofertados no existe venta. Su BV (63) es el segundo más alto y su esfuerzo (37 SP) es moderado, permitiendo al equipo completo adoptar la metodología en el primer sprint.

2. **Sprint 2 – Búsqueda, compra y pagos:** Concentra el corazón económico del sistema (81 BV, el máximo por sprint). La búsqueda (US-08/09) y la compra (US-10 a US-13), junto a los pagos (US-14/15), requieren del modelo de datos y la autenticación ya construidos. Es el sprint que habilita el ingreso real de la aerolínea y por lo tanto se prioriza por encima de funcionalidades de soporte.

3. **Sprint 3 – Notificaciones, reportes y mostrador:** Estas funcionalidades dependen de la información producida por la compra y el pago (para enviar pasajes, notificar cambios y medir ocupación), por lo que deben desarrollarse después del Sprint 2. Su BV acumulado (49) es intermedio; aportan la operación y el control que sostienen la confianza del pasajero y la gestión del administrador.

4. **Sprint 4 – App móvil e integración:** La App móvil (US-23 a US-25) publicada dentro de los 6 meses del proyecto (objetivo del POS) se construye sobre los módulos ya desarrollados para la web, reutilizando la lógica de negocio y el modelo de datos. Al ser la última entrega, se libera espacio para absorber retrabajos de sprints anteriores y asegurar el cumplimiento de la fecha de producción comprometida.

---

## PARTE 2: DEFINICIÓN Y PLANIFICACIÓN DEL SPRINT #1

**Duración del Sprint #1:** 2 semanas (10 días hábiles)
**Capacidad del equipo implementador estimada:** ~240 h (3 perfiles dedicados × 8 h/día × 10 días)
**User Stories comprometidas:** US-01 a US-07
**Story Points comprometidos:** 37 SP

> Nota: siguiendo las pautas de la cátedra, las estimaciones del primer sprint se realizan sin asistencia de herramientas de inteligencia artificial; su comparación contra el tiempo real se documentará en la retrospectiva del sprint.

---

### 2.1. Criterios de Aceptación

Para cada User Story seleccionada para el Sprint #1 se definen criterios de aceptación claros, medibles y verificables.

#### US-01: Preparación de la infraestructura del proyecto

**Criterios de aceptación:**

- **CA-01:** El repositorio del proyecto se encuentra inicializado con una rama principal protegida (sin commits directos) y una guía de contribución (branching, pull requests, revisión de código).
- **CA-02:** El proyecto compila y ejecuta en un entorno local limpio siguiendo exclusivamente la guía de instalación documentada (README), sin dependencias manuales no declaradas.
- **CA-03:** El pipeline de integración continua se ejecuta automáticamente sobre cada pull request, corriendo build y suite de pruebas básicas, con resultado exitoso.
- **CA-04:** Se definió y documentó el stack tecnológico seleccionado (frontend, backend, base de datos, herramientas) con la justificación de cada elección.
- **CA-05:** Existen convenciones de estilo (linter/formateador) configuradas e integradas al repositorio, aplicables con un único comando.

#### US-02: Diseño del modelo de datos

**Criterios de aceptación:**

- **CA-01:** El modelo contempla la totalidad de las entidades del dominio: aeropuertos, vuelos (con plan de operación semanal), clases/capacidades, precios, pasajes, compras, pagos, pasajeros y usuarios/roles.
- **CA-02:** El modelo lógico se presenta con sus relaciones, claves primarias y foráneas, y normalización acorde (eliminación de redundancias evitables).
- **CA-03:** El modelo es capaz de representar los estados de un vuelo (programado, modificado, cancelado) y de una compra (reserva temporal, pendiente de pago, confirmada, fallida).
- **CA-04:** Se generaron scripts de creación/migración de la base de datos ejecutables en un entorno local, permitiendo recrear el esquema desde cero.
- **CA-05:** El modelo fue revisado y validado por el equipo de Análisis y Management contra los requerimientos del enunciado y el POS, quedando la validación documentada.

#### US-03: Autenticación y control de roles

**Criterios de aceptación:**

- **CA-01:** Un usuario puede registrarse (pasajero) e iniciar sesión con email y contraseña de forma segura (almacenamiento con hash y sal).
- **CA-02:** Existen al menos tres roles diferenciados —administrador, empleado de mostrador y pasajero— y cada uno solo puede acceder a los módulos que le corresponden (gestión de vuelos, mostrador y compra, respectivamente).
- **CA-03:** Las rutas y endpoints del backend validan la autenticación (token/sesión) y la autorización por rol, denegando accesos no permitidos con el código de error correspondiente (401/403).
- **CA-04:** El acceso administrativo se restringe por defecto y su asignación inicial está documentada (credenciales de administrador de arranque).
- **CA-05:** Las pruebas de autenticación y control de acceso cubren al menos: login correcto, login incorrecto, acceso permitido y acceso denegado por rol.

#### US-04: Creación de un vuelo

**Criterios de aceptación:**

- **CA-01:** Desde el módulo de administración, un administrador puede crear un vuelo indicando días de operación (lunes a domingo, multi-selección), hora de partida, hora de llegada, aeropuerto de origen y destino.
- **CA-02:** El formulario permite definir el período del año en que el vuelo estará disponible para la venta (fecha inicio y fin) y las capacidades por clase (Economy y Primera).
- **CA-03:** El formulario permite definir el precio del pasaje por clase, diferenciado entre Economy y Primera.
- **CA-04:** El sistema valida los datos antes de persistir: origen distinto de destino, hora de llegada posterior a la de partida, capacidad > 0 y precios > 0; los errores se muestran al usuario de forma clara.
- **CA-05:** Una vez creado, el vuelo aparece en el listado de vuelos con todos sus datos y queda disponible para la configuración de la venta.
- **CA-06:** Solamente los administradores pueden acceder a la funcionalidad de creación de vuelos.

#### US-05: Modificación de un vuelo

**Criterios de aceptación:**

- **CA-01:** Un administrador puede modificar los datos de un vuelo existente seleccionándolo desde el listado.
- **CA-02:** Todos los campos editables (días de operación, horarios, período de venta, capacidades, precios) permiten su actualización, y el sistema persiste el cambio tras una confirmación explícita.
- **CA-03:** Se aplican las mismas validaciones que en la creación; además, si la capacidad se reduce por debajo de la cantidad de pasajes ya vendidos, el sistema lo impide con un mensaje descriptivo.
- **CA-04:** La fecha de modificación queda registrada y el historial de cambios del vuelo es consultable.
- **CA-05:** El rol administrador es el único habilitado para modificar vuelos.

#### US-06: Cancelación de un vuelo

**Criterios de aceptación:**

- **CA-01:** Un administrador puede cancelar un vuelo desde el listado, con una confirmación explícita (incluye advertencia sobre pasajeros ya comprados).
- **CA-02:** Tras la cancelación, el vuelo deja de ofrecerse en las búsquedas de venta y su estado se muestra como "Cancelado" en el listado del administrador.
- **CA-03:** La cancelación no elimina el registro del vuelo: se preserva el historial con fecha y responsable de la cancelación.
- **CA-04:** Ante un vuelo con pasajes vendidos, el sistema genera la lista de pasajeros afectados a modo de insumo para la notificación posterior (US-17, Sprint 3).

#### US-07: Listado y consulta de vuelos (vista administrador)

**Criterios de aceptación:**

- **CA-01:** El módulo de administración muestra el listado de todos los vuelos con paginación y ordenamiento por fecha de salida y ruta.
- **CA-02:** Cada vuelo del listado incluye: origen, destino, horario de partida y llegada, días de operación, período de venta, capacidades y precios por clase.
- **CA-03:** El listado permite filtrar los vuelos por estado (programado/cancelado) y realizar una búsqueda simple por origen o destino.
- **CA-04:** Desde el listado se accede al detalle completo del vuelo y a las acciones correspondientes según el rol (modificar/cancelar para administradores).
- **CA-05:** Los tiempos de respuesta del listado se mantienen por debajo de 2 segundos para un volumen de datos de prueba definido (al menos 100 vuelos).

---

### 2.2. Descomposición en Tareas

A continuación se descompone cada User Story del Sprint #1 en tareas técnicas, con su estimación de esfuerzo en horas. El total del Sprint Backlog se presenta al final de la sección.

#### US-01: Preparación de la infraestructura del proyecto — 30 h

| Tarea | Descripción | Tipo | Horas |
|-------|-------------|------|-------|
| T1.1 | Seleccionar y justificar el stack tecnológico (frontend, backend, base de datos) | Investigación/Decisiones | 6 |
| T1.2 | Inicializar el repositorio con estructura de carpetas, rama protegida y guía de contribución | Diseño/Implementación | 4 |
| T1.3 | Configurar el entorno de desarrollo (IDE, linter, formateador de código, convenciones) | Implementación | 6 |
| T1.4 | Configurar el pipeline de integración continua (build + tests automáticos) | Implementación | 8 |
| T1.5 | Preparar el entorno de base de datos local y su configuración | Implementación | 4 |
| T1.6 | Redactar la guía de instalación y puesta en marcha (README) | Documentación | 2 |
| | **Total US-01** | | **30** |

#### US-02: Diseño del modelo de datos — 62 h

| Tarea | Descripción | Tipo | Horas |
|-------|-------------|------|-------|
| T2.1 | Relevar y consolidar los requerimientos de información a partir del enunciado y el POS | Análisis | 8 |
| T2.2 | Elaborar el modelo conceptual (entidades, atributos y relaciones del dominio) | Diseño | 12 |
| T2.3 | Definir el modelo lógico (tablas, claves primarias y foráneas, tipos de datos) | Diseño | 16 |
| T2.4 | Definir el modelo físico (índices, restricciones, reglas de integridad) y scripts de creación/migración | Diseño/Implementación | 14 |
| T2.5 | Validar el modelo contra los requerimientos junto al equipo de Análisis y Management | Pruebas/Revisión | 6 |
| T2.6 | Documentar el modelo de datos (diagrama y diccionario de datos) | Documentación | 6 |
| | **Total US-02** | | **62** |

#### US-03: Autenticación y control de roles — 36 h

| Tarea | Descripción | Tipo | Horas |
|-------|-------------|------|-------|
| T3.1 | Implementar el registro de usuarios (pasajeros) con almacenamiento seguro de credenciales | Implementación | 8 |
| T3.2 | Implementar el inicio de sesión y la emisión/validación de token de sesión | Implementación | 8 |
| T3.3 | Implementar el control de roles y permisos en backend (middleware de autorización por rol) | Implementación | 10 |
| T3.4 | Aplicar el control de acceso en frontend (rutas protegidas y menús condicionados por rol) | Implementación | 6 |
| T3.5 | Testear los flujos de autenticación y autorización (login, acceso permitido/denegado) | Pruebas | 4 |
| | **Total US-03** | | **36** |

#### US-04: Creación de un vuelo — 56 h

| Tarea | Descripción | Tipo | Horas |
|-------|-------------|------|-------|
| T4.1 | Diseñar el formulario de creación de vuelo y sus campos (días, horarios, ruta, período, capacidad, precios) | Diseño | 8 |
| T4.2 | Implementar los endpoints del backend para alta de vuelo (con persistencia en BD) | Implementación | 14 |
| T4.3 | Implementar las validaciones de negocio del formulario (origen≠destino, horarios, capacidades, precios, período de venta) | Implementación | 12 |
| T4.4 | Implementar la pantalla de creación de vuelo en el frontend del administrador | Implementación | 12 |
| T4.5 | Testear el flujo completo de creación de vuelo (casos felices y de error) | Pruebas | 7 |
| T4.6 | Documentar la funcionalidad de creación de vuelos | Documentación | 3 |
| | **Total US-04** | | **56** |

#### US-05: Modificación de un vuelo — 40 h

| Tarea | Descripción | Tipo | Horas |
|-------|-------------|------|-------|
| T5.1 | Implementar los endpoints del backend para actualización de vuelos (incluye control de capacidad vs. ventas) | Implementación | 12 |
| T5.2 | Implementar el registro del historial de modificaciones del vuelo | Implementación | 6 |
| T5.3 | Implementar la pantalla de edición de vuelo en el frontend del administrador | Implementación | 10 |
| T5.4 | Testear el flujo de modificación (incluye rechazo de capacidad menor a vendidos) | Pruebas | 7 |
| T5.5 | Documentar la funcionalidad de modificación de vuelos | Documentación | 5 |
| | **Total US-05** | | **40** |

#### US-06: Cancelación de un vuelo — 24 h

| Tarea | Descripción | Tipo | Horas |
|-------|-------------|------|-------|
| T6.1 | Implementar el endpoint de cancelación de vuelo y la transición de estado a "Cancelado" | Implementación | 8 |
| T6.2 | Implementar el flujo de confirmación con advertencia y la generación de la lista de pasajeros afectados (insumo de notificación) | Implementación | 8 |
| T6.3 | Excluir los vuelos cancelados de las búsquedas disponibles para la venta | Implementación | 3 |
| T6.4 | Testear el flujo de cancelación (con y sin pasajes vendidos) | Pruebas | 5 |
| | **Total US-06** | | **24** |

#### US-07: Listado y consulta de vuelos (vista administrador) — 26 h

| Tarea | Descripción | Tipo | Horas |
|-------|-------------|------|-------|
| T7.1 | Implementar endpoints de listado de vuelos con paginación, ordenamiento y filtros | Implementación | 10 |
| T7.2 | Implementar la vista de listado paginado y filtrable en el frontend del administrador | Implementación | 8 |
| T7.3 | Implementar la vista de detalle de vuelo y las acciones por rol (modificar/cancelar) | Implementación | 5 |
| T7.4 | Testear el listado, filtros y rendimiento con volumen de datos de prueba | Pruebas | 3 |
| | **Total US-07** | | **26** |

---

#### Resumen de horas del Sprint Backlog

| User Story | SP | Total de horas |
|------------|----|----------------|
| US-01: Preparación de la infraestructura | 5 | 30 |
| US-02: Diseño del modelo de datos | 8 | 62 |
| US-03: Autenticación y control de roles | 5 | 36 |
| US-04: Creación de un vuelo | 8 | 56 |
| US-05: Modificación de un vuelo | 5 | 40 |
| US-06: Cancelación de un vuelo | 3 | 24 |
| US-07: Listado y consulta de vuelos | 3 | 26 |
| **TOTAL SPRINT #1** | **37 SP** | **274 h** |

**Análisis de capacidad:** El total de 274 h estimadas para el Sprint #1 se encuentra dentro del rango de capacidad de un equipo implementador de 3 a 4 perfiles dedicados durante 2 semanas (240 a 320 h), considerando además que el equipo de Análisis y Management participa en jornadas específicas de relevamiento y validación (tareas T1.1, T2.1, T2.5). En caso de detectarse desvíos durante el sprint, el orden de prioridad de las US comprometidas (US-01 → US-07) permite recortar el alcance sin comprometer los sprints posteriores, dado que la totalidad de las 7 US entrega un incremento potencialmente utilizable al cierre del Sprint #1.

---

*Documento elaborado en el marco del Sprint 0 del proyecto SIGVA — Enunciado 2, Administración de Proyectos de Software (APS), Segundo Cuatrimestre 2026.*