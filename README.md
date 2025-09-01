# Jellyfin Docker

Este proyecto permite desplegar un contenedor de **Jellyfin** con opciones de **branding y personalización** mediante archivos de configuración y recursos estáticos.

---

## ⚙️ Configuración de la interfaz

Toda la configuración de la apariencia se controla desde el archivo:

```
settings.json
```

Ejemplo:

```json
{
    "titulo": "Titulo",
    "colorFondo": "#fff",
    "imagenFondo": true,
    "desenfoque": 10,
    "opacidad": 0.2
}
```

## Parámetros disponibles

-   **titulo**
    Texto que aparecerá en la pestaña del navegador como título de la web.

-   **colorFondo**
    Color hexadecimal utilizado como fondo de la página.

    > ⚠️ Este valor se ignora si `imagenFondo` está en `true`.

-   **imagenFondo**

    -   `true`: se utilizará la imagen `background.png` como fondo.
    -   `false`: se usará el valor definido en `colorFondo`.

-   **desenfoque**
    Nivel de desenfoque aplicado al fondo (número entero).

-   **opacidad**
    Nivel de opacidad del fondo, entre `0.0` (transparente) y `1.0` (opaco).

---

## 🖼️ Personalización de imágenes

Para modificar favicon, logo y fondo, sustituye los archivos dentro de:

```
branding/icons/
```

Archivos a reemplazar:

-   `favicon.png` → Icono de la pestaña del navegador.
-   `logo.png` → Logo principal de la plataforma.
-   `background.png` → Imagen de fondo de la web.

### Recomendaciones

-   Mantener el **mismo formato y proporciones** que los archivos originales.
-   Editar los archivos existentes en lugar de crear nuevos con dimensiones distintas.

---

## 🚀 Cómo levantar el proyecto

1. Edita `settings.json` o reemplaza las imágenes en `branding/icons/`.
2. Inicia el contenedor de Jellyfin:

```bash
docker compose down jellyfin /* elimina el contenedor si ya existe */
docker compose up -d
```

---

## 📂 Estructura del proyecto

```
jellyfin-docker/
├── docker-compose.yml
├── branding/
│   ├── settings.json
│   ├── base.css
│   ├── index.html
│   └── icons/
│       ├── favicon.png
│       ├── logo.png
│       └── background.png
```
