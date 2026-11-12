# Tablero KPI Diario · Logística Total SRL

Página estática que lee la planilla **Reporte KPI** de Google Sheets y muestra el tablero de KPI diarios: Tablero del día, Tabla por período, Configuración e Info.

## 1. Hacer que la planilla se pueda leer desde la web

La página lee la planilla directamente desde el navegador de quien la abre, sin iniciar sesión. Para eso:

1. Abrí la planilla Reporte KPI en Google Sheets.
2. **Compartir** → Acceso general → **Cualquier persona con el vínculo** → rol **Lector**.

> Importante: con esto, cualquiera que tenga el link de la planilla (o del tablero) puede ver todos sus datos. Si eso no es aceptable, no publiques el tablero en un sitio público.

## 2. Subirlo a GitHub Pages

1. En GitHub, creá un repositorio nuevo (por ejemplo `tablero-kpi`).
2. Subí el archivo `index.html` (y este README si querés) a la raíz del repositorio: **Add file → Upload files**.
3. Andá a **Settings → Pages**. En *Build and deployment* elegí **Deploy from a branch**, rama `main`, carpeta `/ (root)` y **Save**.
4. En uno o dos minutos el tablero queda en `https://<tu-usuario>.github.io/tablero-kpi/`.

## 3. Cómo se actualiza

- Cada vez que alguien abre el tablero, lee la planilla. Para no pedirla de más, guarda la lectura en el navegador durante 60 minutos.
- El botón **⟳ Actualizar datos** fuerza una lectura nueva en el momento.
- Responsables, objetivos, condición y qué indicadores se muestran se editan en la hoja **Config KPI** de la planilla.

## Ajustes (dentro de `index.html`)

Al principio del bloque `<script>` del `<head>` están:

- `SHEET_ID`: el ID de la planilla.
- `HOJAS`: el nombre de cada hoja que se lee. Si renombrás una hoja en la planilla, cambiala acá también.
- `MINUTOS_CACHE`: cuántos minutos se reutiliza una lectura.

## Si aparece "Sin conexión con Google Sheets"

- Revisá que la planilla esté compartida como "Cualquier persona con el vínculo".
- Revisá que los nombres de las hojas coincidan con `HOJAS`.
- Abrí la consola del navegador (F12) para ver el mensaje de error.
