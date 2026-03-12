# Diseños RH Ensambles — Portafolio Web

Sistema de portafolio y panel de administración en un solo archivo HTML autocontenido, publicado vía GitHub Pages.

---

## 🌐 Sitio en vivo

```
https://elparivera.github.io/DisenosRhensambles/
```

---

## 🔐 Acceso al Panel de Administración

1. Abre el sitio en tu navegador
2. Haz clic en **⚙ Panel Admin** en el pie de página
3. Ingresa las credenciales:

| Campo | Valor |
|-------|-------|
| Usuario | `admin` |
| Contraseña | `disenosrh2024` |

> Puedes cambiar usuario y contraseña desde el panel → sección **Mi Cuenta**.

---

## 💾 Sistema de Auto-Guardado

El portafolio usa un sistema de **estado embebido** dentro del mismo archivo HTML. Todos los datos (productos, imágenes, configuración, citas) viven dentro del archivo.

### ¿Cómo funciona?

```
[Editas en el panel]  →  [Estado en memoria]  →  [Exportas el archivo]  →  [Subes a GitHub]
```

El panel admin **no guarda automáticamente en GitHub**. El flujo correcto es:

### Flujo de guardado paso a paso

**1. Haz tus cambios** en el panel de administración (productos, imágenes, texto, etc.)

**2. Exporta / Respalda el archivo** desde el panel:
- Ve al botón **☁ Respaldo** (esquina del panel)
- Haz clic en **⬇ Descargar** para obtener el archivo actualizado
- El archivo se descarga con nombre versionado: `RH_backup_YYYY-MM-DD_v001.html`

**3. Sube el archivo a GitHub:**
- Renombra el archivo descargado a `index.html`
- Ve a tu repositorio: `https://github.com/elparivera/DisenosRhensambles`
- Haz clic en `index.html` → **Edit** (ícono de lápiz) → **Upload**
- O usa Git directamente:

```bash
git add index.html
git commit -m "Actualización de productos"
git push
```

**4. Espera ~2 minutos** para que GitHub Pages publique los cambios.

---

## 🗂 Estructura del repositorio

```
DisenosRhensambles/
├── index.html       ← Archivo principal (TODO el sistema en un solo archivo)
└── README.md        ← Este documento
```

---

## ☁ Integración con Google Drive (opcional)

Para habilitar respaldo automático directo a Google Drive:

1. Ve a [console.cloud.google.com](https://console.cloud.google.com)
2. Crea un proyecto nuevo
3. Activa la **Google Drive API**
4. Crea credenciales → **OAuth 2.0 Client ID** (tipo: Aplicación Web)
5. En **Orígenes autorizados** agrega: `https://elparivera.github.io`
6. Copia el **Client ID** generado
7. En el panel admin → **☁ Respaldo** → ⚙ → pega el Client ID

Una vez configurado, el botón **Subir a Drive** sube el archivo directamente a tu carpeta de Google Drive.

---

## 📦 Respaldo con Terabox

Terabox no permite subida automática desde el navegador, por lo que el flujo es manual:

1. Panel → **☁ Respaldo** → **⬇ Descargar** (descarga el archivo versionado)
2. Panel → **☁ Respaldo** → **Abrir Terabox** (abre tu carpeta)
3. Sube manualmente el archivo descargado a esa carpeta

---

## 🔄 Historial de versiones de respaldo

El sistema lleva conteo automático de respaldos. Cada archivo exportado tiene nombre único:

```
RH_backup_2025-03-12_v001.html
RH_backup_2025-03-12_v002.html
RH_backup_2025-03-15_v003.html
```

Puedes ver el historial de los últimos 8 respaldos directamente en el modal de respaldo del panel.

---

## ⚠️ Solución de problemas

### No puedo entrar al panel
- Verifica que usas exactamente: usuario `admin`, contraseña `disenosrh2024`
- Haz recarga forzada: **Ctrl + Shift + R** (Windows/Linux) o **Cmd + Shift + R** (Mac)
- Si sigue sin funcionar, abre en modo incógnito

### Los cambios no se ven en el sitio
- Asegúrate de haber subido el archivo exportado (no el original sin cambios)
- Espera 2–5 minutos después de hacer push
- Recarga la página con Ctrl+Shift+R para limpiar caché

### GitHub Pages no está activo
1. Ve a **Settings → Pages** en tu repositorio
2. En **Branch** selecciona `main` y carpeta `/ (root)`
3. Guarda y espera 2–3 minutos

---

## 📝 Notas técnicas

- El archivo `index.html` es completamente autocontenido (imágenes en base64, sin dependencias externas en CDN para el núcleo del sistema)
- El estado se serializa como JavaScript embebido entre los marcadores `__EMBEDDED_STATE_START__` y `__EMBEDDED_STATE_END__`
- Las contraseñas se guardan en texto plano dentro del estado para garantizar compatibilidad en cualquier hosting estático
- Compatible con cualquier navegador moderno (Chrome, Firefox, Edge, Safari)

---

*Diseños RH Ensambles © 2025*
