<!-- l10n-sync: source-file="workshop/04-design-vibes.md" -->
# Parte 4: Tematización orientada al diseño

---

En esta parte, usarás los ciclos de planificación e implementación de Copilot para diseñar una transformación completa del tema. Este es un enfoque de desarrollo orientado al diseño: empieza con una visión, itera sobre los elementos visuales y deja que Copilot se encargue del trabajo pesado de CSS.

## Tarea 1: Planifica el tema retro

<!-- track:vscode:start -->
Cambia al modo **Plan** en GitHub Copilot Chat.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Usa `/plan` en GitHub Copilot CLI o pulsa **Shift+Tab** hasta activar el modo de planificación.
<!-- track:cli:end -->

Introduce este prompt:

> Quiero transformar esta página en una experiencia completa de arcade retro. Planifica una renovación visual integral que incluya: efectos de líneas de escaneo CRT en el fondo, un resplandor de neón en el título que pulse como un letrero luminoso, una insignia VS animada con cambios de color en degradado, una capa de brillo y reflejos en las tarjetas de resultados de usuario, animaciones de entrada flotante para los campos de entrada, texto de carga que cambie entre verde y morado, y efectos de resplandor al pasar el cursor sobre los cuadros de contribuciones. Mantén el fondo oscuro (`#0a0a1a`) y los colores de acento verde (`#5fed83`) y morado (`#8a2be2`). Usa el tema oscuro y la fuente retro de videojuegos Press Start 2P de Google Fonts.

Copilot generará un plan de implementación detallado con todos los efectos visuales. **No lo aceptes de inmediato**: revísalo e itera:

- Sugiere cambios en la duración de las animaciones (por ejemplo: «Haz que el pulso de neón sea más lento, de unos 3 segundos»).
- Pregunta por efectos concretos (por ejemplo: «¿Cómo funcionará la capa de reflejos de las tarjetas?»).
- Pide que se modifique el enfoque si algo no te convence.

## Tarea 2: Implementa el tema

Cuando estés satisfecho con el plan, pide a Copilot que lo implemente.

> Implementa el plan de tema de arcade retro que acabamos de diseñar.

Copilot añadirá animaciones CSS, pseudoelementos y transiciones a tu hoja de estilos. Puede incluir:

- `@keyframes` para las líneas de escaneo, el pulso de neón, los reflejos y las animaciones de entrada flotante
- Pseudoelementos (`::before`, `::after`) para los efectos de superposición
- Propiedades personalizadas de CSS para los colores del tema
- Transiciones y estados al pasar el cursor para los elementos interactivos

<!-- track:cli:start -->
Cuando se apliquen los cambios, usa `/diff` para revisar los estilos antes de aprobarlos.
<!-- track:cli:end -->

## Tarea 3: Perfecciona el estilo

> **⚠️ ¿No ves los cambios?** Si no aparecen el nuevo tema o las animaciones, detén el servidor de desarrollo (`Ctrl+C`), reinícialo con `npm run dev` y fuerza la recarga del navegador (`Ctrl+Shift+R`).

Mantén abierta la vista previa en el navegador e itera sobre el diseño. Prueba prompts como:

> El efecto de líneas de escaneo es demasiado intenso; reduce la opacidad a 0.03.

> Añade un parpadeo eléctrico sutil al título.

> La insignia VS debería pulsar de forma más llamativa.

Este es un enfoque de **desarrollo orientado al diseño**: iteras en tiempo real sobre el resultado visual. Cada prompt perfecciona la experiencia hasta que te convenza. No te conformes con «está bastante bien»: ajusta el estilo hasta que la página parezca una máquina de arcade.

## Tarea 4: Actualiza las instrucciones

Tus instrucciones deben reflejar las principales decisiones de diseño para que los prompts posteriores sigan alineados.

<!-- track:vscode:start -->
Pide a Copilot Chat:

> Añade a `copilot-instructions.md` una sección de guía de diseño que describa el tema de arcade retro: colores, fuentes y estilo de animación.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Pide a Copilot CLI:

> Actualiza las instrucciones del repositorio con una guía breve de diseño para el tema de arcade retro: colores, fuentes, estilo de animación y la regla de que la nueva interfaz debe mantener la estética de neón.
<!-- track:cli:end -->

Cuando la página tenga el aspecto deseado, haz commit de las instrucciones actualizadas y de los cambios de diseño.

## ✅ Parte 4 completada

**Lo que has aprendido:**

- Usar flujos de planificación para definir un **sistema de diseño antes de implementarlo**
- **Iterar sobre el resultado visual** con prompts de seguimiento rápidos
- **Actualizar las instrucciones tras tomar decisiones importantes** para mantener una identidad visual coherente
