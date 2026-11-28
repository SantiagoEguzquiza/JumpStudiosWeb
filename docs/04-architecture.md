
# Arquitectura y propuesta tecnológica — Jump Studios

**Proyecto:** JumpStudiosWeb
**Versión del documento:** 1.0
**Fecha:** 26/11/2026
**Etapa:** Sprint 1
**Estado:** Stack tecnológico aprobado. Resto de la propuesta pendiente de aprobación

## 1. Objetivo

Definir las tecnologías, la arquitectura, la organización del
código y los criterios técnicos que se utilizarán durante el
desarrollo de la landing page de Jump Studios.

La solución deberá priorizar:

- Identidad visual propia.
- Rendimiento y velocidad de carga.
- Posicionamiento en motores de búsqueda.
- Adaptabilidad a diferentes dispositivos.
- Transiciones y animaciones personalizadas.
- Facilidad de mantenimiento.
- Escalabilidad.
- Desarrollo colaborativo.

## 2. Alcance

El proyecto consiste en una landing page corporativa orientada
principalmente a presentar los servicios de desarrollo web
y software a medida de Jump Studios.

También incluirá una sección secundaria dedicada a los
servicios relacionados con hardware.

La sección de proyectos se denominará "Destacados" e incluirá
inicialmente los siguientes trabajos:

- Wis Barbers.
- Peninsula Constructora.
- Provider, cuando esté disponible.

La primera versión no requerirá autenticación, base de datos,
panel de administración ni un backend independiente.

## 3. Evaluación tecnológica

Se consideraron las siguientes alternativas:

### 3.1. HTML, CSS y JavaScript

Permite desarrollar una landing ligera con pocas dependencias.
Sin embargo, requiere establecer manualmente una arquitectura
para organizar componentes y facilitar el mantenimiento.

### 3.2. Vite + React

Proporciona un entorno de desarrollo rápido y una arquitectura
basada en componentes.

La configuración convencional genera una aplicación renderizada
principalmente en el cliente. La generación previa de HTML
requiere configuración o herramientas adicionales.

### 3.3. Astro

Framework orientado a sitios centrados en contenido.
Permite generar páginas estáticas y utilizar JavaScript
únicamente en los componentes que necesitan interactividad.

Es una alternativa adecuada para una landing corporativa.

### 3.4. Next.js

Framework basado en React que permite combinar generación
estática, renderizado en servidor y componentes interactivos.

Incluye herramientas para gestionar metadatos, rutas,
fuentes y recursos visuales.

Permite ampliar las funcionalidades del sitio en el futuro
sin sustituir el framework principal.

### 3.5. Decisión propuesta

Se propone utilizar Next.js con App Router y TypeScript.

La decisión se fundamenta en su arquitectura modular,
herramientas integradas y posibilidades de crecimiento.

La primera versión priorizará la generación estática,
evitando funcionalidades de servidor que no sean necesarias.

Decisión aprobada para el Sprint 2: Next.js con App Router,
React, TypeScript y CSS Modules.

## 4. Stack tecnológico

| Tecnología | Finalidad |
|---|---|
| Next.js | Framework principal |
| React | Desarrollo de componentes |
| TypeScript | Lenguaje de programación |
| CSS Modules | Estilos de componentes |
| CSS Custom Properties | Variables del sistema visual |
| Motion | Animaciones avanzadas, si se requieren |
| Node.js | Entorno de desarrollo |
| npm | Gestión de dependencias |
| ESLint | Análisis estático del código |
| Prettier | Formato del código |
| Git | Control de versiones |
| GitHub | Repositorio y colaboración |

Se utilizarán versiones estables y compatibles.

La versión de Node.js se fijará durante la inicialización
del proyecto mediante un archivo .nvmrc.

Las dependencias quedarán registradas en package.json
y package-lock.json.

No se incorporarán librerías adicionales sin una
justificación técnica.

## 5. Arquitectura general

El sitio utilizará una arquitectura frontend modular.

Next.js será responsable de organizar las rutas, generar
el HTML y gestionar los componentes de React.

Se utilizarán Server Components de forma predeterminada.

Los Client Components se reservarán para aquellos elementos
que necesiten:

- Manejo de eventos.
- Estados interactivos.
- Acceso a APIs del navegador.
- Animaciones que requieran JavaScript.

La primera versión utilizará contenido local almacenado
dentro del repositorio.

No se realizarán solicitudes a una base de datos.

## 6. Estructura de directorios

Se propone conservar la estructura existente del repositorio
y ampliarla durante la implementación.

JumpStudiosWeb/
├── docs/
│   └── 04-architecture.md
├── design/
├── content/
├── public/
│   └── assets/
│       ├── images/
│       ├── logos/
│       ├── icons/
│       └── fonts/
├── src/
│   ├── app/
│   │   ├── layout.tsx
│   │   └── page.tsx
│   ├── components/
│   │   ├── layout/
│   │   │   ├── Header/
│   │   │   └── Footer/
│   │   ├── sections/
│   │   │   ├── Hero/
│   │   │   ├── Services/
│   │   │   ├── Featured/
│   │   │   ├── Hardware/
│   │   │   ├── About/
│   │   │   └── Contact/
│   │   └── ui/
│   ├── styles/
│   │   ├── globals.css
│   │   └── tokens.css
│   ├── hooks/
│   └── lib/
├── AGENTS.md
├── README.md
├── package.json
├── package-lock.json
├── next.config.ts
├── tsconfig.json
├── .nvmrc
└── .gitignore

Los archivos y directorios nuevos se crearán únicamente
cuando sean necesarios.

### 6.1. Responsabilidades

- docs: documentación técnica y planificación.
- design: referencias visuales y propuestas de diseño.
- content: textos y datos estructurados de la landing.
- public/assets: recursos gráficos y tipográficos.
- src/app: rutas, estructura general y metadatos.
- src/components/layout: elementos estructurales del sitio.
- src/components/sections: secciones independientes.
- src/components/ui: elementos visuales reutilizables.
- src/styles: estilos globales y variables visuales.
- src/hooks: lógica interactiva reutilizable.
- src/lib: funciones auxiliares.

## 7. Arquitectura de componentes

Cada sección de la landing deberá implementarse como
un componente independiente.

Los componentes tendrán sus propios archivos de estilos
cuando corresponda.

Ejemplo:

Hero/
├── Hero.tsx
└── Hero.module.css

Se evitará concentrar toda la implementación en page.tsx.

La página principal será responsable de organizar las
secciones, no de implementar toda su lógica interna.

Los componentes deberán ser reutilizables cuando exista
una necesidad real de reutilización.

No se crearán abstracciones innecesarias.

## 8. Gestión de estilos

Se utilizará CSS Modules para los estilos específicos
de cada componente.

Los estilos globales se reservarán para:

- Normalización de estilos.
- Configuración tipográfica.
- Comportamiento general del documento.
- Variables del sistema de diseño.
- Reglas globales de accesibilidad.

El archivo tokens.css centralizará:

- Colores.
- Tipografías.
- Tamaños de texto.
- Espaciados.
- Bordes.
- Duraciones de animación.
- Curvas de aceleración.

Los valores visuales se definirán a partir del manual
de identidad de Jump Studios y del sistema de diseño
aprobado por el equipo.

No se utilizarán plantillas visuales prediseñadas ni
frameworks de componentes completos.

## 9. Animaciones y transiciones

Las animaciones serán un elemento importante de la
experiencia visual del sitio.

Se establece la siguiente estrategia técnica:

### 9.1. CSS nativo

Será la primera opción para:

- Transiciones simples.
- Estados hover y focus.
- Cambios de opacidad.
- Transformaciones.
- Animaciones que no requieran lógica compleja.

### 9.2. Motion

Se evaluará su incorporación cuando las animaciones
seleccionadas requieran:

- Coordinación entre componentes.
- Secuencias complejas.
- Animaciones vinculadas al desplazamiento.
- Transiciones dependientes del estado de la interfaz.

No se instalará esta dependencia hasta conocer los
requerimientos concretos de las animaciones.

### 9.3. Criterios generales

Las animaciones deberán:

- Mantener una finalidad visual clara.
- Evitar interferir con la navegación.
- Funcionar correctamente en dispositivos móviles.
- Priorizar propiedades como transform y opacity.
- Respetar la preferencia prefers-reduced-motion.
- Evitar bloquear el desplazamiento de la página.
- Mantener el contenido accesible sin animaciones.
- Evitar dependencias innecesarias.

La selección estética de los efectos y las transiciones
se realizará durante la etapa de diseño.

## 10. Gestión de recursos visuales

Se utilizarán preferentemente:

- SVG para logotipos e iconos cuando estén disponibles.
- WebP o AVIF para imágenes fotográficas.
- WOFF2 para tipografías locales compatibles.

Las tipografías deberán respetar las licencias de uso.

Las imágenes deberán tener dimensiones adecuadas y
comprimirse antes de incorporarse al sitio.

Los recursos gráficos secundarios podrán utilizar
carga diferida cuando corresponda.

Si se utiliza la exportación estática de Next.js, las
imágenes deberán optimizarse previamente o mediante
un cargador compatible con ese modo de despliegue.

No se incorporarán recursos externos sin autorización
o sin comprobar sus condiciones de uso.

## 11. Gestión del contenido

Los textos comerciales y la información de los proyectos
se mantendrán separados de la lógica de presentación.

La sección Destacados utilizará datos estructurados,
de forma que incorporar nuevos proyectos no requiera
reescribir el componente.

Los datos podrán incluir, según el diseño aprobado:

- Nombre del proyecto.
- Descripción.
- Imagen.
- Enlace.
- Categoría.

No se publicarán proyectos, métricas, testimonios ni
información comercial que no hayan sido confirmados.

Provider se incorporará cuando exista material aprobado.

## 12. Adaptabilidad y accesibilidad

El sitio se desarrollará con un enfoque mobile-first.

Deberá verificarse su funcionamiento en:

- Teléfonos móviles.
- Tablets.
- Computadoras portátiles.
- Monitores de escritorio.

Se utilizará HTML semántico y se procurará cumplir
los criterios aplicables de WCAG 2.2 nivel AA.

Se prestará especial atención a:

- Contraste de colores.
- Navegación mediante teclado.
- Indicadores de foco.
- Textos alternativos.
- Jerarquía de encabezados.
- Reducción de movimiento.
- Legibilidad del contenido.

## 13. SEO

Se utilizará la Metadata API de Next.js para gestionar
los metadatos del sitio.

Se contempla la incorporación de:

- Título y descripción.
- Metadatos Open Graph.
- Favicon.
- URL canónica.
- Sitemap.
- Robots.txt.

Los valores definitivos se establecerán cuando estén
confirmados el contenido comercial y el dominio.

El contenido principal deberá estar disponible en el
HTML generado, sin depender exclusivamente de JavaScript.

## 14. Rendimiento

El sitio deberá mantener un equilibrio entre impacto
visual y velocidad de carga.

Se evitará:

- JavaScript innecesario.
- Dependencias redundantes.
- Imágenes de tamaño excesivo.
- Animaciones que provoquen bloqueos.
- Carga de recursos que no se utilicen.

Se establecen como objetivos iniciales:

- Lighthouse Performance: 90 puntos o más.
- Lighthouse Accessibility: 95 puntos o más.
- Lighthouse SEO: 95 puntos o más.
- LCP: igual o inferior a 2,5 segundos.
- INP: igual o inferior a 200 milisegundos.
- CLS: igual o inferior a 0,1.

Los resultados de Lighthouse se comprobarán sobre
una compilación de producción.

Los Core Web Vitals se evaluarán con datos reales de
usuarios cuando estén disponibles.

Estos valores constituyen objetivos técnicos,
no resultados garantizados.

## 15. Desarrollo colaborativo

El repositorio utilizará Git y GitHub.

La rama main representará la versión estable del proyecto.

Cada desarrollador trabajará en ramas independientes
según las tareas asignadas.

Convenciones propuestas:

- feature/: nuevas funcionalidades.
- fix/: corrección de errores.
- docs/: documentación.
- refactor/: reorganización del código.

Los cambios se integrarán mediante Pull Requests
y deberán ser revisados por el otro desarrollador.

Se evitará modificar simultáneamente los mismos
archivos sin coordinación previa.

Los cambios que afecten a la arquitectura, dependencias
o estilos globales deberán ser comunicados al equipo.

## 16. Uso de agentes de inteligencia artificial

Las herramientas de IA actuarán como asistentes
durante el desarrollo.

El archivo AGENTS.md centralizará las reglas comunes
que deberán respetar ambos desarrolladores y agentes.

Los agentes deberán:

- Leer la documentación antes de modificar el proyecto.
- Respetar el sistema de diseño.
- Limitar los cambios a la tarea asignada.
- Evitar instalar dependencias sin autorización.
- No inventar requisitos ni información comercial.
- No sustituir componentes aprobados innecesariamente.
- Informar sobre errores y decisiones técnicas.

Todo código generado deberá ser revisado y verificado.

## 17. Control de calidad

Antes de integrar cambios se deberá comprobar:

- Compilación correcta del proyecto.
- Ausencia de errores de TypeScript.
- Cumplimiento de las reglas de ESLint.
- Ausencia de errores en la consola del navegador.
- Funcionamiento de los enlaces.
- Adaptabilidad a diferentes resoluciones.
- Comportamiento correcto de las animaciones.

Se propone configurar GitHub Actions para automatizar
las comprobaciones de compilación, tipos y linting.

Los comandos definitivos se documentarán en README.md
una vez inicializado el proyecto.

## 18. Seguridad

No se almacenarán contraseñas, claves de API ni
credenciales dentro del repositorio.

Si se incorporan variables de entorno, los archivos
que contengan información sensible serán excluidos
mediante .gitignore.

El sitio deberá publicarse mediante HTTPS.

Se revisarán periódicamente las dependencias y se
evitarán librerías sin mantenimiento.

## 19. Despliegue

Se priorizará una solución de alojamiento compatible
con sitios generados estáticamente.

La primera versión podrá utilizar la exportación
estática de Next.js si no requiere funciones de servidor.

El proveedor de alojamiento y su configuración
se definirán en la documentación de despliegue.

Se evaluarán:

- Costos de alojamiento.
- Compatibilidad técnica.
- Uso comercial permitido.
- Dominio personalizado.
- Certificado HTTPS.
- Integración con GitHub.
- Facilidad de mantenimiento.

No se establece todavía un proveedor definitivo.

## 20. Decisiones pendientes

- Aprobación del sistema de diseño.
- Selección de animaciones y transiciones.
- Necesidad de incorporar Motion.
- Definición de los canales de contacto.
- Confirmación del proveedor de alojamiento.
- Confirmación del dominio.
- Aprobación del contenido comercial.
- Definición de los requisitos de analítica web.

## 21. Referencias técnicas

- https://nextjs.org/docs
- https://nextjs.org/docs/app/guides/static-exports
- https://react.dev
- https://www.typescriptlang.org/docs/
- https://vite.dev/guide/
- https://docs.astro.build/
- https://motion.dev/docs/react
- https://developer.mozilla.org/
- https://www.w3.org/TR/WCAG22/

## 22. Conclusión

La arquitectura propuesta busca garantizar una base
técnica sólida sin introducir complejidad innecesaria.

Next.js, TypeScript y CSS Modules permitirán desarrollar
una landing personalizada, mantenible y ampliable.

Las decisiones técnicas deberán acompañar los objetivos
comerciales y visuales de Jump Studios, evitando que
las herramientas condicionen la identidad del sitio.
