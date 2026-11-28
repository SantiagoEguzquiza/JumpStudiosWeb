# Sistema de diseño — Jump Studios

**Proyecto:** JumpStudiosWeb
**Versión del documento:** 1.0
**Fecha:** 27/11/2026
**Etapa:** Sprint 1
**Estado:** Base para la primera implementación. Sujeto a rediseño iterativo.

## 1. Objetivo

Definir los valores visuales y las reglas de uso que se
implementarán en src/styles/tokens.css y en los componentes
(ver docs/04-architecture.md, sección 8).

La dirección artística se describe en docs/07-art-direction.md.

## 2. Identidad cromática

| Color | HEX |
|---|---|
| Jump Midnight | #18222B |
| Jump Green | #02BF60 |
| Jump White | #FFFFFF |
| Jump Black | #000000 |

Proporciones orientativas del manual de identidad:

- 60% Midnight.
- 25% White.
- 10% Green.
- 5% Black.

Estas proporciones son orientativas. Se mantiene el tema
híbrido (sección 3), aunque el contenido principal en contexto
claro modifique el reparto entre Midnight y White.

### 2.1. Contraste

Relaciones de contraste calculadas según WCAG 2.2:

| Combinación | Contraste | Uso |
|---|---|---|
| White sobre Midnight | 16,12:1 | Texto en contexto oscuro |
| Midnight sobre White | 16,12:1 | Texto en contexto claro |
| Green sobre Midnight | 6,62:1 | Acento y texto en contexto oscuro |
| Midnight sobre Green | 6,62:1 | Texto de botones verdes |
| Black sobre Green | 8,62:1 | Texto de botones verdes |
| White sobre Green | 2,44:1 | No permitido |
| Green sobre White | 2,44:1 | No permitido para texto ni indicadores |

Reglas derivadas:

- Utilizar texto oscuro (Midnight o Black) sobre botones verdes.
  Evitar texto blanco sobre verde.
- En fondos blancos, textos y enlaces se mostrarán en Midnight.
  El verde no se utilizará como color de texto, de enlaces ni
  como único indicador de foco o estado, porque no alcanza
  3:1 sobre blanco.
- En fondos blancos, el indicador de foco será Midnight.
  En fondos Midnight, será Green (6,62:1) o White (16,12:1).
- En contexto claro, un botón verde sobre fondo blanco tiene
  un contraste de borde de 2,44:1. Si el relleno es necesario
  para identificar el control, se añadirá un borde de 1 px
  con contraste suficiente. Validar durante la implementación.

## 3. Temas

La web contará en el futuro con tres temas:

- Híbrido (predeterminado).
- Oscuro.
- Claro.

Durante la primera implementación se trabajará
exclusivamente con el tema híbrido:

- Header, Hero y cierre (Contacto y Footer): contexto oscuro.
- Contenido principal (Servicios, Destacados, Hardware,
  Nosotros): contexto claro.

### 3.1. Variables semánticas

Los componentes utilizarán únicamente variables semánticas,
nunca valores HEX directos.

| Variable | Finalidad | Contexto oscuro | Contexto claro |
|---|---|---|---|
| --color-bg | Fondo de la sección | Midnight | White |
| --color-surface | Superficies diferenciadas | Black | White |
| --color-text | Texto principal | White | Midnight |
| --color-text-muted | Texto secundario | White al 72% (8,92:1) | Midnight al 72% (6,38:1) |
| --color-accent | Acento y acción principal | Green | Green (solo rellenos, ver 2.1) |
| --color-on-accent | Texto sobre acento | Midnight | Midnight |
| --color-border | Bordes de 1 px | White al 16% | Midnight al 16% |
| --color-grid | Líneas de grilla visibles | White al 8% | Midnight al 8% |

Los valores con transparencia derivan de la paleta oficial y
deberán validarse visualmente. Los bordes de controles
interactivos (por ejemplo, campos de formulario) requieren
un contraste mínimo de 3:1; en esos casos se utilizará
--color-text o un valor validado.

La superficie del contexto claro queda pendiente de
definición: la paleta no incluye un gris claro y no se
incorporarán colores fuera del manual sin aprobación.

### 3.2. Contextos cromáticos por sección

Cada sección declara su contexto y redefine las variables
semánticas. Los componentes se reutilizan sin cambios en
cualquier contexto.

Ejemplo orientativo (no es código del proyecto):

```css
:root {
  --jump-midnight: #18222b;
  --jump-green: #02bf60;
  --jump-white: #ffffff;
  --jump-black: #000000;
}

[data-context="dark"] {
  --color-bg: var(--jump-midnight);
  --color-text: var(--jump-white);
  --color-accent: var(--jump-green);
  --color-on-accent: var(--jump-midnight);
  /* ... */
}

[data-context="light"] {
  --color-bg: var(--jump-white);
  --color-text: var(--jump-midnight);
  /* ... */
}
```

Los temas futuros se aplicarán mediante un atributo en el
elemento raíz (por ejemplo, data-theme="dark"), que
determinará el contexto asignado a cada sección. El tema
híbrido no requiere atributo.

## 4. Tipografía

### 4.1. Familias

- Principal: Lato. Pesos 400, 700 y 900.
- Complementaria: IBM Plex Mono (valor inicial, sujeto a
  validación) para etiquetas técnicas, numeraciones y
  diagramas. No se utilizará en párrafos.

Los pesos de IBM Plex Mono y el método de carga de ambas
fuentes se definirán durante la implementación, comprobando
sus licencias de uso.

### 4.2. Escala

| Estilo | Escritorio | Móvil | Valor fluido propuesto |
|---|---|---|---|
| H1 | 80 px | 42 px | clamp(2.625rem, 1.789rem + 3.568vw, 5rem) |
| H2 | 48 px | 32 px | clamp(2rem, 1.648rem + 1.502vw, 3rem) |
| H3 | 28 px | 24 px | clamp(1.5rem, 1.412rem + 0.3756vw, 1.75rem) |
| Introducción | 20 px | 18 px | clamp(1.125rem, 1.081rem + 0.1878vw, 1.25rem) |
| Párrafos | 16 px | 16 px | 1rem |
| Botones | 16 px | 16 px | 1rem |
| Etiquetas técnicas | 12 px | 12 px | 0.75rem |

Los valores fluidos interpolan entre un viewport de 375 px
y 1440 px, con una base de 16 px. Se expresan en rem para
respetar el tamaño de texto configurado por el usuario.

Interlineados, pesos por estilo y espaciado entre letras se
ajustarán durante la primera implementación.

## 5. Grilla y espaciado

### 5.1. Grilla

Valores iniciales, sujetos a validación durante la
implementación:

| Dispositivo | Viewport | Columnas | Margen lateral |
|---|---|---|---|
| Móvil | Menor a 768 px | 4 | 20 px |
| Tablet | 768–1023 px | 8 | 32 px |
| Escritorio | 1024 px o más | 12 | 64 px |

- Breakpoints: 768 y 1024 px.
- Ancho máximo de contenido: 1440 px.
- Separación entre columnas: 24 px, adaptable.

La grilla se utilizará para generar composiciones variadas y
asimétricas, evitando una sucesión monótona de tarjetas.

### 5.2. Separación entre secciones

| Dispositivo | Separación |
|---|---|
| Móvil | 64 px |
| Tablet | 96 px |
| Escritorio | 96–144 px |

Valor fluido propuesto para escritorio (de 1024 a 1440 px):
clamp(6rem, -1.385rem + 11.54vw, 9rem).

Valores iniciales, sujetos a validación durante la
implementación.

### 5.3. Escala de espaciado

4, 8, 12, 16, 24, 32, 48, 64, 96 y 128 px.

No se utilizarán valores fuera de la escala sin una
justificación.

## 6. Componentes

### 6.1. Criterios generales

- Bordes de 1 px.
- Radios de esquina de 0 a 4 px.
- Botones de al menos 48 px de altura.
- Sin sombras, salvo necesidad funcional.
- Navegación completa mediante teclado.
- Contraste adecuado según WCAG 2.2 nivel AA.

### 6.2. Estados

Todos los componentes interactivos definirán:

| Estado | Criterio |
|---|---|
| Default | Estado de reposo |
| Hover | Cambio visible de borde, fondo o icono |
| Focus | Indicador visible con contraste mínimo de 3:1 (:focus-visible) |
| Active | Respuesta inmediata a la pulsación |
| Disabled | Apariencia atenuada y atributo disabled o aria-disabled |

El hover no será la única forma de acceder a información o
acciones; existirá un equivalente táctil y de teclado.

### 6.3. Iconografía

- Estilo lineal y consistente.
- Tamaños: 16, 20, 24 y 32 px.
- Un único conjunto o estilo de iconos en todo el sitio.

Conjunto propuesto: Lucide (valor inicial, sujeto a
validación). No se instalará ninguna dependencia todavía; la
forma de incorporarlo se decidirá durante la implementación.

## 7. Logotipo

- Utilizar los archivos SVG oficiales.
- Ancho mínimo orientativo del logotipo horizontal: 160 px.
- Tamaño mínimo del símbolo independiente: 24 px.
- Área de protección: 1/10 de la altura del logotipo.
- Utilizar la variante correspondiente a cada fondo.
- No reconstruir, deformar ni agregar efectos.

## 8. Pendientes

- Incorporar los SVG oficiales del logotipo y sus variantes
  (no existen en el repositorio).
- Definir el método de carga de Lato e IBM Plex Mono.
- Definir la superficie del contexto claro.
- Validar breakpoints, márgenes, separaciones, IBM Plex Mono
  y Lucide durante la implementación.
