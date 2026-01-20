# 📚 Guía de Publicación de Eventos para TecniLauncher

Bienvenido a la guía oficial para creadores de eventos. Este documento explica cómo alojar y publicar tus eventos (mods, mapas, configs) para que sean accesibles desde **TecniLauncher**.

## 🛠️ Prerrequisitos

Antes de empezar, asegúrate de tener:
1.  **TecniCreateTools (TCT):** La herramienta para generar la carpeta del evento (`Output`).
2.  Una cuenta en **GitHub** y/o **GitLab**.

---

## 🚦 Paso 1: El Semáforo de Decisión

Dependiendo del tamaño total de tu evento o de tus archivos individuales, debes elegir dónde alojarlo.

| Ruta | Plataforma | ¿Cuándo usarla? | Límite de Archivo | Dificultad |
| :--- | :--- | :--- | :--- | :--- |
| **A** | **GitHub** | Eventos ligeros, mods técnicos, actualizaciones pequeñas. | **Máx 25 MB** por archivo | ⭐ Fácil |
| **B** | **GitLab** | Eventos pesados (Pixelmon, Cobblemon), ResourcePacks HD, música. | **Sin límite práctico** (Git LFS) | ⭐⭐ Media |

---

## 🟢 Ruta A: GitHub (Para Eventos Ligeros)
*Sigue este camino si ningún archivo de tu evento supera los 25MB.*

1.  **Crea un Repositorio:**
    * Ve a [github.com/new](https://github.com/new).
    * Ponle nombre a tu evento.
    * **IMPORTANTE:** Marca la visibilidad como **Public**.
    * Crea el repositorio.

2.  **Sube los Archivos:**
    * En tu nuevo repositorio, haz clic en **Add file** > **Upload files**.
    * Arrastra la carpeta completa de tu evento (generada por TCT).
    * Espera a que carguen y haz clic en el botón verde **Commit changes**.

3.  **Obtén el Link Maestro:**
    * Navega dentro de las carpetas hasta encontrar el archivo `evento_master.json`.
    * Haz clic en el botón **Raw** (arriba a la derecha del código).
    * Copia la URL del navegador.
    * **[Ve al Paso Final](#-paso-final-conectar-al-launcher)**.

---

## 🔴 Ruta B: GitLab (Para Eventos Pesados)
*Sigue este camino si tienes archivos grandes (+25MB). GitLab permite subir gigabytes de datos sin problemas usando las herramientas adecuadas.*

### 1. Preparación del Entorno (En la Web)
GitLab organiza los proyectos en "Grupos". Para que tu evento sea accesible, **el Grupo debe ser Público**.

1.  Ve a [gitlab.com](https://gitlab.com).
2.  En el menú, ve a **Groups** > **New Group** > **Create group**.
    * **Nombre:** El nombre de tu Studio o Equipo.
    * **Visibility Level:** Marca **Public** (Obligatorio).
3.  Dentro del Grupo, haz clic en **New Project** > **Create blank project**.
    * **Nombre:** El nombre del evento.
    * **Visibility:** Marca **Public**.

### 2. Herramientas de Subida
No uses la web para subir archivos gigantes (se colgará). Usaremos **GitHub Desktop** (compatible con GitLab).

1.  Descarga e instala [GitHub Desktop](https://desktop.github.com/).
2.  Ve a **File** > **Clone Repository**.
3.  Pega la URL HTTPS de tu proyecto de GitLab (ej: `https://gitlab.com/MiStudio/EventoZombie.git`).
4.  Haz clic en **Clone**.

> **🔐 ¿Te pide contraseña y falla?**
> GitLab ya no usa tu contraseña de inicio de sesión para aplicaciones externas. Necesitas un **Token**:
> 1. Ve a GitLab > User Settings (tu foto) > **Access Tokens**.
> 2. Crea un nuevo token (marca todas las casillas de permisos).
> 3. **Copia el código que empieza por `glpat-...`**.
> 4. Usa ese código como contraseña en GitHub Desktop.

### 3. Subir los Archivos
1.  En GitHub Desktop, haz clic en el botón **Show in Explorer** (Mostrar en Explorador).
2.  Se abrirá una carpeta vacía. **Copia y Pega** ahí dentro la carpeta `Output` que generó la herramienta TCT.
3.  Vuelve a GitHub Desktop. Verás todos tus archivos listados en verde.
4.  **Hacer Commit (Guardar):**
    * Abajo a la izquierda, escribe un título (ej: "Versión 1.0").
    * Haz clic en el botón azul **Commit to main**.
5.  **Hacer Push (Subir):**
    * Haz clic en el botón **Push origin** (arriba a la derecha).
    * *Espera a que termine la barra de carga.*

### 4. Obtener el Link Maestro
1.  Vuelve a tu proyecto en la web de GitLab.
2.  Entra en la carpeta del evento hasta ver `evento_master.json`.
3.  Haz clic en el botón **Open Raw** (icono de descarga 📥 a la derecha).
4.  Copia la URL del navegador.

---

## 🏁 Paso Final: Conectar al Launcher

Independientemente de si usaste GitHub o GitLab, ahora tienes un **Link Raw** que apunta a tu `evento_master.json`.

1.  Envía este link al Administrador de **TecniLauncher**.
2.  El administrador lo agregará al archivo `index_eventos.json` en el repositorio principal.
3.  **¡Listo!** El evento aparecerá automáticamente en el Launcher de todos los jugadores.

---

## ❓ Solución de Problemas Comunes

**El Launcher da error "404 Not Found" al intentar descargar.**
* Verifica que el repositorio (y el Grupo en GitLab) esté en modo **Public**.
* Asegúrate de que el link copiado sea el **Raw** (debe empezar por `raw.githubusercontent...` o `gitlab.com/.../raw/...`).

**GitHub Desktop pide credenciales en bucle.**
* Tu contraseña normal no funciona. Debes generar un **Access Token** en tu perfil de GitLab y usarlo como contraseña.

**Error al subir en GitHub Web: "File is too big".**
* Estás intentando subir un archivo de más de 25MB por la web. Debes usar la **Ruta B (GitLab + GitHub Desktop)**.
