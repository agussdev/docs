# Changelog

Todos los cambios relevantes en la documentación de NADIA se registran en este archivo.

## [2026-05-21] — Actualización de documentación

### Módulos actualizados

#### Profesionales (`modulos/profesionales.mdx`)
- Documentada la nueva **ficha individual del profesional** (`/professionals/[id]`): datos editables, campos nuevos (autónomo, tarifa/hora, días de vacaciones/año) y estadísticas por periodo (citas, horas, ingresos, ocupación).
- Documentado el **editor de horario personalizado**: horario semanal independiente del horario de clínica, con soporte para múltiples franjas por día.
- Documentado el **horario bisemanal** (semana A/B): rotación automática con fecha de referencia.
- Documentadas las **excepciones de horario**: excepciones por día exacto y por periodo con horario semanal alternativo, con prioridad de resolución documentada.
- Documentada la **gestión de vacaciones**: calendario visual, días sueltos o rangos con notas, contador de días usados vs asignados, vista de vacaciones de otros profesionales.
- Documentada la **validación de horario en citas**: NADIA valida automáticamente que la cita esté dentro del horario disponible del profesional.

#### Actividades dirigidas (`modulos/actividades.mdx`)
- Documentada la **domiciliación bancaria** como forma de pago al inscribir paciente: campos IBAN (formato ES + 22 dígitos) y titular de cuenta con validación.
- Documentado el **modelo de inscripción separado**: inscripción permanente vs suscripciones mensuales generadas automáticamente.
- Documentada la **facturación mensual automática**: cron del día 1 que genera suscripciones y facturas para todas las inscripciones activas.
- Documentados los **justificantes de pago**: subida y visualización de recibos bancarios para suscripciones con domiciliación.

#### Citas (`modulos/citas.mdx`)
- Documentada la **detección de conflictos en citas recurrentes**: pre-check contra citas existentes del profesional, diálogo con fechas conflictivas, opción de crear solo las sesiones sin conflicto.
- Documentado el **input libre de meses para recurrentes**: de 1 a 24 meses (antes era un desplegable fijo).
- Documentado el **bloqueo de fechas pasadas** en el selector de fecha al crear citas nuevas.
- Documentada la **info del creador de la cita** visible solo para administradores.
- Documentado el **ancho mínimo de columna** (80px) para clínicas con 20+ profesionales.
- Documentado el **bloqueo visual de franjas** en el calendario según horario del profesional y vacaciones.
- Documentadas las **notificaciones automáticas de WhatsApp**: confirmación al crear, aviso al cancelar y recordatorio 24h antes.

#### WhatsApp (`modulos/whatsapp.mdx`)
- Documentada la **prioridad de nombre en conversaciones**: se muestra el nombre del paciente vinculado en lugar del nombre de WhatsApp.
- Documentada la opción de **vincular conversación a empresa** (además de paciente), con exclusión mutua.

#### Pacientes (`modulos/pacientes.mdx`)
- Documentada la sección **Actividades dirigidas** en la ficha del paciente: listado de actividades en las que está inscrito.
- Documentado el checkbox **"Ha dejado reseña"** para seguimiento de reseñas de pacientes.

#### Panel general (`modulos/panel-general.mdx`)
- Documentado el **rediseño completo del panel**: nueva timeline horizontal del día por profesional con estados visuales y línea "Ahora".
- Documentada la **tarjeta de cita en curso y próxima cita** con cuenta atrás en minutos.
- Documentados los **KPIs con sparklines** y comparativa porcentual.
- Documentado el **gráfico semanal** de área con tendencias de actividad.

#### Facturación (`modulos/facturacion.mdx`)
- Documentado el botón **"Ver justificante"** para facturas con recibo de domiciliación adjunto.
- Documentado el **nuevo diseño premium de facturas PDF**.
- Actualizada la nota de generación automática para incluir las facturas mensuales de actividades dirigidas.

---

### Resumen de cambios en el producto (nadia-api + nadia-dashboard)

Estos son los cambios implementados en el producto que motivaron esta actualización de la documentación:

#### Profesionales — ficha individual, horarios y vacaciones (nuevo)
- Nueva página de detalle del profesional con datos editables, estadísticas y KPIs por periodo.
- Campos nuevos: autónomo (sí/no), tarifa por hora, días de vacaciones anuales.
- Editor de horario semanal personalizado por profesional (independiente del horario de clínica).
- Soporte bisemanal (semana A/B) con fecha de referencia para rotación automática.
- Excepciones de horario: por día exacto y por periodo con horario semanal alternativo.
- Gestor de vacaciones con calendario visual, días sueltos/rangos, notas y contador anual.
- Vista de vacaciones de otros profesionales para evitar solapamientos.
- Validación automática de horario del profesional al crear/editar citas.
- Bloqueo visual de franjas no disponibles en el calendario.
- Endpoint de disponibilidad bulk para múltiples profesionales.

#### Actividades dirigidas — domiciliación y facturación automática
- Modelo de inscripción separado de suscripciones mensuales.
- Domiciliación bancaria: tipo de pago con IBAN y titular al inscribir paciente.
- Cron mensual de facturación automática (día 1, 02:00): genera suscripciones y facturas.
- Subida y visualización de justificantes de pago (recibos bancarios) almacenados en R2.
- Scripts de migración de inscripciones y backfill de receipt URLs.

#### Citas — conflictos, recurrentes y notificaciones
- Detección de conflictos en citas recurrentes: pre-check contra citas existentes, diálogo de resolución.
- Input libre de meses para citas recurrentes (1–24, antes desplegable fijo).
- Bloqueo de fechas pasadas en selector de fecha al crear citas.
- Info del creador de la cita visible solo para admins en preview y detalle.
- Columna mínima de 80px en calendario para 20+ profesionales.
- WhatsApp: confirmación automática al crear cita, aviso al cancelar, recordatorio diario 24h antes.

#### WhatsApp — mejoras en conversaciones
- Nombre del paciente vinculado como nombre principal en conversaciones (antes: nombre de WhatsApp).
- Resolución de nombres de paciente y empresa vía aggregation en lista y detalle.
- Vinculación de empresa a conversación (antes solo paciente), con exclusión mutua.
- Cabeceras CORS en endpoint SSE para soporte cross-origin.

#### Panel general — rediseño completo
- Timeline horizontal del día con citas por profesional, colores, estados y línea "Ahora".
- Tarjeta de cita en curso + próxima cita con cuenta atrás.
- KPIs con mini sparklines y comparativa porcentual.
- Gráfico semanal de área con recharts.
- Widget de salas actualizado.

#### Ficha de paciente — ampliaciones
- Listado de actividades dirigidas en las que el paciente está inscrito.
- Checkbox "Ha dejado reseña" (campo hasLeftReview).

#### Facturación — mejoras
- Nuevo diseño premium de facturas PDF (estilo "Headline Block", paleta teal).
- Campo receiptUrl en facturas y botón "Ver justificante" para recibos de domiciliación.
- Generación automática de facturas mensuales para actividades dirigidas.

#### Panel general (admin) — fix de permisos
- Admins sin campo permissionLevel explícito ahora ven correctamente los datos completos del dashboard.

---

## [2025-05-21] — Actualización de documentación

### Nuevas páginas

- **Consentimiento digital** (`modulos/consentimiento.mdx`) — Documentación completa del nuevo sistema de firma digital de consentimiento RGPD: flujo de firma en tablet, generación de PDF, gestión de dispositivos y seguimiento del estado de firma en la ficha del paciente.

### Módulos actualizados

#### Agente IA (`modulos/asistente-ia.mdx`)
- Documentado el **control de acceso por rol**: categorías de datos configurables por rol clínico (citas, pacientes, facturación, profesionales, KPIs, empresas, otros).
- Documentada la **generación de documentos**: exportación de datos a Excel (XLSX) y CSV directamente desde el chat.
- Documentada la **exportación de tablas**: botones de descarga CSV/Excel en tablas del asistente.
- Actualizado el acceso: ahora requiere categorías de IA asignadas al rol.

#### Ajustes (`modulos/ajustes.mdx`)
- Documentada la sección **Métodos de pago**: configuración dinámica de métodos de cobro (Efectivo, Tarjeta, Bizum, etc.).
- Documentada la sección **Tipos de bono (plantillas)**: plantillas reutilizables con nombre, sesiones, precio y caducidad en meses.
- Documentada la sección **Dispositivos**: gestión de tablets para firma de consentimiento digital.
- Documentadas las **categorías de IA por rol**: configuración de acceso al Agente IA en la sección de roles de profesionales.
- Documentado el campo **Texto de consentimiento RGPD** en la pestaña General.

#### Estadísticas (`modulos/estadisticas.mdx`)
- Documentada la nueva sección **Caja del Día**: ingresos del día desglosados por método de pago con total general.

#### Bonos (`modulos/bonos.mdx`)
- Documentado el uso de **plantillas de bono** al crear un nuevo bono: selector de plantilla con auto-relleno de campos y cálculo automático de caducidad.

#### Pacientes (`modulos/pacientes.mdx`)
- Documentado el **indicador de estado de consentimiento** en la cabecera de la ficha (firmado, menor, pendiente).
- Documentado el nuevo **menú "Acciones"** que consolida todas las acciones de la ficha (consentimiento, WhatsApp, datos personales, datos médicos).

### Primeros pasos actualizados

#### Roles y permisos (`primeros-pasos/roles.mdx`)
- Documentado el **acceso al Agente IA por rol**: explicación de cómo las categorías de datos se configuran por rol clínico.

#### Acceso al sistema (`primeros-pasos/acceso.mdx`)
- Documentada la opción **"Omitir por ahora"** en la configuración de passkey: el sistema recuerda la decisión y no vuelve a mostrar el aviso.

### Navegación (`mint.json`)
- Añadida la página de **Consentimiento digital** al menú de módulos, entre Pacientes y Bonos.

---

### Resumen de cambios en el producto (nadia-api + nadia-dashboard)

Estos son los cambios implementados en el producto que motivaron esta actualización de la documentación:

#### Sistema de consentimiento digital (nuevo)
- API completa de consentimiento: solicitud, firma, generación de PDF, almacenamiento en R2.
- Página pública de tablet con firma digital y tema minimalista.
- Gestión de dispositivos (tablets) desde ajustes.
- Indicador de estado de consentimiento en ficha del paciente.
- Texto legal personalizable por clínica.
- Limpieza de datos de consentimiento en borrado RGPD.

#### Agente IA — mejoras
- Generación de documentos Excel/CSV desde el chat (hasta 1.000 filas).
- Filtrado de herramientas por rol: cada rol solo accede a las categorías de datos asignadas.
- Registro de peticiones con TTL de 90 días (cumplimiento GDPR).
- Mejora del filtro de temas fuera de contexto (menos falsos positivos).
- UI de descarga de documentos y botones de exportación en tablas.
- Limpieza automática de JSON en mensajes del asistente.

#### Métodos de pago dinámicos
- Eliminación de métodos de pago fijos (Efectivo/Tarjeta): ahora configurables por clínica.
- Selector dinámico en todos los modales de cobro.
- Nueva pestaña de configuración en Ajustes.

#### Plantillas de bono
- Plantillas reutilizables de bono con nombre, sesiones, precio y caducidad.
- Selector de plantilla con auto-relleno al crear bono.
- Pestaña de configuración en Ajustes.

#### Caja del Día
- Nueva sección en Estadísticas con ingresos del día por método de pago.
- Siempre visible, incluso sin cobros registrados.

#### Ficha de paciente — consolidación de acciones
- Botones de cabecera agrupados en menú desplegable "Acciones".
- Integración de controles de consentimiento en el menú.

#### Autenticación
- Mensajes de error de login en español.
- Opción de omitir configuración de passkey con persistencia de la decisión.
