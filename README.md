# Examen de Ascenso de Categoría — Simulador de estudio

Aplicación web estática (HTML + CSS + JS puro, sin dependencias ni build) para practicar el **Banco de Preguntas del Ministerio de Educación**, pensada para la preparación al Examen de Ascenso de Categoría Docente.

## Qué hace

- Cada intento toma **50 preguntas aleatorias** del banco (2158 preguntas en total), repartidas proporcionalmente entre 11 temas.
- Tienes **4 intentos** guardados en tu propio navegador (no se envía nada a ningún servidor).
- Cada pregunta se presenta en opción múltiple (1 correcta + 3 distractores generados del mismo tema) y te dice al instante si acertaste, mostrando la respuesta correcta.
- Al terminar un intento, ves tu puntaje y un **desglose por ramo/tema**, de más débil a más fuerte.
- Después del 4º intento, se genera un **reporte final ponderado** combinando los 4 intentos por tema.
- **Modo estudio libre**: tarjetas de pregunta/respuesta, sin calificar, filtrables por tema — para repasar antes de un intento formal.
- Todo el progreso se guarda en `localStorage` del navegador. Si borras datos de navegación o cambias de dispositivo, empiezas de cero (hay un botón "Reiniciar intentos" para hacerlo manualmente).

## Estructura

```
index.html   — estructura de la página
style.css    — sistema de diseño (tema "geoide" / curvas de nivel)
app.js       — toda la lógica: muestreo, calificación, vistas
data.js      — banco de preguntas (generado desde el PDF original)
```

## Publicar en GitHub Pages

1. Crea un repositorio nuevo en GitHub (puede ser público o privado con Pages habilitado en un plan que lo permita).
2. Sube estos 4 archivos (`index.html`, `style.css`, `app.js`, `data.js`) a la raíz del repositorio — o a una carpeta `docs/` si prefieres esa convención.
3. En el repositorio: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, elige la rama (`main`) y la carpeta (`/root` o `/docs` según dónde subiste los archivos).
4. Guarda. GitHub te dará una URL del tipo `https://tu-usuario.github.io/tu-repositorio/` en uno o dos minutos.

No requiere `npm install`, build, ni configuración adicional — son archivos estáticos.

## Actualizar el banco de preguntas

Si más adelante quieres regenerar `data.js` desde un PDF actualizado, el formato esperado por `app.js` es:

```js
const CATEGORIES = ["Nombre tema 0", "Nombre tema 1", ...];
const QUESTION_BANK = [
  [idNumerico, indiceDeCategoria, "texto de la pregunta", "texto de la respuesta"],
  ...
];
```

## Notas sobre el contenido

Las preguntas y respuestas provienen tal cual del banco de preguntas oficial (documento "RESPONDIDO"). Los temas (ramos) fueron asignados automáticamente por palabras clave a partir del contenido de cada pregunta, así que alguna clasificación puntual puede no ser perfecta — pero es suficiente para orientar el repaso por área.
# Examen-de-Ascenso-de-Categor-a-Simulador-de-estudio
