# Estructura de la landing — Jump Studios

**Proyecto:** JumpStudiosWeb
**Versión del documento:** 1.0
**Fecha:** 27/11/2026
**Etapa:** Sprint 1
**Estado:** Estructura conceptual aprobada. Sin wireframe final.

## 1. Objetivo

Definir el orden, la finalidad y el contenido de las secciones
de la landing page.

No se define un wireframe final. Se construirá primero una
versión web funcional y, a partir de pruebas reales en
escritorio y móvil, se realizará un rediseño iterativo.

## 2. Prioridades comerciales

- El desarrollo web y el software a medida tienen el mayor
  protagonismo comercial.
- Las aplicaciones móviles y la consultoría tecnológica
  forman parte de los servicios de software.
- El hardware y las soluciones complementarias tienen un
  protagonismo secundario.
- La sección de proyectos se denomina «Destacados».

## 3. Estructura conceptual

| Orden | Sección | Componente (docs/04-architecture.md) | Contexto cromático |
|---|---|---|---|
| 1 | Header | layout/Header | Oscuro |
| 2 | Hero | sections/Hero | Oscuro |
| 3 | Servicios de software | sections/Services | Claro |
| 4 | Destacados | sections/Featured | Claro |
| 5 | Hardware y soluciones complementarias | sections/Hardware | Claro |
| 6 | Nosotros | sections/About | Claro |
| 7 | Contacto | sections/Contact | Oscuro (cierre) |
| 8 | Footer | layout/Footer | Oscuro (cierre) |

Los contextos cromáticos corresponden al tema híbrido
descrito en docs/05-design-system.md.

## 4. Secciones

### 4.1. Header

- Logotipo oficial (variante para fondo oscuro).
- Navegación a las secciones principales.
- Acceso directo a Contacto.
- Navegación accesible por teclado y adaptada a móvil.

### 4.2. Hero

- Eslogan corporativo disponible:
  «Ingeniería de software. Visión de negocio.»
- Breve descripción del estudio centrada en desarrollo web
  y software a medida.
- Acción principal: contacto.
- Acción secundaria: Destacados.
- Diagrama técnico (concepto provisional, ver
  docs/06-motion.md).

### 4.3. Servicios de software

Sección comercial principal.

- Software a medida.
- Desarrollo web.
- Aplicaciones móviles.
- Consultoría tecnológica.

Se evitará presentar los servicios como una fila de
tarjetas idénticas (ver docs/07-art-direction.md).

### 4.4. Destacados

| Proyecto | Descripción | Estado |
|---|---|---|
| Wis Barbers | Plataforma web y gestión de reservas | Incluido |
| Peninsula Constructora | Plataforma web corporativa | Incluido |
| Provider | Producto propio de gestión comercial y operativa para empresas distribuidoras | Se incorporará posteriormente |

- Utilizar capturas reales de los proyectos.
- Los datos se gestionarán de forma estructurada
  (docs/04-architecture.md, sección 11).
- No se publicarán métricas ni resultados no confirmados.

### 4.5. Hardware y soluciones complementarias

Sección secundaria, de menor extensión y jerarquía visual.

- Hardware y soluciones complementarias.
- Prototipado e impresión 3D.
- Evaluación de soluciones electromecánicas según viabilidad.

### 4.6. Nosotros

- Estudio de desarrollo de software uruguayo con capacidades
  multidisciplinarias en software, informática, hardware y
  mecatrónica.
- Valores: transparencia, responsabilidad, fiabilidad,
  humildad y autocrítica.

### 4.7. Contacto

- Acción principal de la página.
- Transición cromática hacia el cierre oscuro.
- Los canales y datos de contacto están pendientes de
  confirmación. No se publicarán datos no verificados.

### 4.8. Footer

- Logotipo oficial (variante para fondo oscuro).
- Enlaces de navegación.
- Información legal y de contacto, cuando esté confirmada.

## 5. Propuesta pendiente de aprobación: Metodología

Se propone evaluar una sección de metodología basada en el
proceso de trabajo del dossier corporativo:

1. Descubrimiento y relevamiento.
2. Análisis y planificación.
3. Diseño.
4. Desarrollo.
5. Validación y pruebas.
6. Implementación.
7. Soporte y evolución, según contratación.

Su incorporación, posición y formato (por ejemplo, como
diagrama técnico) se decidirán durante el rediseño
iterativo. No forma parte de la estructura aprobada ni
existe un componente asignado en docs/04-architecture.md.

## 6. Información corporativa de referencia

Extracto verificado del dossier corporativo. No reemplaza
el documento original.

**Descripción:** Jump Studios es un estudio de desarrollo de
software uruguayo con capacidades multidisciplinarias en
software, informática, hardware y mecatrónica.

**Servicios:**

- Software a medida.
- Desarrollo web.
- Aplicaciones móviles.
- Consultoría tecnológica.
- Hardware y soluciones complementarias.
- Prototipado e impresión 3D.
- Evaluación de soluciones electromecánicas según viabilidad.

**Proyectos:**

- Wis Barbers: plataforma web y gestión de reservas.
- Peninsula Constructora: plataforma web corporativa.
- Provider: producto propio de gestión comercial y operativa
  para empresas distribuidoras.

**Metodología:** ver sección 5.

**Valores:** transparencia, responsabilidad, fiabilidad,
humildad y autocrítica.

No se inventarán estadísticas, testimonios, clientes,
resultados, datos de contacto ni funcionalidades.

## 7. Pendientes

- Redacción definitiva de los textos (directorio content/).
- Confirmación de los canales de contacto.
- Capturas reales y enlaces autorizados de los proyectos.
- Decisión sobre la sección de metodología.
- Material aprobado de Provider.
