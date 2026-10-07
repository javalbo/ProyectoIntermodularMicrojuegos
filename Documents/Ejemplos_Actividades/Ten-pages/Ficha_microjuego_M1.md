# Planeta en Juego - Ficha del microjuego M1: ¡No malgastes agua!

## Ficha del microjuego M1: ¡No malgastes agua!

| Campo | Valor |
| --- | --- |
| **Nombre** | ¡No malgastes agua! |
| **ODS** | 6 · Agua limpia y saneamiento |
| **Autor/a** | ... |
| **Instrucción en pantalla** | «¡Recoge!» |
| **Objetivo** | Llenar el vaso con las gotas que caen antes de que se acabe el tiempo. |
| **Controles** | Ratón: el vaso sigue la posición horizontal del cursor. Teclado: las flechas ← y → lo desplazan. |
| **Tiempo límite** | 10 s en el nivel 1 (ver tabla de niveles). |
| **Victoria** | El vaso se llena (8 gotas). Se gana en ese momento, sin esperar a que acabe el tiempo. |
| **Derrota** | El tiempo llega a 0 con el vaso sin llenar. |
| **Elementos** | Vaso (controlado por el jugador), gotas, nivel de agua dentro del vaso, HUD. |

**Mecánica.** Las gotas aparecen en la parte superior, en una posición horizontal aleatoria, y caen en línea recta. Una gota que entra por la boca del vaso desaparece y sube el nivel de agua una unidad. Una gota que cae fuera se pierde sin más penalización.

### Niveles de dificultad

Zona de juego de 800 × 600 px. Son valores iniciales: se ajustarán al probar el juego (Actividad 4).

| Parámetro | Nivel 1 (0–9 puntos) | Nivel 2 (10–19 puntos) | Nivel 3 (20+ puntos) |
| --- | --- | --- | --- |
| Tiempo límite | 10 s | 8 s | 7 s |
| Gotas para llenar el vaso | 8 | 8 | 8 |
| Aparece una gota cada | 0,6 s | 0,5 s | 0,5 s |
| Velocidad de caída | 200 px/s | 300 px/s | 400 px/s |
| Anchura del vaso | 120 px | 90 px | 70 px |
| Gotas que llegan abajo antes del final (aprox.) | 12 | 13 | 12 |

### Justificación de las decisiones de diseño

- **Vaso y gotas.** Traduce el ODS 6 a un gesto cotidiano: cada gota cuenta y no hay que desperdiciarla.
- **«¡Recoge!».** Una sola palabra se lee de un vistazo durante los 1,5 s de la pantalla de instrucción.
- **10 s en el nivel 1.** Es el tiempo del ejemplo del enunciado y basta para entender el control la primera vez.
- **Ratón y flechas.** El ratón es lo más rápido para seguir las gotas; las flechas permiten jugar sin ratón.
- **Ganar al llenar el vaso.** Premia la rapidez y mantiene el ritmo de la partida (decisión D-04).
- **Las gotas perdidas no penalizan.** Así el microjuego tiene un único objetivo: llenar el vaso a tiempo (decisión D-05).
- **La dificultad viene de la precisión, no de la escasez.** En los tres niveles llegan unas 12 gotas y hacen falta 8. Lo que cambia es la anchura del vaso, la velocidad de las gotas y el tiempo, así que perder depende de la habilidad y no de la suerte.