# Sistema de Ahorro · Jaime & Marina

## Qué es

Aplicación web personal de planificación financiera para Jaime y Marina. Permite registrar ingresos, gastos y objetivos de ahorro, y calcular cuánto dinero libre queda cada mes para viajes u otros objetivos.

Es un único archivo `index.html` — sin frameworks, sin build — que se sirve directamente en el navegador.

## Tecnología

- **Frontend**: HTML + CSS + JavaScript vanilla, todo en `index.html`
- **Backend/datos**: Firebase Realtime Database — los datos se sincronizan en tiempo real entre dispositivos
- **Hosting**: GitHub (`jaumeborras/ahorro-familia`)

## Qué hace la app

### Panel de métricas (arriba)
Cuatro tarjetas que se actualizan en tiempo real al editar cualquier campo:
- **Ingresos**: suma de los ingresos netos de Jaime y Marina
- **Gastos totales**: fijos + variables
- **Ahorro mensual**: calculado según el objetivo definido (% o cantidad fija)
- **Libre para gastar**: lo que sobra después de gastos y ahorro

### Ingresos mensuales
Dos campos: uno para Jaime y otro para Marina. Se guardan automáticamente en Firebase.

### Objetivo de ahorro
Se puede definir como porcentaje de los ingresos o como cantidad fija mensual.

### Gastos fijos
Lista editable con categorías predefinidas (hipoteca/alquiler, seguros, internet, suscripciones...). Se pueden añadir y eliminar filas.

### Gastos variables
Lista editable con categorías predefinidas (supermercado, restaurantes, transporte, ropa, salud, ocio...). Se pueden añadir y eliminar filas.

### Planificador de viajes
Sección para planificar viajes con:
- Slider para definir qué % del dinero libre se destina a viajes
- Tarjetas por destino con nombre, presupuesto y fecha de salida
- Calendario personalizado estilo Apple para seleccionar la fecha
- Cuenta atrás en tiempo real (días, horas, minutos, segundos)
- Estadísticas: cuánto se lleva ahorrado, cuánto falta y en cuántos meses se llega

### Sincronización
- Indicador en el header (punto verde = sincronizado, naranja = guardando)
- Guardado automático con debounce de 700ms tras cada cambio
- Escucha cambios remotos y actualiza la UI en tiempo real sin interrumpir el foco del usuario

---

## Instrucciones para Claude

- Al iniciar sesión en este proyecto, activar el modelo opusplan (`/model opusplan`)
- Cada cambio realizado en el código debe añadirse al final de la sección **Historial de cambios** de este archivo

---

## Historial de cambios

| Fecha | Descripción |
|-------|-------------|
| 2026-03-23 | Commit inicial: sistema de ahorro familiar Jaime & Marina |
| 2026-03-23 | Integrar Firebase Realtime Database para sincronización en tiempo real |
| 2026-03-23 | Corregir conflicto de nombres con `set()` y versión SDK Firebase |
| 2026-03-23 | Corregir pérdida de foco al escribir importes en la tabla |
| 2026-03-23 | Rediseñar planificador de viajes con destino y fecha manual |
| 2026-03-23 | Mejorar planificador de viajes: quitar % libre, selector de fecha elegante |
| 2026-03-23 | Corregir reset de selects al elegir mes/año del viaje |
| 2026-03-23 | Corregir persistencia de mes/año del viaje y cálculo de stats |
| 2026-03-23 | Añadir fecha exacta de viaje y cuenta atrás en tiempo real |
| 2026-03-23 | Reemplazar input date por calendario personalizado estilo Apple |
| 2026-03-23 | Corregir cierre del calendario al navegar entre meses (x2 intentos) |
| 2026-03-23 | Reescribir lógica `_calOutside` para evitar acumulación de listeners — fix definitivo del cierre del calendario al navegar meses |
| 2026-03-23 | Título del header cambiado a "Familia Borrás Coll", subtítulo eliminado, sync y fecha apilados verticalmente |
| 2026-03-23 | Eliminado el badge de importe en las pestañas Gastos fijos / Gastos variables |
| 2026-03-23 | Icono de pantalla de inicio iOS: bolsa de dinero con símbolo €, luego rediseñado como casa + bolsa |
| 2026-03-23 | Calendario móvil: anclado a right:0 para que no se salga de pantalla + max-width seguro |
| 2026-03-23 | Eliminado texto "Seleccionar fecha" del botón de fecha para alinear con campo presupuesto |
| 2026-03-23 | Modo oscuro: toggle 🌙/☀️ en header, persiste en Firebase, cubre todos los componentes |
| 2026-03-23 | Historial mensual: "Guardar mes" toma snapshot del mes actual, tarjetas editables por mes |
| 2026-03-23 | Ahorro acumulado: barra de progreso real vs objetivo, campo editable de ahorro real por mes |
