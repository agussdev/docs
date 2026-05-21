# Changelog

Todos los cambios relevantes en la documentación de NADIA se registran en este archivo.

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
