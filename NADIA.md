# NADIA — Contexto del producto

> Este documento describe el producto NADIA para dar contexto a una IA de motion design que va a crear animaciones, videos promocionales o contenido visual del producto.

## Qué es NADIA

NADIA es un **sistema de gestión integral para clínicas de fisioterapia y bienestar**. Es una aplicación web (SPA) que centraliza toda la operativa diaria de la clínica: agenda, pacientes, cobros, facturación, comunicación y análisis de datos.

El primer cliente es **Aniento Fisioterapia y Bienestar**, una clínica de fisioterapia en España.

## Estética y marca

- **Colores principales:** Azul (#2563eb como primario, #3b82f6 light, #1d4ed8 dark)
- **Estilo visual:** Interfaz moderna y limpia, modo claro por defecto, modo oscuro disponible
- **Tipografía:** Sans-serif, estilo dashboard SaaS moderno
- **Tono:** Profesional pero accesible, en español
- **Logo:** "NADIA" como marca del software, "Aniento Fisioterapia" como marca del cliente

## Público objetivo

- Fisioterapeutas y profesionales de salud (usuarios del día a día)
- Administradores de clínica (gestión completa)
- Recepcionistas (agenda y registro de pacientes)
- Pacientes (interacción indirecta: firman consentimientos en tablet, reciben WhatsApp)

## Módulos principales

### 1. Panel general (Dashboard)
Pantalla de inicio al entrar. Muestra:
- Saludo personalizado con nombre del profesional
- Contador de citas del día y profesionales activos
- "Insight del día" generado por IA (análisis automático)
- Timeline visual "Tu día" con citas por hora (09:00–19:00)
- KPIs en tarjetas: ingresos hoy, citas semana, pacientes activos, facturas pendientes
- Estado de salas en tiempo real (ocupada/libre con colores)
- Gráfica de barras con citas de la semana

### 2. Calendario de citas
Vista de calendario multi-profesional configurable de 1 a 7 días:
- Columnas por profesional, con color asignado a cada uno
- Creación de citas arrastrando sobre el calendario (drag-to-create)
- Movimiento de citas arrastrando (cambiar hora, profesional o día)
- Mini calendario con mapa de calor de citas
- Filtros por profesional (pills de colores)
- Detección automática de conflictos de horario
- Soporte para citas normales y actividades dirigidas (pilates, yoga, etc.)
- Visualizador de plano de la clínica con ocupación de salas

### 3. Pacientes
Directorio central con búsqueda en tiempo real:
- Ficha completa: datos personales, médicos, historial de citas, facturas
- KPIs por paciente: total citas, pagado, pendiente
- Banner de avisos (alergias, información importante)
- Estado de consentimiento RGPD con indicador visual (firmado/pendiente/menor)
- Menú "Acciones" con: enviar consentimiento a tablet, WhatsApp, editar datos
- Alta en 2 pasos: datos personales + cuestionario médico personalizable
- Borrado RGPD (eliminación total e irreversible de datos)

### 4. Consentimiento digital
Sistema de firma digital de consentimiento RGPD sin papel:
- Tablets registradas como dispositivos desde ajustes
- Profesional envía solicitud de firma desde ficha del paciente
- Tablet muestra interfaz limpia: nombre, texto legal, área de firma
- Paciente firma con el dedo en la pantalla
- Se genera PDF automático con firma y se almacena en la nube
- Estado visible en ficha del paciente

### 5. Bonos y Pools
Paquetes de sesiones prepagadas:
- **Bonos individuales:** asignados a un paciente
- **Bonos empresariales:** asignados a una empresa, usables por sus empleados
- **Pools de crédito:** bolsas compartidas de sesiones para empresas
- Plantillas reutilizables con auto-relleno
- Control de sesiones usadas/disponibles, caducidad
- Descuento automático al cobrar citas

### 6. Actividades dirigidas
Clases grupales (pilates, yoga, HIIT):
- Gestión de actividades con nombre, precio mensual, color
- Suscripciones mensuales de pacientes
- Citas recurrentes en el calendario

### 7. Estadísticas
Panel analítico solo para administradores:
- 6 KPIs principales: ingresos YTD, ingresos mes, pacientes, media euro/hora, citas mes, cancelaciones
- 9 gráficas: ingresos mensuales (área), citas por mes (barras apiladas), facturas por estado (pie), ingresos por tipo (pie), citas por día, facturado por origen, sesiones por método de pago, nuevos pacientes, top profesionales
- **Caja del Día:** ingresos de hoy desglosados por método de pago

### 8. Facturación
Gestión de facturas (solo admin):
- Tres vistas: Todas, Individuales, Empresas
- KPIs: facturado, cobrado, pendiente
- Estados: pagada, pendiente, vencida (con barra de progreso de días)
- Exportación y descarga de PDF

### 9. Empresas
Gestión de empresas cliente:
- Ficha con KPIs: facturas, facturado, pendiente
- Historial de facturas
- Acceso directo a bonos y pools de la empresa
- Registro de visitas con facturación automática

### 10. Agente IA
Chat inteligente conectado a datos reales de la clínica:
- Preguntas en lenguaje natural en español
- 6 acciones rápidas predefinidas (informe mes, pacientes en riesgo, facturas pendientes, slots libres, top pacientes, tendencia 3 meses)
- Genera gráficas de barras, líneas y sectores en la conversación
- Genera tablas con exportación a CSV y Excel
- Genera documentos Excel/CSV descargables (hasta 1.000 filas)
- Acceso filtrado por rol: cada rol clínico solo ve categorías de datos autorizadas
- Más de 50 herramientas internas de consulta de datos

### 11. WhatsApp
Mensajería integrada con WhatsApp Business:
- Lista de conversaciones con búsqueda
- Envío de mensajes libres y plantillas predefinidas
- 11 plantillas en 4 categorías: general, citas, bonos, facturación
- Regla de 24 horas: mensajes libres solo dentro de la ventana, después solo plantillas
- Acceso directo a ficha del paciente desde la conversación

### 12. Ajustes (Configuración)
Panel de administración con múltiples pestañas:
- **General:** datos de la clínica + texto de consentimiento RGPD personalizable
- **Horarios:** apertura por día con turnos múltiples
- **Tarifas:** precios de servicios
- **Tratamientos:** categorías de tratamiento
- **Salas:** definición con colores, profesionales permitidos, visualizador de plano
- **Métodos de pago:** configuración dinámica (Efectivo, Tarjeta, Bizum, etc.)
- **Tipos de bono:** plantillas reutilizables
- **Dispositivos:** tablets para firma de consentimiento
- **Roles:** roles clínicos + categorías de acceso IA por rol
- **Preguntas médicas:** cuestionario de anamnesis personalizable

### 13. Perfil
Gestión personal del profesional: nombre, teléfono, bio, foto.

## Autenticación

- Login con email/contraseña
- Passkeys (biometría/PIN sin contraseña)
- MFA (autenticación en dos pasos)
- Opción de omitir configuración de passkey

## Roles y permisos

Dos niveles de acceso:
- **Usuario estándar:** calendario, pacientes, bonos, pools, actividades, historial, IA, WhatsApp, perfil
- **Administrador:** todo lo anterior + estadísticas, facturación, empresas, profesionales, ajustes

Los roles clínicos (fisioterapeuta, nutricionista, entrenador...) son independientes del nivel de acceso y determinan la apariencia en el calendario y el acceso a categorías del Agente IA.

## Stack técnico (contexto visual)

- **Frontend:** React (SPA), diseño responsive, componentes tipo shadcn/ui
- **Plataforma:** Web app, accesible desde navegador en escritorio, tablet y móvil
- **Idioma:** Toda la interfaz en español

## Flujos clave para animar

Estos son los flujos más representativos del producto, ideales para mostrar en animaciones:

1. **Crear cita arrastrando en el calendario** → visual, intuitivo, muestra la agilidad del sistema
2. **Firma de consentimiento en tablet** → paciente firma con el dedo, se genera PDF automático
3. **Pregunta al Agente IA → respuesta con gráfica** → muestra la inteligencia del sistema
4. **Panel general al iniciar el día** → overview con KPIs, timeline, insight IA
5. **Cobrar una cita → seleccionar método de pago** → flujo rápido y limpio
6. **Enviar WhatsApp desde ficha de paciente** → comunicación integrada sin salir del sistema
7. **Estadísticas con Caja del Día** → datos en tiempo real, gráficas animadas
8. **Crear bono desde plantilla** → seleccionar plantilla, auto-relleno, confirmar
