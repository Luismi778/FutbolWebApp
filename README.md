# FutbolWebApp

Aplicación web de gestión deportiva desarrollada en **DataFlex (WebApp Drilldown)** conectada a una base de datos **MySQL / MariaDB**.

## Funcionalidades implementadas

### Sprint 1 — Estructura base y vistas principales
* **Dashboard** personalizado con acceso rápido a todas las entidades.
* **Data Dictionaries** y vistas **Select / Zoom** para la gestión completa (CRUD) de:
  * Ligas (`SelectLiga` / `ZoomLiga`)
  * Equipos (`SelectEquipo` / `ZoomEquipo`)
  * Jugadores (`SelectJugador` / `ZoomJugador`)
  * Entrenadores (`SelectEntrenador` / `ZoomEntrenador`)
  * Posiciones (`SelectPosicion` / `ZoomPosicion`)

### Sprint 2 — Navegación Drilldown y mejoras funcionales
* **Navegación relacional** configurada entre vistas (`nfFromMain`, `nfFromParent`, `nfFromChild` y `nfUndefined`).
* **Lista de equipos por liga** integrada directamente dentro de `ZoomLiga`.
* **Títulos dinámicos** en la cabecera y ruta de navegación (*breadcrumb*) para `ZoomJugador` (`Jugador: [Nombre Apellido]`) y `ZoomEntrenador` (`Entrenador: [Nombre Apellido]`) mediante `OnPostFind`.
* **Carga automática de posiciones** en `ZoomJugador` consultando la tabla intermedia `jugadorposicion`.
* **Arquitectura limpia de objetos web** usando `Register_Object` en lugar de inclusiones cruzadas `Use *.wo`, y `.gitignore` configurado para excluir binarios, cachés y sesiones locales de DataFlex.

## Estructura del proyecto
* `AppSrc/` — Vistas web (`.wo`) y punto de entrada (`WebApp.src`).
* `DDSrc/` — Data Dictionaries (`.dd`) y definiciones de tablas (`.fd`).
* `AppHtml/` — Recursos web, temas y hojas de estilo (`application.css`).
* `Data/` — Archivos de configuración de conexión y tablas locales de DataFlex.
