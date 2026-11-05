# MENTALIDAD 7

App personal (PWA) de mentalidad y emociones.
Interfaz en **GitHub Pages** · Datos en **Google Sheets** · Audios en **Google Drive**.

```
mentalidad7/
├── index.html          # interfaz (edita API_URL)
├── manifest.json       # configuración de app instalable
├── sw.js               # caché offline de la interfaz
├── icons/              # íconos (180 iPhone, 192/512 PWA, 1024 original)
└── apps-script/Code.gs # backend: se pega en Apps Script, NO se ejecuta en GitHub
```

## 1. Backend (Google Sheets + Apps Script)
1. Crea una Google Sheet → **Extensiones > Apps Script**.
2. Borra todo y pega `apps-script/Code.gs`. Cambia `CLAVE` por una clave tuya.
3. Ejecuta `setup` y acepta permisos.
4. **Implementar > Nueva implementación > Aplicación web**
   - Ejecutar como: **Yo**
   - Quién tiene acceso: **Cualquier usuario** (la clave protege tus datos)
5. Copia la URL que termina en `/exec`.

> Si cambias `Code.gs`: **Implementar > Administrar implementaciones > Editar > Nueva versión** (así la URL no cambia).

## 2. Frontend (GitHub Pages)
1. En `index.html` reemplaza `PEGA_AQUI_TU_URL_DE_APPS_SCRIPT` por tu URL `/exec`.
2. Crea un repositorio en github.com (ej. `mentalidad7`).
3. Sube todos los archivos (Add file > Upload files) o por terminal:
   ```bash
   git init && git add . && git commit -m "MENTALIDAD 7"
   git branch -M main
   git remote add origin https://github.com/TU_USUARIO/mentalidad7.git
   git push -u origin main
   ```
4. **Settings > Pages > Source: Deploy from a branch > main / (root) > Save**.
5. En 1–2 min estará en `https://TU_USUARIO.github.io/mentalidad7/`.

## 3. iPhone
1. Abre la URL en **Safari** (no Chrome).
2. Compartir ⬆ > **Agregar a pantalla de inicio** > Agregar.
3. Abre desde el ícono: pantalla completa, sin barra de Safari. Ingresa tu clave una vez.

## Actualizar la app
Edita, sube a GitHub y cambia `CACHE = 'm7-vX'` en `sw.js`. Cierra y abre la app dos veces.
