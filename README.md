# WebCofontaNew — Sitio web corporativo COFONTA

Sitio web corporativo de **COFONTA, S.L.**, empresa especializada en fontanería e instalaciones con sede en Tenerife (Islas Canarias), fundada en 1986.

---

## Tecnologías

| Tecnología | Uso |
|---|---|
| HTML5 | Estructura y contenido |
| CSS3 (inline) | Estilos embebidos en cada página |
| JavaScript (vanilla) | Animaciones, formulario, cookies |
| Google Fonts | Bebas Neue, DM Sans, DM Serif Display |
| Schema.org (JSON-LD) | SEO estructurado (LocalBusiness/Plumber) |
| PWA Manifest | Instalación como app en móvil |

No se utilizan frameworks ni dependencias externas de JavaScript. El sitio es completamente estático.

---

## Estructura del proyecto

```
WebCofontaNew/
├── index.html                   # Página principal (home)
├── aviso-legal.html             # Aviso legal
├── politica-privacidad.html     # Política de privacidad
├── politica-cookies.html        # Política de cookies
├── politica-calidad.html        # Política de calidad
├── mapaoficina.html             # Mapa — Oficina de administración (Tacoronte)
├── mapatiendasauzal.html        # Mapa — Tienda El Sauzal
├── mapaalmacen.html             # Mapa — Almacén central (Tacoronte)
├── indexvieja.html              # Versión anterior (archivo, no publicada)
├── index2.html                  # Placeholder
├── google96ac7e7bc273d449.html  # Verificación Google Search Console
├── robots.txt                   # Configuración para crawlers
├── sitemap.xml                  # Mapa del sitio para SEO
├── site.webmanifest             # Manifiesto PWA
├── favicon.ico                  # Favicon principal
├── favicon-16x16.png
├── favicon-32x32.png
├── apple-touch-icon.png
├── android-chrome-192x192.png
├── android-chrome-512x512.png
├── logo_cofonta.png             # Logo principal
├── logoCofonta.jpg
├── LogocofontaLimpio.jpg        # Logo sin fondo
├── curriculum cofonta.pdf       # Dossier de empresa descargable
├── ImagenesWeb/                 # Fotografías de obras y proyectos (22 imágenes)
└── fotos cofonta/               # Fotografías de instalaciones y tienda (15 imágenes)
```

---

## Paleta de colores

| Variable CSS | Color | Uso |
|---|---|---|
| `--navy` | `#0a1628` | Fondo principal |
| `--steel` | `#1c3452` | Fondo secundario, tarjetas |
| `--blue` | `#1a56a0` | Botones CTA |
| `--sky` | `#3b82c4` | Acentos, hover, bordes |
| `--water` | `#7eb8d4` | Acento claro, highlights |
| `--gold` | `#c9a84c` | Etiquetas, separadores de sección |
| `--white` | `#f5f9fc` | Texto principal, titulares |
| `--muted` | `#8aafc8` | Texto secundario |
| `--text` | `#e8f0f7` | Cuerpo de texto |

---

## Páginas y secciones

### `index.html` — Página principal

| Sección | Descripción |
|---|---|
| **Navegación** | Fija en la parte superior con efecto frosted-glass. Incluye logo, enlaces de sección y botón CTA. |
| **Hero** | Pantalla completa con titular, subtítulo, dos CTAs y contadores animados (40+ años, 3.500+ viviendas, 15.000+ instalaciones). |
| **Servicios** | 10 tarjetas de servicio: energía solar, filtración de piscinas, grupos de presión, termos, grifería, calefacción, gas, fontanería, asesoramiento. |
| **La empresa** | Historia, política de calidad (5 principios), organizaciones asociadas (FEMETE, CONAIF, APIGASTE). |
| **Obras** | 6 proyectos destacados con imagen + listado de 14 obras adicionales. PDF del curriculum descargable. |
| **Tienda** | Información de la tienda en El Sauzal: dirección, teléfono, email, enlace al mapa. |
| **Contacto** | Ubicaciones de oficina y almacén + formulario de solicitud de presupuesto. |
| **Footer** | Año, derechos y enlaces a páginas legales. |

### Páginas legales

Todas comparten el mismo diseño que `index.html` y están enlazadas desde el footer.

- `aviso-legal.html` — Información legal de la empresa (RGPD, responsable, etc.)
- `politica-privacidad.html` — Tratamiento de datos personales
- `politica-cookies.html` — Tipos de cookies y gestión del consentimiento
- `politica-calidad.html` — Política de calidad certificada

### Páginas de mapa

Páginas independientes con mapa embebido (Google Maps) para cada ubicación:

- `mapaoficina.html` — C/ La Vera, 30 — Tacoronte (Administración)
- `mapaalmacen.html` — Almacén central — Tacoronte
- `mapatiendasauzal.html` — Tienda — El Sauzal

---

## Formulario de presupuesto

El formulario de la sección **Contacto** recoge los siguientes campos y genera un `mailto:` que abre el cliente de correo del usuario:

| Campo | Tipo | Obligatorio |
|---|---|---|
| Nombre | Texto | Sí |
| Teléfono | Tel | No |
| Email de contacto | Email | No |
| Tipo de instalación | Texto | No |
| Dirección de la instalación | Texto | No |
| Descripción del proyecto | Textarea | Sí |

El correo se envía a: `cofonta-oficina@cofonta.com`

---

## Correos de contacto

| Departamento | Email |
|---|---|
| Administración / Presupuestos | cofonta-oficina@cofonta.com |
| Almacén central | cofonta-almacen@cofonta.com |
| Tienda El Sauzal | tienda@cofonta.com |

---

## Ejecución local

Al ser un sitio estático, basta con abrir `index.html` en el navegador, o servir la carpeta con cualquier servidor local:

```bash
# Con Python
python -m http.server 8080

# Con Node.js (npx)
npx serve .
```

Luego acceder a `http://localhost:8080`

---

## Despliegue

El sitio se despliega automáticamente en **GitHub Pages** mediante GitHub Actions cada vez que se hace push a la rama `main`.

Ver workflow: [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml)

Una vez configurado en GitHub Pages (Settings → Pages → Source: GitHub Actions), el sitio estará disponible en:
`https://fabianviera.github.io/WebCofontaNew/`

---

## GitHub Actions

| Workflow | Archivo | Cuándo se ejecuta |
|---|---|---|
| Despliegue a GitHub Pages | `deploy.yml` | Push a `main` |
| Validación de HTML | `validate.yml` | Push a `main` y Pull Requests |

---

## Autor

**Fabián Viera** — Diseño y desarrollo web
COFONTA, S.L. © 2026
