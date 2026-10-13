# Desarrollo Guiado por Contrapruebas (DGC)

[![Licencia: CC BY-SA 4.0](https://img.shields.io/badge/licencia-CC%20BY--SA%204.0-lightgrey.svg)](LICENSE)
![Versión](https://img.shields.io/badge/versión-0.1-blue.svg)
![Estado](https://img.shields.io/badge/estado-propuesta-orange.svg)

**DGC es una metodología de desarrollo de software con agentes de IA cuyo objetivo es garantizar que el código generado cumple su especificación sin requerir revisión humana.** La especificación es la única fuente de verdad y las pruebas de aceptación, definidas por personas, son inaccesibles al agente implementador.

Dicho de otra forma: el agente estudia el temario (la especificación), pero no conoce las preguntas del examen (las contrapruebas).

📄 **[Leer el método completo](metodo/dgc.md)** · 🌐 **[Página de DGC](https://j2logo.com/desarrollo-guiado-por-contrapruebas-dgc/)** · ✉️ **[Newsletter](https://j2logo.com/#newsletter)**

---

## El problema

Los agentes de IA escriben código funcional a gran velocidad. El cuello de botella se ha desplazado: ya no está en escribir el código, sino en saber si es correcto.

- **Revisar el código a mano** no escala: cuanto más produce el agente, más superficial se vuelve la revisión.
- **Dejar que el agente escriba sus propios tests** no sirve como autoridad: quien implementa y quien comprueba comparten la misma interpretación de la tarea, y los agentes tienden a ajustarse a las pruebas que pueden ver.
- **Spec-driven development** mejora el punto de partida, pero no define cómo verificar que el resultado cumple la especificación.

DGC propone que la verificación funcione como un examen: una autoridad independiente del implementador, derivada de la especificación y oculta a quien escribe el código.

## Las tres ideas

1. **La especificación es la única fuente de verdad.** El sistema se describe como un conjunto de **capacidades** versionadas, y el código se deriva de ellas. Nadie edita el código a mano.
2. **La verificación es independiente de quien implementa.** Cada criterio se comprueba con **contrapruebas**: ejemplos concretos que decide una persona (los escribe o los aprueba), que se ejecutan contra el sistema desde fuera y que el agente implementador nunca ve.
3. **El trabajo avanza por deltas.** Cada cambio es un **delta** tipado (adición, enmienda, derogación, bug, refactor o cimientos) que modifica la especificación y sus contrapruebas antes de tocar el código.

El método cubre además el feedback al agente cuando una contraprueba falla, la organización del trabajo del equipo, la retirada gradual de la revisión humana y la adopción en proyectos existentes.

DGC es una guía, no una camisa de fuerza. Distingue entre **principios**, que son obligatorios (por ejemplo, que el agente implementador no pueda acceder a las contrapruebas), y **prácticas**, que son la forma recomendada de cumplirlos (cómo organizar repositorios, ramas y pipeline). Cada equipo puede adaptar las prácticas a su contexto siempre que respete los principios.

## Contenido del repositorio

| Documento | Contenido |
|---|---|
| [`metodo/dgc.md`](metodo/dgc.md) | El método completo: principios, modelo, contrapruebas, deltas, ciclo, organización y limitaciones |
| [`CHANGELOG.md`](CHANGELOG.md) | Historial de versiones |

## Estado

**Propuesta v0.1.** Se está aplicando en **MaIA**, su implementación de referencia. Los resultados se publican en la [página de DGC](https://j2logo.com/desarrollo-guiado-por-contrapruebas-dgc/).

El texto canónico está en español.

## Participar

DGC es una propuesta abierta y mejora con la experiencia de quien la aplica.

- **¿Lo has probado, o parte de él?** Cuéntalo en una [issue con la plantilla «Lo he probado»](../../issues/new/choose): qué funcionó, qué no y en qué contexto.
- **¿Dudas, críticas o propuestas de cambio?** Abre una [discusión](../../discussions). Los cambios en el método se debaten ahí antes de incorporarse.
- **¿Has encontrado un precedente que no se cita?** Indícalo con la referencia. Se añadirá a la sección de influencias.

Antes de contribuir, lee [`CONTRIBUTING.md`](CONTRIBUTING.md): explica cómo se decide qué entra en el método y qué tipo de pull requests se aceptan.

## Cómo citar

> Juanjo Lozano Gómez (j2logo). *Desarrollo Guiado por Contrapruebas (DGC)*, v0.1, 2026. https://github.com/j2logo/dgc

GitHub ofrece también el botón *Cite this repository*, generado a partir de [`CITATION.cff`](CITATION.cff).

## Autor

**Juanjo Lozano Gómez** ([j2logo](https://j2logo.com)). Ingeniero Informático con más de 20 años de experiencia, trabajando en cómo construir y verificar software en la era de los agentes de IA.

- Blog: [Desarrollo Guiado por Contrapruebas](https://j2logo.com/desarrollo-guiado-por-contrapruebas-dgc/)
- Newsletter: [EstrategIA](https://j2logo.com/#newsletter)
- LinkedIn: [j2logo](https://www.linkedin.com/in/j2logo/)

## Licencia

*Desarrollo Guiado por Contrapruebas* © 2026 Juanjo (j2logo). Publicado bajo licencia [Creative Commons Attribution-ShareAlike 4.0 International Public
License](https://creativecommons.org/licenses/by-sa/4.0/deed.es) (CC BY-SA 4.0). Puedes usar, adaptar y redistribuir el texto siempre que cites la autoría y publiques las versiones derivadas con la misma licencia. El texto legal completo está en [`LICENSE`](LICENSE).
