# Plan — Informe final y presentación (SIGVA, Equipo Verde)

## 0. Qué piden (de `guias.md`)

- **Informe** corto (~2 carillas), siempre **desde el punto de vista del grupo que gestionó el desarrollo** (comisión de Análisis y Management; el equipo blanco implementó).
- Contenido obligatorio:
  1. Descripción general del proyecto y sus objetivos.
  2. Breve resumen de lo realizado en cada sprint.
  3. Conclusiones finales sobre la modalidad de trabajo ágil, lo aprendido en cada sprint, etc.
- **Defensa**: presentación de **≤ 10 minutos** por grupo, con lo más relevante del informe.
- Entregas en Moodle: el informe (obligatorio) y las slides (opcional, pero conviene subirlas para tenerlas el día de la defensa).

## 1. Fuentes

| Archivo (`entregados/`) | De dónde sacar |
|---|---|
| `Entrega 1 StartUp - Equipo Verde.pdf` | POS: problema, meta, 7 objetivos, criterios de éxito, 13 riesgos + 6 planes RSGR |
| `informe-sprint-0-equipo-verde.pdf` | Supuestos del análisis, product backlog (29 US, 144 SP, 233 BV), plan en sprints, criterios de priorización (dependencias + BV/SP + velocity 35–40 SP), Sprint #1 y DoD |
| `informe-sprint-1-equipo-verde.pdf` | Retro S1 (comunicación, estimaciones, recortes de alcance) + planificación S2 |
| `informe-sprint-2-equipo-verde.pdf` | Review S2 (64 tests, US-11 observada, decisión pasarela) + retro + planificación S3 |
| `informe-sprint-3-equipo-verde.pdf` | Review S3 (71 tests, observaciones) + retro final + lecciones aprendidas |

Repo del equipo implementador: https://github.com/Jona-77/SIGVA (por si queremos capturas de pantalla para las slides).

## 2. Datos clave ya extraídos (para no releer los PDFs)

### Proyecto
- **SIGVA** — Sistema Integral de Gestión de Vuelos y Venta de Pasajes (enunciado N.º 2). Plataforma web con interfaces para administrador, mostrador y pasajero + app móvil.
- Problema: gestión manual y fragmentada de vuelos, ventas y atención.
- Objetivos (resumir a 3–4 líneas): ABM de vuelos; compra de hasta 9 pasajes en < 5 min; envío de pasaje y factura por email; reportes de ocupación; alertas ante cambios/cancelaciones; app móvil.
- Riesgo principal identificado: **sobreventa por compras concurrentes** (R2, exposición 12) → efectivamente se mitigó con reserva temporal + bloqueo por salida (US-15). Buen ejemplo para mostrar que la gestión de riesgos se tradujo en US concretas.

### Planificación (Sprint 0)
- 29 User Stories, 144 SP, 233 BV, en 8 épicas. Formato Como/Quiero/De forma que + INVEST + criterios de aceptación.
- Priorización: dependencias → BV/SP → velocity inicial 35–40 SP (derivada de horas).
- Plan original: 4 sprints (el 4.º: mostrador, app móvil, filtros, exportación).

### Por sprint

| Sprint | Objetivo | US | SP | BV | Horas est. | Resultado |
|---|---|---|---|---|---|---|
| 1 | Admin gestiona la oferta de vuelos (login, aeropuertos, ABM y listado de vuelos) | US-01, 02, 03, 06, 07, 08, 09, 10 | 39 | 68 | 250 | Funcionalidad completa para la demo; **sin tests, sin CI, sin diagrama ER**; US-08 parcial |
| 2 | Pasajero se registra, busca, selecciona, carga datos, reserva y paga | US-04, 11, 13, 14, 15, 17 + 2 técnicas (testing S1, fix US-08) | 35 | 63 | 126 | 64 tests OK; todo aprobado salvo **US-11 (“+1”)**; pago con modo local-sandbox (Mercado Pago aceptado sin cuenta); integración a `master` pendiente |
| 3 | Emails de pasaje/factura, reintento de pago, historial, alertas, cuentas de empleados, reportes | US-05, 16, 18, 19, 20, 22 + 2 técnicas (fix US-11, integración S2) | 32 | 47 | 83 | 71 tests OK; **las 6 US aprobadas sin correcciones**; observaciones menores (bug de zona horaria en “+1”, estados en inglés, PDFs sin diseño) |

- **Totales entregados:** 20 US de producto, **106 de 144 SP (~74 %)**, **178 de 233 BV (~76 %)**.
- **No realizado** → 38 SP: US-12 (filtrado y ordenamiento; planificada para el S3 en el Sprint 0, pero no entró al sprint backlog del S3) y el Sprint 4 planificado, no ejecutado (US-21, 23–29): exportación de reportes, **interfaz de mostrador** y **app móvil**. Hay que decirlo explícitamente: el proyecto terminó en el S3 (“el último del proyecto”, informe S3), y las stories de mostrador y app dependían de casi todo lo anterior (tabla de dependencias del Sprint 0). Ojo: no justificar con BV/SP, porque US-29 tiene BV/SP 2,67, de los más altos.

### Evolución / aprendizajes (hilo conductor de las conclusiones)
- **Comunicación:** S1 arrancó con un vocero por equipo (Oscar / Jhonatan) → insuficiente → grupo de WhatsApp con ambos equipos.
- **Estimaciones:** S1 sobreestimó implementación y subestimó testing → S2 baja ~10 % las horas de implementación y separa el testing → S2 llegó justo (carga de otras materias) → S3 baja de 35 a 32 SP → S3 cumplió todo. Pero **sin horas reales registradas** no se pudo validar la estimación en horas.
- **Alcance y DoD:** en S1, para llegar a la demo, se **eliminaron** la CI (“no es rentable para el scope”) y el diagrama ER (“no agrega valor al incremento”), y el **testing pasó al S2** como US técnica (junto con la corrección de US-08). Las US técnicas no suman SP ni BV. Patrón repetido en S2→S3 (corrección de US-11 e integración). Lección: acordar al inicio qué puntos de la DoD no pueden sacrificarse cuando el tiempo se acorta.
- **Testing:** de 0 tests (S1) a 64 (S2) a 71 (S3); faltan tests de frontend y de zona horaria.
- **Review / documentación:** S2 entregó en tandas con checklist (facilitó la review, aunque la checklist marcó US-11 como cumplida sin estarlo) → S3 un único commit de 1.537 líneas sin documentación actualizada (retroceso).
- **Rol de gestión:** asumimos el rol de PO (definimos BV nosotros), verificamos criterios contra el código y la ejecución, no solo contra la checklist.
- Lecciones finales del informe S3: tandas pequeñas con checklist; probar criterios en la pantalla real y en distintas configuraciones; planificar el despliegue con responsable; registrar horas reales; DoD con puntos innegociables.

> ✅ Resuelto: la review del S3 solo da por cumplido el criterio 1 (integración a `master` vía PR #3 y #4); el criterio 2 (despliegue en el entorno de demostración) no se verificó. Por eso la retro dice “a medias”. En el informe final se dice solo eso (“se completó a medias”), sin afirmar que el despliegue quedó pendiente, porque ningún informe lo dice así.

## 3. Informe final — estructura (≤ 2 carillas)

Formato: `informe-final/informe-final-equipo-verde.md` → exportar a PDF con el mismo método que los informes de sprint (mantener el mismo encabezado: proyecto, materia, integrantes). Tono en primera persona del plural, como gestores.

1. **Encabezado** (3–4 líneas): título, materia, integrantes, rol de la comisión (Análisis y Management) y equipo implementador.
2. **Descripción del proyecto y objetivos** (~1/3 carilla): problema, meta, objetivos resumidos, cómo organizamos el backlog (29 US / 144 SP, priorización dependencias + BV/SP).
3. **Resumen por sprint** (~3/4 carilla): un párrafo corto por sprint (0 a 3) con objetivo, qué se entregó y el evento más relevante. Incluir la tabla compacta de la sección 2 (Sprint / SP / BV / resultado).
4. **Resultado global** (2–3 líneas): 106/144 SP, qué quedó fuera y por qué.
5. **Conclusiones** (~2/3 carilla), en bullets breves:
   - Sobre la modalidad ágil (iteraciones cortas permitieron recalibrar estimaciones y alcance; reviews con criterios de aceptación objetivos detectaron defectos que la checklist no; el traslado del trabajo pendiente como US técnicas permitió completarlo en el S2, pero en el S3 la integración quedó a medias).
   - Aprendizajes por sprint (una línea cada uno).
   - Qué haríamos distinto (horas reales, DoD con puntos que no se sacrifican, despliegue planificado, tests de frontend).

Control de largo: si se pasa de 2 carillas, recortar primero el detalle de US por sprint (dejar solo la tabla) y luego las conclusiones a 5–6 bullets.

## 4. Presentación — estructura (≤ 10 min, ~9 slides, ~1 min c/u)

| # | Slide | Contenido | Tiempo |
|---|---|---|---|
| 1 | Portada | SIGVA, Equipo Verde, integrantes, rol de gestión | 0:20 |
| 2 | El problema y la meta | Problema en 1 frase + 3 roles + objetivos clave (iconos) | 1:00 |
| 3 | Cómo planificamos | Backlog 29 US / 144 SP / 233 BV, 8 épicas, criterios de priorización, riesgo principal → US-15 | 1:15 |
| 4 | Sprint 1 | Objetivo, 39 SP, qué se entregó, qué se recortó (CI y ER eliminados; tests pasados al S2) | 1:00 |
| 5 | Sprint 2 | Objetivo, 35 SP, flujo de compra punta a punta, 64 tests, US-11 observada | 1:00 |
| 6 | Sprint 3 | Objetivo, 32 SP, 6/6 aprobadas, 71 tests, observaciones | 1:00 |
| 7 | Resultado global | Gráfico de SP planificados vs. entregados por sprint + barra 106/144; qué quedó afuera | 1:00 |
| 8 | Cómo evolucionamos | Línea de tiempo: comunicación, estimaciones (S2: −10 % horas de implementación; S3: 35→32 SP), testing (0→64→71), documentación | 1:30 |
| 9 | Conclusiones y lecciones | 4–5 lecciones + cierre | 1:30 |
| — | (Opcional) Demo / capturas | 2–3 capturas del sistema (búsqueda, compra, reporte) si sobra tiempo | — |

Total ≈ 9:35. Repartir las slides entre los tres integrantes (p. ej. 1–3, 4–6, 7–9) y ensayar con cronómetro.

Formato de las slides: a definir (Google Slides / PowerPoint / PDF exportado). Recomendación: generar el deck y exportarlo a **PDF** para subirlo a Moodle, así se ve igual en cualquier máquina el día de la defensa.

## 5. Pasos

1. [x] Resolver la inconsistencia de la integración del S2 (ver sección 2).
2. [x] Redactar el informe (`informe-final-equipo-verde.tex`, LaTeX) siguiendo la sección 3. Sin capturas del sistema y sin notas al pie ni citas.
3. [x] Exportar a PDF (`informe-final-equipo-verde.pdf`).
4. [ ] Armar las slides a partir del informe final (sección 4), con el gráfico de SP.
