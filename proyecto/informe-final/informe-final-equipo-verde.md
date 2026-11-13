# Informe Final — SIGVA

**Proyecto:** SIGVA — Sistema Integral de Gestión de Vuelos y Venta de Pasajes
**Materia:** Administración de Proyectos de Software — Segundo Cuatrimestre 2026
**Integrantes:** Bertotto Tomás, Blanco Oscar, Cid Nicolás
**Rol de la comisión:** Análisis y Management (la implementación estuvo a cargo del equipo blanco)

## 1. Descripción del proyecto y objetivos

SIGVA es una plataforma para una aerolínea nacional que hoy gestiona la creación de vuelos, la venta de pasajes y la atención de pasajeros de forma manual y fragmentada. La meta del proyecto es centralizar esa operación en una plataforma web con interfaces diferenciadas para administradores, empleados de mostrador y pasajeros, complementada por una aplicación móvil para pasajeros.

Los objetivos principales definidos en el Start Up fueron:

- Que los administradores puedan crear, modificar y cancelar vuelos (días de operación, horarios, ruta, período de venta, capacidad y precio por clase).
- Que un pasajero pueda buscar y comprar hasta 9 pasajes en menos de 5 minutos, desde la web o desde la app.
- Enviar automáticamente el pasaje electrónico y la factura por email al confirmarse el pago, y avisar a los pasajeros ante cambios de horario o cancelaciones.
- Generar reportes de ocupación por vuelo, clase y fecha.

Como comisión de gestión relevamos los requerimientos y armamos el product backlog: 29 user stories, 144 story points y 233 puntos de valor de negocio, que fijamos nosotros al asumir el rol de Product Owner. Priorizamos las stories por sus dependencias y por la relación valor/esfuerzo, planificamos cada sprint y revisamos cada incremento del equipo implementador contra los criterios de aceptación. El riesgo principal que identificamos fue la sobreventa de asientos por compras simultáneas, y lo convertimos en una story propia: la reserva temporal con control de concurrencia.
