# Dirección artística — Jump Studios

**Proyecto:** JumpStudiosWeb
**Versión del documento:** 1.0
**Fecha:** 27/11/2026
**Etapa:** Sprint 1
**Estado:** Concepto aprobado. Aplicación sujeta a rediseño iterativo.

## 1. Objetivo

Definir el lenguaje visual de la landing page de Jump Studios
y los criterios que guiarán las decisiones de diseño durante
la primera implementación y el rediseño posterior.

Este documento se complementa con:

- docs/05-design-system.md: valores concretos (color,
  tipografía, grilla, componentes).
- docs/06-motion.md: animaciones e interacciones.
- docs/08-structure.md: estructura de la landing.

## 2. Concepto

**Ingeniería y precisión.**

La web debe transmitir que Jump Studios diseña y construye
soluciones técnicas con rigor. La forma visual se apoya en
recursos propios de la ingeniería: grillas, medidas,
diagramas, numeraciones y etiquetas técnicas.

El concepto se traduce en una interfaz ordenada y exacta,
sin ornamentos que no comuniquen información.

## 3. Personalidad

- Tecnológica.
- Profesional.
- Seria.
- Diferenciada.

El tono visual debe ser sobrio y seguro. La diferenciación
se obtiene mediante la composición y la tipografía, no
mediante efectos decorativos.

## 4. Referencias visuales

- Vercel.
- Railway.
- Resend.
- Evil Martians.

Las referencias se utilizan para analizar criterios
(jerarquía tipográfica, uso de grillas, densidad de
información, diagramas técnicos, sobriedad cromática).
No se copiarán sus composiciones, ilustraciones, recursos
gráficos ni identidad.

## 5. Recursos visuales

### 5.1. Composiciones asimétricas

Utilizar la grilla de 12 columnas para generar bloques de
distinto ancho y alineación. Evitar la repetición de
secciones con el mismo esquema (título centrado y fila de
elementos iguales).

### 5.2. Grillas arquitectónicas

La grilla puede hacerse visible mediante líneas de 1 px,
divisiones y marcas de medida, siempre que ayude a ordenar
el contenido. Su color se controla con la variable
--color-grid.

### 5.3. Diagramas técnicos personalizados

Diagramas propios en SVG que representen procesos, flujos
o arquitecturas (por ejemplo, la transformación de una
necesidad empresarial en una solución tecnológica).
Deben construirse para Jump Studios; no se utilizarán
ilustraciones genéricas ni bancos de recursos.

### 5.4. Tipografía protagonista

Los títulos en Lato de gran tamaño y peso alto son el
principal recurso expresivo. La fuente monoespaciada se
reserva para etiquetas técnicas, numeraciones y diagramas.

### 5.5. Imágenes

Priorizar capturas reales de los proyectos desarrollados
(Wis Barbers, Peninsula Constructora y, posteriormente,
Provider). Las capturas deben presentarse con un
tratamiento consistente y sin alterar su contenido.

## 6. Elementos a evitar

- Apariencia genérica de páginas generadas por IA.
- Degradados genéricos.
- Glassmorphism excesivo.
- Tarjetas repetitivas como recurso principal de maquetación.
- Elementos flotantes sin propósito.
- Fotografías de stock de programadores.
- Sombras decorativas.
- Iconografía mezclada de distintos estilos.

Cualquier excepción deberá justificarse con una decisión
de diseño documentada, según lo indicado en AGENTS.md.

## 7. Identidad visual

Se respetará el manual de identidad visual de Jump Studios:

- Paleta oficial: Jump Midnight, Jump Green, Jump White y
  Jump Black.
- Logotipos oficiales en SVG, sin reconstrucciones,
  deformaciones ni efectos.

Los valores y reglas de uso se detallan en
docs/05-design-system.md.

## 8. Criterios de validación

Durante las pruebas y el rediseño se comprobará que:

- Cada recurso visual cumple una función (ordenar,
  explicar, jerarquizar o dirigir la acción).
- El desarrollo web y el software a medida tienen el
  mayor protagonismo.
- La página no puede confundirse con una plantilla genérica.
- La identidad se mantiene en escritorio y en móvil.

## 9. Pendientes

- Incorporar al repositorio el manual de identidad y los
  logotipos oficiales en SVG (public/assets/logos está vacío).
- Obtener capturas reales de Wis Barbers y
  Peninsula Constructora con autorización para su uso.
- Definir el estilo concreto de los diagramas técnicos
  durante la primera implementación.
