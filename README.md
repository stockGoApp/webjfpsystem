# JFPSYSTEM · Landing de pre-lanzamiento (Flowtock + EatTock)

Landing page de alta conversión (CRO) para captar leads / lista de espera de los dos
productos en pre-lanzamiento de **JFPSYSTEM**: **Flowtock** (ERP en la nube) y
**EatTock** (suite para restaurantes).

Todo vive en un **único archivo** `index.html` (HTML + CSS + JS embebidos). Ábrelo
directamente en el navegador, sin servidor ni build.

```
webJfpSystem/
├── index.html      ← la landing completa (estilos y JS embebidos)
└── README.md       ← este archivo
```

---

## Cómo verla

Doble clic en `index.html`, o desde terminal:

```bash
open index.html          # macOS
```

No requiere instalación, dependencias ni conexión (salvo la fuente Inter de Google Fonts,
que tiene fallback a fuentes del sistema).

---

## Estructura de la página

1. **Navbar fija** con scroll suave y menú hamburguesa en móvil.
2. **Hero** — fondo abstracto tecnológico animado (glows + grid), título dual y botones
   *Ver Flowtock* / *Ver EatTock*. Incluye prueba social (“+15 empresas en espera”).
3. **JFPSYSTEM** — banda de confianza (equipo de arquitectos/ex-CTOs, MVP→enterprise, productos propios).
4. **Somos JFPSYSTEM (agencia)** — pitch de desarrollo a medida ultrarrápido + 3 pilares
   (⚡ velocidad real 4–8 semanas, 🎯 100% a medida, 🛡️ calidad enterprise) y CTA *“Habla con un experto”*.
5. **Flowtock** — badge *“Creado por JFPSYSTEM”*, logo + tagline, 4 beneficios, funcionalidades,
   mockup de dashboard, stats y CTA *“Quiero acceso anticipado”*.
6. **EatTock** — misma estructura, enfocada a restaurantes (POS, KDS, Food Cost, SUNAT offline).
7. **Comparativa Antes / Después** — dos tarjetas visuales, una por producto.
8. **¿Por qué JFPSYSTEM?** — 3 frases con números (76% / +40 / 100%) + testimonio simulado.
9. **Formulario de lista de espera** — select *“¿Qué buscas?”* (Flowtock / EatTock / ambos /
   desarrollo a medida urgente), nombre, email (obligatorio), checkboxes de producto (auto-sincronizados)
   y rol. Si elige *desarrollo a medida*, aparece un campo extra *“Cuéntanos tu idea”*. Sello de confianza
   (Desarrollo ágil · Seguridad enterprise · Soporte 24/5 SLA 99.9%). Validación JS + éxito sin recargar.
10. **Footer** — contacto, redes (placeholder) y copyright con año dinámico.

---

## Decisiones técnicas

- **Sin frameworks.** HTML5 + CSS3 (Grid/Flexbox) + JavaScript vanilla.
- **Mobile-first y responsive**, con breakpoints en **900px / 680px / 380px**
  (cubre 375px, 768px y 1200px).
- **Animaciones de scroll** con `IntersectionObserver` (clase `.reveal` → `.in`), con
  fallback si el navegador no lo soporta y respeto a `prefers-reduced-motion`.
- **Validación de formulario**: email obligatorio (regex básica) + al menos un producto.
  Envío **simulado** (sin backend): muestra mensaje de éxito y oculta el form. El punto
  exacto donde conectar una API real está comentado en el JS (`fetch('/api/waitlist'...)`).
- **Favicon** SVG embebido (data URI), **meta tags** description/viewport/theme-color y Open Graph.
- **Identidad de marca:**
  - Flowtock → índigo/cyan (`#5048e5` → `#06b6d4`), tono *eficiencia / control total*.
  - EatTock → ámbar/coral (`#f97316` → `#ef4444`), tono *calidez gastronómica / sin estrés*.
  - JFPSYSTEM → fondo oscuro `#0b0a1f`, look “startup serie A”.

---

## Origen del contenido (no son placeholders)

El copy se extrajo de las presentaciones reales de cada producto:

- **Flowtock** → `../Flowtock/presentacion-flowtock.html`
  (8 módulos, facturación SUNAT/GRE/PLE, kardex valorizado, multi-sucursal, métricas como
  *-30% tiempo en compras*, precios S/250/mes).
- **EatTock** → `../restaurante/docs/presentacion-ventas/deck.html`
  (18 módulos, POS/KDS, Food Cost, módulo de Calidad con muestreo, modo SUNAT offline,
  fidelización, plan desde S/169/mes, prueba 14 días).

---

## Gatillos mentales aplicados (CRO)

- **Escasez:** “Cupos limitados para el lote de lanzamiento”, “tarifa preferencial”.
- **Prueba social:** “+15 empresas ya en lista de espera”.
- **Autoridad:** JFPSYSTEM como socio tecnológico con años de experiencia y SUNAT nativo.
- **Cada producto responde a:** ¿qué problema resuelve? (beneficios), ¿por qué es único?
  (diferenciadores/funcionalidades), ¿qué pasa si no lo usas? (bloque rojo *“pain”*).

---

## Personalización rápida

| Quiero cambiar… | Dónde |
|---|---|
| Colores de marca | bloque `:root` (variables `--flow`, `--eat`, `--ink`…) |
| Textos / copy | directamente en cada `<section>` del HTML |
| Email / teléfono / redes | sección `<footer>` |
| Conectar el formulario a un backend | comentario `fetch('/api/waitlist'...)` en el `<script>` |
| Logos reales en vez de las iniciales | `.brand .mark` y `.product-logo .mark` |

---

## Pendientes para producción

- Conectar el formulario a un servicio real (Mailchimp, Brevo, Formspree, o API propia).
- Reemplazar enlaces `#` de redes sociales por URLs reales.
- Confirmar el email de contacto definitivo (ahora `helpdesk@pulsosalud.com`, placeholder).
- Añadir logos/imágenes reales de producto si se desea sustituir los mockups CSS.
