<!-- l10n-sync: source-file="03-agent-mode.md" -->
# Parte 3: Construye el juego con flujos de trabajo agénticos

---

En esta parte, Copilot pasa de planificar a implementar. En lugar de escribir código línea por línea, describes lo que quieres y dejas que Copilot realice el trabajo en los archivos que debe modificar.

## Tarea 1: Conecta la Batalla

<!-- track:vscode:start -->
1. Cambia a modo **Agent** en Copilot Chat (selecciona "Agent" en el menú desplegable de modo).
2. Introduce este prompt:
<!-- track:vscode:end -->

<!-- track:cli:start -->
1. Devuelve Copilot CLI al flujo habitual de programación (o sigue en autopilot si quieres que continúe hasta que lo detengas).
2. Si te resulta útil, añade el archivo de la página como contexto: `@src/pages/index.astro`.
3. Introduce este prompt:
<!-- track:cli:end -->

   > Añade JavaScript del lado del cliente a la página de batalla para que:
   > 1. Al hacer clic en el botón Battle, obtenga los dos nombres de usuario de los campos.
   > 2. Compruebe que ambos estén completos (y muestre un error si no lo están).
   > 3. Obtenga en paralelo, desde nuestra API, los datos de contribuciones de ambos usuarios.
   > 4. Muestre los gráficos de contribuciones como cuadrículas de colores: cada día debe ser un cuadrado de color de la paleta de GitHub.
   > 5. Muestre una insignia VS entre los dos usuarios.
   > 6. Muestre el nombre de usuario, el total de contribuciones y el intervalo de fechas de cada usuario.
   > 7. Gestione los estados de carga y los errores.
   > 8. También se active al pulsar la tecla Enter en los campos de entrada.
   > 9. Por ahora, usa la interfaz sencilla que ya está creada.
   >
   > Usa interfaces de TypeScript para la estructura de datos de contribuciones.

<!-- track:vscode:start -->
3. Deja que Agent Mode trabaje en la implementación a través de `index.astro`. Observa cómo planifica su enfoque, identifica los archivos que necesita modificar y escribe el código.
4. Revisa los cambios propuestos en la vista de diferencias antes de aceptarlos.
<!-- track:vscode:end -->

<!-- track:cli:start -->
4. Deja que Copilot CLI realice la implementación en `src/pages/index.astro`.
5. Usa `/diff` para inspeccionar los cambios generados y aprobarlos.
<!-- track:cli:end -->

## Tarea 2: Prueba la Batalla

1. Ingresa `octocat` y `torvalds` como los dos nombres de usuario, luego haz clic en **Battle**.
2. Deberías ver ambos gráficos de contribuciones renderizados lado a lado con cuadrículas de colores.
3. Prueba los casos de error:
   - Deja uno o ambos campos vacíos y haz clic en Battle — deberías ver un error de validación.
   - Ingresa un nombre de usuario inválido — la app debería mostrar un error de la API.
4. Prueba presionar **Enter** en cualquier campo de entrada — debería activar la batalla igual que al hacer clic en el botón.

## Tarea 3: Itera con Copilot

Si algo no está del todo bien, da seguimiento con comentarios directamente a Copilot. Por ejemplo:

- *"Los cuadrados de contribuciones son demasiado grandes; haz que midan 12x12px."*
- *"Añade una ayuda emergente al pasar el cursor que muestre la fecha y el número de contribuciones."*
- *"El estado de carga necesita una animación de pulso."*

<!-- track:vscode:start -->
Agent Mode gestiona de forma natural los cambios en varios archivos y las iteraciones. Cada prompt de seguimiento aprovecha el contexto anterior, así que puedes perfeccionar la implementación poco a poco sin empezar de cero.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Las sesiones de Copilot CLI conservan el historial, por lo que cada prompt de seguimiento se apoya en los anteriores. Usa `/session` o `/context` para inspeccionar el contexto que Copilot mantiene y, después de una iteración importante, ejecuta `/review` para buscar errores o mejoras.
<!-- track:cli:end -->

## Consejos para esta parte

- **Sé específico sobre lo que quieres** — requisitos claros producen mejores resultados.
- **Divide las tareas grandes en prompts más pequeños** si Copilot se desvía.
- **Revisa los cambios antes de aceptarlos** — el código generado es más fácil de inspeccionar que de reescribir después.
- **Prueba la aplicación después de cada implementación** para detectar los problemas cuanto antes.

## ✅ Parte 3 Completa

Has aprendido a:

- Usar Copilot para **implementar cambios en varios archivos**
- **Iterar sobre los resultados** con comentarios concretos
- Gestionar el **ciclo completo de una funcionalidad**: implementación, revisión, pruebas y refinamiento
