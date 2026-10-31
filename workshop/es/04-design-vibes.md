<!-- l10n-sync: source-file="workshop/04-design-vibes.md" -->
# Parte 4: Tematización con el diseño como punto de partida

---

En esta parte, usarás los flujos de planificación e implementación de Copilot para diseñar una transformación completa del tema. Este es un enfoque de desarrollo centrado en el diseño: empieza con una visión, perfecciona los elementos visuales y deja que Copilot se encargue del trabajo pesado de CSS.

## Tarea 1: Planifica el tema retro

<!-- track:vscode:start -->
Cambia al modo **Plan** en GitHub Copilot Chat.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Usa `/plan` en GitHub Copilot CLI o pulsa **Shift+Tab** hasta activar el modo plan.
<!-- track:cli:end -->

Introduce este prompt:

> Quiero transformar esta página en una experiencia completa de arcade retro. Planifica una renovación visual que incluya: efectos de líneas de barrido CRT en el fondo, un brillo de neón pulsante en el título, una insignia VS animada con cambios de degradado, una capa de brillo y destellos sobre las tarjetas de resultados, animaciones de entrada flotante para los campos, texto de carga que cambie entre verde y morado, y efectos de brillo al pasar el cursor sobre los cuadrados de contribuciones. Mantén el fondo oscuro (`#0a0a1a`) y usa verde (`#5fed83`) y morado (`#8a2be2`) como colores de acento. Usa un tema oscuro con la fuente retro Press Start 2P de Google Fonts.

Copilot generará un plan detallado de implementación con todos los efectos visuales. **No lo aceptes de inmediato**: revísalo e itera:

- Sugiere ajustes en la duración de las animaciones (por ejemplo, «Haz que el pulso del neón sea más lento, de unos 3 segundos»).
- Pregunta por efectos concretos (por ejemplo, «¿Cómo funcionará la capa de destellos en las tarjetas?»).
- Solicita cambios en el enfoque si algo no te convence.

## Tarea 2: Implementa el tema

Cuando estés satisfecho con el plan, pide a Copilot que lo implemente.

> Implementa el plan del tema de arcade retro que acabamos de diseñar.

Copilot añadirá animaciones CSS, pseudoelementos y transiciones en la hoja de estilos. Por ejemplo:

- `@keyframes` para las líneas de barrido, el pulso de neón, los destellos y los efectos de entrada flotante.
- Pseudoelementos (`::before`, `::after`) para los efectos de superposición.
- Propiedades personalizadas CSS para los colores del tema.
- Transiciones y estados `hover` para los elementos interactivos.

<!-- track:cli:start -->
Cuando terminen los cambios, usa `/diff` para revisar los estilos antes de aprobarlos.
<!-- track:cli:end -->

## Tarea 3: Ajusta los detalles visuales

> **⚠️ ¿No ves los cambios?** Si el tema nuevo o las animaciones no aparecen, detén el servidor de desarrollo (`Ctrl+C`), reinícialo con `npm run dev` y actualiza la página por completo (`Ctrl+Shift+R`).

Mantén abierta la vista previa en el navegador e itera sobre el diseño. Prueba prompts como:

> El efecto de líneas de barrido es demasiado intenso; reduce la opacidad a 0.03.

> Añade un parpadeo eléctrico sutil al texto del título.

> La insignia VS debería pulsar con más intensidad.

Esto es **desarrollo centrado en el diseño**: iteras sobre el resultado visual en tiempo real. Cada prompt perfecciona la experiencia. No te conformes con algo «suficientemente bueno»: ajusta el diseño hasta que la página parezca una máquina de arcade.

## Tarea 4: Actualiza las instrucciones

Tus instrucciones deben reflejar las decisiones de diseño importantes para que los prompts posteriores mantengan el mismo rumbo.

<!-- track:vscode:start -->
Pide a Copilot Chat:

> Añade a `copilot-instructions.md` una sección de guía de diseño que describa el tema de arcade retro: colores, fuentes y estilo de animación.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Pide a Copilot CLI:

> Actualiza las instrucciones del repositorio con una breve guía de diseño del tema de arcade retro: colores, fuentes, estilo de animación y la regla de que la nueva interfaz conserve la estética de neón.
<!-- track:cli:end -->

Haz commit de las instrucciones y los cambios de diseño cuando la página tenga el aspecto que quieres.

## ✅ Parte 4 completada

**Lo que has aprendido:**

- Usar flujos de planificación para definir un **sistema de diseño antes de implementarlo**.
- **Iterar sobre el resultado visual** con prompts de seguimiento.
- **Actualizar las instrucciones tras tomar decisiones importantes** para mantener la identidad visual.
