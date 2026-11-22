# PRD · biencomun

> Documento de requisitos del producto (Product Requirements Document).
> Complétalo en el Sprint 0 (historia H0.3) y pide la aprobación del profesor en un Issue.
> Cada requisito funcional (RF) se convierte en un Issue con la plantilla "Historia de usuario".

| Campo | Valor |
| :--- | :--- |
| Alumno | Rosa Victoria Barrera Banquez |
| Proyecto n.º | Por asignar |
| Sitio de referencia | FixMyStreet |
| Compañero revisor | Por asignar |
| URL desplegada | (se completa en el Sprint 5) |

## 1. Problema
El deterioro de la infraestructura urbana (baches, alumbrado público dañado, acumulación de basura y drenajes obstruidos) afecta diariamente la movilidad y seguridad de los vecinos. Actualmente no existe un canal web centralizado y georreferenciado donde la comunidad pueda registrar incidencias con evidencia fotográfica y hacer seguimiento transparente de su atención.

## 2. Usuarios
* **Ciudadano:** Vecino que consulta el mapa público de incidencias urbanas y registra nuevos reportes marcando la ubicación exacta y adjuntando una fotografía.
* **Moderador:** Encargado que revisa la cola de reportes pendientes para verificar la evidencia, aprobarlos, rechazarlos o marcarlos como resueltos.

## 3. Alcance
* **Incluye:** Mapa interactivo con reportes validados, registro de reportes con coordenadas geográficas y fotografía, cola de moderación por estados (`pendiente`, `aprobado`, `rechazado`, `resuelto`), filtrado por categoría y vista de detalle de cada reporte.
* **Fuera de alcance inicial:** Aplicación móvil nativa, notificaciones push/SMS, chat entre usuarios e integración directa con sistemas externos de alcaldías.

## 4. Requisitos Funcionales
* **RF-01:** Mostrar en el mapa público únicamente los reportes con estado `aprobado` o `resuelto`, permitiendo filtrarlos por categoría.
* **RF-02:** Permitir al ciudadano crear un reporte seleccionando ubicación en el mapa, eligiendo categoría, escribiendo descripción y adjuntando una fotografía (nace con estado `pendiente`).
* **RF-03:** Permitir al ciudadano consultar el detalle completo de un reporte aprobado o resuelto (foto, ubicación, fecha y estado).
* **RF-04:** Permitir al moderador listar la cola de reportes en estado `pendiente` y cambiar su estado a `aprobado`, `rechazado` o `resuelto`.

## 5. Funcionalidades y carpetas en `src/`
| Funcionalidad | Carpeta en `src/` | Descripción |
| :--- | :--- | :--- |
| Autenticación y roles | `src/auth/` | Registro, inicio de sesión y control de permisos (`ciudadano` y `moderador`). |
| Gestión de reportes | `src/reportes/` | Creación de incidencias geolocalizadas, listado público y consulta de detalle. |
| Carga de fotografías | `src/uploads/` | Recepción, validación de formato/tamaño y almacenamiento de fotos de evidencia. |
| Cola de moderación | `src/moderacion/` | Bandeja de revisión para aprobar, rechazar o resolver reportes pendientes. |
| Vistas e interfaz web | `src/public/` | Mapa interactivo, formulario de reporte y panel web de moderación. |