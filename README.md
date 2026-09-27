# 🎵 Retrophonic Digital Turntable

Tocadiscos digital interactivo basado en **códigos QR**, desarrollado como proyecto académico. El sistema utiliza la cámara del dispositivo para leer una imagen y reproducir automáticamente la melodía asociada desde archivos MP3 almacenados en el repositorio.

## 📌 Descripción

El funcionamiento del sistema es deliberadamente simple:

```text
Código QR
    ↓
melodia_01
    ↓
./audio/melodia_01.mp3
    ↓
Reproducción
```

Cada código QR contiene únicamente el identificador de una melodía. El identificador coincide con el nombre del archivo de audio correspondiente.

El proyecto está implementado como una aplicación web estática y puede ser desplegado mediante **GitHub Pages**.

---

## 📁 Estructura del repositorio

La estructura esperada del repositorio es:

```text
retrophonic/
│
├── index.html
├── README.md
│
└── audio/
    ├── melodia_01.mp3
    ├── melodia_02.mp3
    ├── melodia_03.mp3
    ├── melodia_04.mp3
    ├── melodia_05.mp3
    ├── melodia_06.mp3
    ├── melodia_07.mp3
    ├── melodia_08.mp3
    ├── melodia_09.mp3
    └── melodia_10.mp3
```

No es necesario que las diez melodías existan. El sistema está preparado para diez identificadores, pero solamente reproducirá los archivos que realmente estén presentes en la carpeta `audio`.

---

## 🔲 Sistema de códigos QR

Los códigos QR deben contener **únicamente** el identificador de la melodía.

### Ejemplo

El QR:

```text
melodia_01
```

corresponde al archivo:

```text
audio/melodia_01.mp3
```

De igual manera:

| Código QR | Archivo de audio |
|---|---|
| `melodia_01` | `audio/melodia_01.mp3` |
| `melodia_02` | `audio/melodia_02.mp3` |
| `melodia_03` | `audio/melodia_03.mp3` |
| `melodia_04` | `audio/melodia_04.mp3` |
| `melodia_05` | `audio/melodia_05.mp3` |
| `melodia_06` | `audio/melodia_06.mp3` |
| `melodia_07` | `audio/melodia_07.mp3` |
| `melodia_08` | `audio/melodia_08.mp3` |
| `melodia_09` | `audio/melodia_09.mp3` |
| `melodia_10` | `audio/melodia_10.mp3` |

Los códigos QR pueden generarse con cualquier aplicación o herramienta externa compatible.

---

## 🎛️ Funcionamiento

1. El usuario abre la aplicación web.
2. Se habilita el acceso a la cámara.
3. La cámara detecta un código QR.
4. El sistema obtiene el texto contenido en el QR.
5. Se comprueba si el identificador corresponde a una melodía configurada.
6. Si existe, se construye la ruta:

```text
./audio/<identificador>.mp3
```

7. El archivo MP3 se carga y comienza la reproducción.
8. La interfaz actualiza el estado del tocadiscos y muestra la melodía seleccionada.

### QR no reconocido

Si se escanea un código que no corresponde a una melodía configurada, el sistema muestra un mensaje de error y no genera ni reproduce ninguna melodía alternativa.

---

## 🎼 Agregar una nueva melodía

Para agregar una melodía dentro de las diez posiciones disponibles:

### 1. Agregar el archivo

Copiar el archivo MP3 dentro de:

```text
audio/
```

Por ejemplo:

```text
audio/melodia_07.mp3
```

### 2. Generar el QR

Crear un código QR cuyo contenido sea exactamente:

```text
melodia_07
```

### 3. Subir los cambios a GitHub

Una vez agregado el archivo, realizar el commit correspondiente y esperar a que GitHub Pages actualice el sitio.

No es necesario modificar el código JavaScript mientras se mantenga la convención de nombres:

```text
melodia_##.mp3
```

---

## 🌐 Publicación mediante GitHub Pages

GitHub Pages permite publicar sitios web estáticos directamente desde un repositorio de GitHub. Para este proyecto resulta adecuado porque la aplicación está compuesta por HTML, CSS y JavaScript, junto con los archivos de audio necesarios.

### 1. Crear el repositorio

Crear un nuevo repositorio en GitHub.

Se recomienda utilizar un nombre relacionado con el proyecto, por ejemplo:

```text
retrophonic-digital-turntable
```

El repositorio puede ser público. GitHub Pages está disponible para repositorios públicos en GitHub Free. 

### 2. Subir los archivos

El repositorio debe contener como mínimo:

```text
index.html
README.md
audio/
```

Dentro de `audio/` deben encontrarse los archivos MP3.

### 3. Configurar GitHub Pages

En el repositorio:

```text
Settings
   ↓
Pages
```

En **Build and deployment**:

```text
Source: Deploy from a branch
```

Seleccionar:

```text
Branch: main
Folder: / (root)
```

Después seleccionar:

```text
Save
```

GitHub permite publicar directamente desde una rama y desde la raíz del repositorio, que es la configuración adecuada para este proyecto. 

### 4. Obtener la URL

Después de la configuración, GitHub mostrará la dirección del sitio dentro de:

```text
Settings → Pages
```

Para un repositorio de proyecto, la dirección normalmente tendrá la forma:

```text
https://USUARIO.github.io/NOMBRE-DEL-REPOSITORIO/
```

GitHub documenta este formato como el utilizado para los **Project sites**. 

La primera publicación o una actualización puede tardar algunos minutos en estar disponible. GitHub indica que los cambios pueden tardar hasta aproximadamente 10 minutos en publicarse. 

---

## 📱 Uso desde un teléfono

Una vez publicado el proyecto:

1. Abrir la URL de GitHub Pages.
2. Permitir el acceso a la cámara cuando el navegador lo solicite.
3. Apuntar la cámara hacia uno de los códigos QR.
4. Esperar a que el sistema reconozca el código.
5. La melodía correspondiente comenzará a reproducirse.

La aplicación debe ejecutarse mediante HTTPS, como el proporcionado por GitHub Pages, para facilitar el acceso a las funcionalidades del navegador que requieren un contexto seguro.

---

## 🔊 Archivos de audio

Los archivos de audio forman parte del contenido publicado del proyecto.

Se recomienda utilizar nombres simples y consistentes:

```text
melodia_01.mp3
melodia_02.mp3
...
melodia_10.mp3
```

Evitar nombres como:

```text
Melodía favorita.mp3
canción nueva final.mp3
audio definitivo 2.mp3
```

porque los espacios, caracteres especiales y diferencias de mayúsculas/minúsculas pueden generar problemas de compatibilidad o rutas incorrectas.

---

## ⚠️ Consideraciones sobre los archivos MP3

GitHub Pages publica el contenido del sitio en Internet. Por esta razón, cualquier archivo MP3 incluido en el repositorio y utilizado por la página debe considerarse públicamente accesible.

Si las grabaciones utilizadas tienen restricciones de derechos de autor, debe verificarse que su publicación y distribución mediante el repositorio y GitHub Pages estén permitidas.

---

## 🧩 Tecnologías utilizadas

- **HTML5** — estructura de la aplicación.
- **CSS / Tailwind CSS** — interfaz gráfica y estilos.
- **JavaScript** — lógica del tocadiscos y lectura de códigos QR.
- **Tone.js** — reproducción y procesamiento de audio en el navegador.
- **html5-qrcode** — lectura de códigos QR mediante la cámara.
- **Font Awesome** — iconografía de la interfaz.
- **GitHub Pages** — alojamiento de la aplicación web.

---

## 🛠️ Solución de problemas

### El QR se detecta pero no reproduce la canción

Comprobar que:

1. El QR contiene exactamente, por ejemplo:

```text
melodia_01
```

2. Existe el archivo:

```text
audio/melodia_01.mp3
```

3. El nombre del archivo coincide exactamente.
4. El archivo fue subido correctamente al repositorio.
5. La página publicada corresponde a la versión actual del repositorio.

### Aparece "QR no reconocido"

El texto leído por la cámara no coincide con ninguno de los identificadores configurados:

```text
melodia_01
melodia_02
...
melodia_10
```

Verificar el contenido del QR.

### La cámara no funciona

Comprobar que:

- El navegador tiene permiso para utilizar la cámara.
- El sitio se está ejecutando desde una URL HTTPS.
- Se está utilizando un navegador compatible.
- No existe otra aplicación utilizando la cámara simultáneamente.

### Se actualizó un archivo pero la página sigue mostrando la versión anterior

GitHub Pages puede tardar algunos minutos en desplegar los cambios. También puede ser necesario actualizar la página o limpiar la caché del navegador.

---

## 📄 Licencia

Este proyecto fue desarrollado con fines académicos.

Si el proyecto se distribuye públicamente, se recomienda definir explícitamente una licencia para el código fuente y verificar los derechos correspondientes de cualquier contenido multimedia incluido.

---

## 👤 Proyecto

**Retrophonic Digital Turntable**

Proyecto académico — Sistema de reproducción musical mediante códigos QR.
