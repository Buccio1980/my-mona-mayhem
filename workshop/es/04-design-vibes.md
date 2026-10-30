<!-- l10n-sync: source-file="workshop/04-design-vibes.md" -->
# Parte 4: Tematización con diseño desde el principio

---

En esta parte, usarás los flujos de planificación e implementación de Copilot para diseñar una transformación completa del tema. Es desarrollo orientado al diseño: empieza con una visión, itera sobre los elementos visuales y deja que Copilot se encargue del trabajo pesado de CSS.

## Tarea 1: Planifica el tema retro

<!-- track:vscode:start -->
Cambia al modo **Plan** en GitHub Copilot Chat.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Usa `/plan` en GitHub Copilot CLI o pulsa **Shift+Tab** hasta activar el modo plan.
<!-- track:cli:end -->

Ingresa este prompt:

> Quiero transformar esta página en una experiencia completa de arcade retro. Planifica una renovación visual integral que incluya: efectos de líneas de barrido CRT en el fondo, un brillo de neón pulsante en el título, una insignia VS animada con cambios de degradado, una capa de brillo y destellos en las tarjetas de resultados, animaciones de entrada flotante para los campos, texto de carga que cambie entre verde y morado, y efectos de brillo al pasar el cursor sobre los cuadrados de contribuciones. Mantén el fondo oscuro (`#0a0a1a`) y los colores de acento verde (`#5fed83`) y morado (`#8a2be2`). Usa un tema oscuro con la fuente retro Press Start 2P de Google Fonts.

Copilot generará un plan detallado de implementación que abarque todos los efectos visuales. **No lo aceptes de inmediato**: revisa el plan e itera:

- Sugiere ajustes al ritmo de las animaciones (por ejemplo: «Haz que el pulso de neón sea más lento, de unos 3 segundos»).
- Pregunta por efectos concretos (por ejemplo: «¿Cómo funcionará la capa de destellos de las tarjetas?»).
- Pide cambios en el enfoque si algo no te convence.

## Tarea 2: Implementa el tema

Cuando estés satisfecho con el plan, pide a Copilot que lo implemente.

> Implementa el plan del tema retro que acabamos de diseñar.

Copilot añadirá a la hoja de estilos varias animaciones CSS, pseudoelementos y transiciones. Puede incluir:

- `@keyframes` para líneas de barrido, pulsos de neón, destellos y efectos de entrada flotante
- Pseudoelementos (`::before`, `::after`) para los efectos de superposición
- Propiedades personalizadas de CSS para los colores del tema
- Transiciones y estados al pasar el cursor para los elementos interactivos

<!-- track:cli:start -->
Cuando terminen los cambios, usa `/diff` para revisarlos antes de aprobarlos.
<!-- track:cli:end -->

## Tarea 3: Ajusta los detalles visuales

> **⚠️ ¿No ves los cambios?** Si el tema o las animaciones no aparecen, detén el servidor (`Ctrl+C`), reinícialo con `npm run dev` y actualiza la página sin usar la caché (`Ctrl+Shift+R`).

Mantén abierta la vista previa del navegador e itera sobre el diseño. Prueba prompts como:

> El efecto de líneas de barrido es demasiado intenso; reduce la opacidad a 0.03.

> Añade un sutil parpadeo eléctrico al texto del título.

> Haz que la insignia VS pulse con más intensidad.

Esto es **desarrollo orientado al diseño**: iteras sobre el resultado visual en tiempo real. Cada prompt refina la experiencia hasta que te convenza. No te conformes con algo «suficientemente bueno»: perfecciona el diseño hasta que la página parezca propia de una máquina recreativa.

## Tarea 4: Actualiza las instrucciones

Las instrucciones deben reflejar las decisiones de diseño importantes para que los prompts posteriores mantengan la coherencia.

<!-- track:vscode:start -->
Pide a Copilot Chat:

> Añade a `copilot-instructions.md` una sección de guía de diseño que describa el tema de arcade retro: colores, fuentes y estilo de animación.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Pide a Copilot CLI:

> Actualiza las instrucciones del repositorio con una guía breve del tema de arcade retro: colores, fuentes, estilo de animación y la regla de que la nueva interfaz conserve la estética de neón.
<!-- track:cli:end -->

Cuando la página esté lista, haz commit de las instrucciones actualizadas y de los cambios de diseño.

## ✅ Parte 4 completada

**Lo que has aprendido:**

- Usar flujos de planificación para definir un **sistema de diseño antes de implementarlo**
- **Iterar sobre el resultado visual** con prompts de seguimiento breves
- **Actualizar las instrucciones tras tomar decisiones importantes** para mantener la identidad visual
