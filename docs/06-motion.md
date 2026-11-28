# Animaciones e interacciones — Jump Studios

**Proyecto:** JumpStudiosWeb
**Versión del documento:** 1.0
**Fecha:** 27/11/2026
**Etapa:** Sprint 1
**Estado:** Base para la primera implementación. Concepto del Hero provisional.

## 1. Objetivo

Definir las animaciones e interacciones permitidas en la
landing page. Según AGENTS.md, no se introducirán
transiciones ni animaciones que no estén documentadas aquí.

## 2. Principios

- **Precisión:** movimientos exactos y medidos, coherentes con
  el concepto de ingeniería.
- **Intencionalidad:** cada animación explica, orienta o
  responde a una acción.
- **Continuidad:** las transiciones conectan estados sin saltos.
- **Rendimiento:** solo propiedades que no provoquen
  recálculos de maquetación.
- **Accesibilidad:** el contenido es completo y utilizable sin
  animaciones.

## 3. Hero

Se explorará un diagrama técnico animado que represente la
transformación de una necesidad empresarial en una solución
tecnológica.

- Recursos: conexiones, nodos y activaciones secuenciales.
- Al finalizar la animación inicial, el diagrama mantiene un
  estado visual estable, sin movimiento continuo.
- Títulos con aparición escalonada.

Este concepto es provisional y podrá cambiar durante el
rediseño.

## 4. Secciones

| Sección | Comportamiento |
|---|---|
| Hero | Aparición escalonada de títulos y animación del diagrama |
| Servicios | Respuesta visual de bordes, iconos y elementos técnicos |
| Destacados | Revelado progresivo de capturas reales de proyectos |
| Hardware | Posibles ilustraciones técnicas de componentes (exploratorio) |
| Nosotros | Transiciones tipográficas discretas |
| Contacto | Transición cromática y énfasis en la acción principal |

## 5. Tokens de movimiento

### 5.1. Duraciones

| Token | Valor |
|---|---|
| --motion-instant | 100ms |
| --motion-fast | 180ms |
| --motion-normal | 300ms |
| --motion-slow | 600ms |
| --motion-reveal | 900ms |
| --motion-stagger | 80ms |

### 5.2. Curvas

| Uso | Curva |
|---|---|
| Entradas | Ease-out |
| Transiciones entre estados | Ease-in-out |
| Flujos técnicos (conexiones, recorridos del diagrama) | Linear |

Los valores exactos (palabras clave de CSS o cubic-bezier)
se ajustarán durante la primera implementación y se
centralizarán en src/styles/tokens.css.

## 6. Tecnologías

Orden de prioridad:

1. CSS Transitions.
2. CSS Keyframes.
3. SVG (trazos, nodos y conexiones del diagrama).
4. Intersection Observer (activación de revelados).
5. Web Animations API, cuando sea necesario.

No se incorporarán GSAP, Motion ni Three.js sin una
justificación técnica documentada. Esto concreta el criterio
de docs/04-architecture.md, sección 9.2.

## 7. Restricciones

- Respetar prefers-reduced-motion.
- No utilizar scroll hijacking.
- No utilizar cursores personalizados que dificulten la
  navegación.
- No bloquear contenido durante animaciones.
- No utilizar pantallas de carga artificiales.
- Evitar movimientos continuos innecesarios.
- Evitar desplazamientos inesperados del contenido.
- Proporcionar equivalentes táctiles y de teclado para las
  interacciones de escritorio.
- Permitir pausar animaciones continuas cuando corresponda.
- Aspirar a 60 FPS en dispositivos capaces.

## 8. Criterios de implementación

- Animar preferentemente transform y opacity.
- El contenido debe ser visible en el HTML generado. Los
  estados iniciales ocultos de los revelados se aplicarán solo
  cuando JavaScript esté disponible, para no ocultar contenido
  si falla o no se ejecuta.
- Reservar el espacio de los elementos animados para no
  afectar el CLS.
- Con prefers-reduced-motion: reduce, los revelados mostrarán
  el contenido directamente y el diagrama del Hero se
  presentará en su estado final.

## 9. Pendientes

- Diseño concreto del diagrama del Hero.
- Valores exactos de las curvas.
- Decisión sobre las ilustraciones técnicas de Hardware.
- Validación del rendimiento en dispositivos móviles reales.
