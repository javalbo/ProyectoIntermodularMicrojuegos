# Planeta en Juego · Análisis de requisitos

> **Documento de ejemplo · Actividad 1.** Recoge los requisitos del juego completo y los del microjuego M1, «¡No malgastes agua!». En vuestro documento hay que añadir los requisitos, historias y tarjetas de cada microjuego.

**Prioridad:** Alta = imprescindible para la v1.0 · Media = importante, pero el juego funciona sin ello · Baja = solo si da tiempo.
**Origen:** *Enunciado* = lo pide la práctica · *Ten Pages* = lo decidió el grupo en [01-Ten_pages.md](01-Ten_pages.md).

## 1. Requisitos

### 1.1 Requisitos funcionales del juego

| ID | Descripción | Tipo | Prioridad | Origen |
| --- | --- | --- | --- | --- |
| RF-01 | El menú principal tiene un botón «Jugar» que inicia la partida. | Funcional | Alta | Enunciado |
| RF-02 | Al iniciar la partida, el jugador tiene 4 vidas y 0 puntos. | Funcional | Alta | Enunciado |
| RF-03 | La partida encadena microjuegos en orden aleatorio, sin repetir el anterior. | Funcional | Alta | Enunciado; el orden, Ten Pages (D-03) |
| RF-04 | Antes de cada microjuego se muestran su instrucción y su ODS durante 1,5 s. | Funcional | Media | Ten Pages (D-08) |
| RF-05 | Superar un microjuego suma 1 punto. | Funcional | Alta | Enunciado (D-02) |
| RF-06 | Fallar un microjuego resta 1 vida; si quedan vidas, empieza el siguiente. | Funcional | Alta | Enunciado |
| RF-07 | Con 0 vidas, la partida termina y se muestra la puntuación final. | Funcional | Alta | Enunciado |
| RF-08 | Los microjuegos se juegan en nivel 1 con 0–9 puntos, en nivel 2 con 10–19 y en nivel 3 con 20 o más. | Funcional | Alta | Enunciado (D-01) |
| RF-09 | Cada microjuego tiene un objetivo único y un tiempo límite, y se controla con ratón y/o teclado. | Funcional | Alta | Enunciado |
| RF-10 | Cada microjuego se relaciona con al menos un ODS. | Funcional | Alta | Enunciado |
| RF-11 | Durante el microjuego, el HUD muestra las vidas, los puntos y el tiempo restante. | Funcional | Alta | Ten Pages |
| RF-12 | La pantalla de fin permite jugar otra vez o volver al menú. | Funcional | Media | Ten Pages |
| RF-13 | La web tiene apartados con la documentación del proyecto y un enlace a Trello. | Funcional | Alta | Enunciado |

### 1.2 Requisitos funcionales del microjuego M1 · ¡No malgastes agua!

| ID | Descripción | Tipo | Prioridad | Origen |
| --- | --- | --- | --- | --- |
| RF-M1-01 | El vaso sustituye al cursor y sigue su posición horizontal; las flechas ← y → también lo mueven. | Funcional | Alta | Ten Pages (D-07) |
| RF-M1-02 | Las gotas aparecen arriba, en posiciones horizontales aleatorias, a intervalos fijos según el nivel. | Funcional | Alta | Ten Pages |
| RF-M1-03 | Una gota que entra en el vaso desaparece y sube el nivel de agua una unidad; una gota que cae fuera desaparece sin efecto. | Funcional | Alta | Ten Pages (D-05) |
| RF-M1-04 | Con 8 gotas dentro, el microjuego se supera en ese mismo momento. | Funcional | Alta | Ten Pages (D-04) |
| RF-M1-05 | Si el tiempo llega a 0 sin llenar el vaso, el microjuego se falla. | Funcional | Alta | Enunciado y Ten Pages |
| RF-M1-06 | El tiempo, la frecuencia de las gotas, su velocidad y la anchura del vaso cambian según el nivel, como indica la tabla del Ten Pages. | Funcional | Alta | Enunciado y Ten Pages |

### 1.3 Requisitos no funcionales

| ID | Descripción | Tipo | Prioridad | Origen |
| --- | --- | --- | --- | --- |
| RNF-01 | El juego funciona en las versiones actuales de Chrome, Firefox y Edge de escritorio, sin instalar nada. | No funcional | Alta | Enunciado |
| RNF-02 | La web se publica en GitHub Pages desde la rama `main`, carpeta raíz. | No funcional | Alta | Enunciado |
| RNF-03 | Se usa solo HTML, CSS y JavaScript en el navegador, sin servidor propio. | No funcional | Alta | Enunciado (GitHub Pages solo sirve archivos estáticos) |
| RNF-04 | El código está en un repositorio público de GitHub con control de versiones Git. | No funcional | Alta | Enunciado |
| RNF-05 | El juego se mantiene a unos 60 fotogramas por segundo en un ordenador del aula. | No funcional | Media | Ten Pages |
| RNF-06 | Cada instrucción tiene como máximo 2 palabras. | No funcional | Media | Ten Pages |

## 2. Historias de usuario

Una historia por funcionalidad. Cada criterio de aceptación tiene que poder comprobarse: en la Actividad 4 se convertirá en un caso de prueba.

### HU-01 · Iniciar partida

*Como jugador, quiero empezar una partida desde el menú para jugar cuando esté listo.*
Requisitos: RF-01, RF-02

- **CA-01.1** Dado que estoy en el menú principal, cuando pulso «Jugar», entonces empieza la partida con 4 vidas y 0 puntos.

### HU-02 · Encadenar microjuegos

*Como jugador, quiero saber qué tengo que hacer antes de cada microjuego para poder ganarlo.*
Requisitos: RF-03, RF-04, RF-10

- **CA-02.1** Dado que acaba un microjuego y me quedan vidas, cuando empieza el siguiente, entonces veo durante 1,5 s su instrucción y su ODS.
- **CA-02.2** Dado que acabo de jugar «¡No malgastes agua!», cuando empieza el siguiente microjuego, entonces no es «¡No malgastes agua!».

### HU-03 · Sumar puntos

*Como jugador, quiero sumar un punto al superar un microjuego para ver mi progreso.*
Requisitos: RF-05

- **CA-03.1** Dado que tengo 4 puntos, cuando cumplo el objetivo antes de que acabe el tiempo, entonces tengo 5 puntos.

### HU-04 · Perder una vida al fallar

*Como jugador, quiero perder una vida al fallar un microjuego para que fallar tenga consecuencias.*
Requisitos: RF-06

- **CA-04.1** Dado que tengo 2 vidas, cuando se agota el tiempo sin cumplir el objetivo, entonces me queda 1 vida y empieza otro microjuego.

### HU-05 · Fin de partida

*Como jugador, quiero ver mi puntuación final al perder todas las vidas para intentar superarla.*
Requisitos: RF-07

- **CA-05.1** Dado que me queda 1 vida, cuando fallo un microjuego, entonces aparece la pantalla de fin con mi puntuación final.

### HU-06 · Dificultad progresiva

*Como jugador, quiero que los microjuegos se vuelvan más difíciles a medida que avanzo para que la partida siga siendo un reto.*
Requisitos: RF-08

- **CA-06.1** Dado que tengo 8 puntos, cuando supero un microjuego, entonces el siguiente se juega en nivel 1.
- **CA-06.2** Dado que tengo 9 puntos, cuando supero un microjuego, entonces el siguiente se juega en nivel 2.
- **CA-06.3** Dado que tengo 19 puntos, cuando supero un microjuego, entonces el siguiente se juega en nivel 3.

### HU-07 · Ver el estado de la partida

*Como jugador, quiero ver mis vidas, mis puntos y el tiempo que me queda mientras juego para decidir cómo actuar.*
Requisitos: RF-11

- **CA-07.1** Dado que estoy jugando un microjuego, cuando pasa un segundo, entonces el HUD muestra un segundo menos de tiempo restante.
- **CA-07.2** Dado que estoy jugando un microjuego, cuando lo supero o lo fallo, entonces el HUD actualiza los puntos o las vidas antes del siguiente.

### HU-08 · Volver a jugar o al menú

*Como jugador, quiero elegir entre jugar otra vez o volver al menú al acabar la partida para seguir jugando o consultar la web.*
Requisitos: RF-12

- **CA-08.1** Dado que estoy en la pantalla de fin, cuando pulso «Jugar otra vez», entonces empieza una partida nueva con 4 vidas y 0 puntos.
- **CA-08.2** Dado que estoy en la pantalla de fin, cuando pulso «Menú», entonces veo el menú principal.

### HU-09 · Consultar la documentación

*Como jugador, quiero consultar la documentación del proyecto desde la web para saber cómo se ha hecho el juego.*
Requisitos: RF-13

- **CA-09.1** Dado que estoy en la web del proyecto, cuando pulso «Ten Pages» en la barra de navegación, entonces veo el documento Ten Pages.
- **CA-09.2** Dado que estoy en la web del proyecto, cuando pulso «Trello», entonces se abre el tablero del grupo.

### HU-M1-01 · Mover el vaso

*Como jugador, quiero mover el vaso con el ratón o con las flechas para colocarlo debajo de las gotas.*
Requisitos: RF-09, RF-M1-01

- **CA-M1-01.1** Dado que el microjuego ha empezado, cuando muevo el ratón hacia la derecha, entonces el vaso se desplaza hacia la derecha.
- **CA-M1-01.2** Dado que el vaso está en el borde izquierdo, cuando pulso ←, entonces el vaso no sale de la zona de juego.

### HU-M1-02 · Recoger gotas

*Como jugador, quiero que cada gota que recojo llene un poco el vaso para ver cuánto me falta.*
Requisitos: RF-M1-02, RF-M1-03

- **CA-M1-02.1** Dado que el vaso tiene 3 de 8 gotas, cuando una gota cae dentro, entonces el vaso muestra 4 de 8 y la gota desaparece.
- **CA-M1-02.2** Dado que el vaso tiene 3 de 8 gotas, cuando una gota cae fuera, entonces desaparece y el vaso sigue con 3 de 8.

### HU-M1-03 · Ganar o perder el microjuego

*Como jugador, quiero ganar en cuanto lleno el vaso para no tener que esperar a que acabe el tiempo.*
Requisitos: RF-M1-04, RF-M1-05

- **CA-M1-03.1** Dado que el vaso tiene 7 de 8 gotas y quedan 3 s, cuando recojo una gota más, entonces el microjuego termina como superado.
- **CA-M1-03.2** Dado que el vaso tiene 6 de 8 gotas, cuando el tiempo llega a 0, entonces el microjuego termina como fallado.

### HU-M1-04 · Niveles de «¡No malgastes agua!»

*Como jugador, quiero que este microjuego sea más difícil en los niveles altos para notar que avanzo.*
Requisitos: RF-M1-06

- **CA-M1-04.1** Dado que el nivel es 1, cuando empieza el microjuego, entonces dura 10 s, el vaso mide 120 px y las gotas caen a 200 px/s.
- **CA-M1-04.2** Dado que el nivel es 2, cuando empieza el microjuego, entonces dura 8 s, el vaso mide 90 px y las gotas caen a 300 px/s.
- **CA-M1-04.3** Dado que el nivel es 3, cuando empieza el microjuego, entonces dura 7 s, el vaso mide 70 px y las gotas caen a 400 px/s.

## 3. Diagrama de casos de uso

![Diagrama de casos de uso de Planeta en Juego](img/casos-de-uso.svg)

Diagrama hecho con PlantUML; el código fuente está en [img/casos-de-uso.puml](img/casos-de-uso.puml). «Iniciar partida» incluye «Jugar microjuego» porque toda partida consiste en jugar microjuegos hasta perder las vidas.

| Caso de uso | Qué hace el jugador | Historias |
| --- | --- | --- |
| Iniciar partida | Pulsa «Jugar» en el menú o «Jugar otra vez» en la pantalla de fin. | HU-01, HU-08 |
| Jugar microjuego | Lee la instrucción e intenta cumplir el objetivo antes de que acabe el tiempo. | HU-02, HU-03, HU-04, HU-06, HU-M1-01 a HU-M1-04 |
| Consultar puntuación | Ve las vidas, los puntos y el tiempo en el HUD, y la puntuación final al acabar. | HU-05, HU-07 |
| Volver al menú | Desde la pantalla de fin, vuelve al menú principal. | HU-08 |
| Consultar documentación | En la web, abre los apartados de documentación y el enlace a Trello. | HU-09 |

## 4. Registro de decisiones

Dudas que deja abiertas el enunciado o el diseño, y cómo las ha resuelto el grupo.

| ID | Duda | Decisión | Motivo | Afecta a |
| --- | --- | --- | --- | --- |
| D-01 | «Al superar los 10 y 20 puntos»: ¿el nivel 2 empieza con 10 o con 11 puntos? | Nivel 2 con 10 puntos o más; nivel 3 con 20 o más. | Quien ha superado 10 microjuegos tiene 10 puntos, así que el siguiente ya debe ser más difícil. | RF-08 |
| D-02 | ¿Cuántos puntos da cada microjuego? | 1 punto por microjuego superado. | Así los umbrales de 10 y 20 puntos equivalen a 10 y 20 microjuegos superados. | RF-05 |
| D-03 | ¿En qué orden salen los microjuegos? | Aleatorio, sin repetir el anterior. | Una partida predecible aburre, y el mismo microjuego dos veces seguidas parece un error. | RF-03 |
| D-04 | En M1, ¿se gana al llenar el vaso o al acabar el tiempo? | En cuanto se llena el vaso. | Premia la rapidez y mantiene el ritmo de la partida. | RF-M1-04 |
| D-05 | En M1, ¿penalizan las gotas que caen fuera? | No. | El microjuego tiene un único objetivo: llenar el vaso a tiempo. | RF-M1-03 |
| D-06 | ¿Se guarda la mejor puntuación? | No, en esta versión. | No lo pide el enunciado; el ranking es una ampliación opcional que necesita servidor. | — |
| D-07 | En M1, ¿ratón, teclado o ambos? | Ambos: ratón y flechas. | El enunciado admite cualquiera; con los dos se puede jugar también sin ratón. | RF-M1-01 |
| D-08 | ¿La pantalla de instrucción cuenta dentro del tiempo límite? | No: dura 1,5 s y el tiempo empieza después. | El tiempo límite es para jugar, no para leer. | RF-04 |

## 5. Matriz de trazabilidad inicial

Cada historia es una tarjeta del backlog de Trello. Las columnas **PR** y **Caso de prueba** se completan en las actividades 3 y 4.

**Esfuerzo:** S = una sesión o menos · M = entre una y dos sesiones · L = más de dos sesiones (mejor dividirla en varias tarjetas).

| Requisito | Historia | Tarjeta de Trello | Etiqueta | Esfuerzo | PR (A3) | Caso de prueba (A4) |
| --- | --- | --- | --- | --- | --- | --- |
| RF-01, RF-02 | HU-01 | T-01 · Iniciar partida | motor | S | | |
| RF-03, RF-04, RF-10 | HU-02 | T-02 · Encadenar microjuegos | motor | M | | |
| RF-05 | HU-03 | T-03 · Sumar puntos | motor | S | | |
| RF-06 | HU-04 | T-04 · Perder una vida al fallar | motor | S | | |
| RF-07 | HU-05 | T-05 · Fin de partida | motor | S | | |
| RF-08 | HU-06 | T-06 · Dificultad progresiva | motor | M | | |
| RF-11 | HU-07 | T-07 · HUD | motor | M | | |
| RF-12 | HU-08 | T-08 · Volver a jugar o al menú | motor | S | | |
| RF-13 | HU-09 | T-09 · Documentación en la web | web | M | | |
| RF-09, RF-M1-01 | HU-M1-01 | T-10 · M1: mover el vaso | microjuego | S | | |
| RF-M1-02, RF-M1-03 | HU-M1-02 | T-11 · M1: recoger gotas | microjuego | M | | |
| RF-M1-04, RF-M1-05 | HU-M1-03 | T-12 · M1: ganar o perder | microjuego | S | | |
| RF-M1-06 | HU-M1-04 | T-13 · M1: tres niveles | microjuego | M | | |
| RNF-02 | — | T-14 · Publicar en GitHub Pages | web | S | | |
| RNF-01, RNF-03, RNF-05 | — | Se comprueban en todas las tarjetas y en la Actividad 4 | — | — | | |
| RNF-04 | — | Hecho en la Actividad 0 | — | — | | |
| RNF-06 | HU-02 | T-02 · Encadenar microjuegos | motor | M | | |

Tarjetas de documentación, sin requisito asociado: **T-15 · Redactar el Ten Pages** (docs, M) y **T-16 · Redactar el análisis** (docs, M).

### Ejemplo de tarjeta en Trello

> **T-04 · Perder una vida al fallar**
> Etiqueta: `motor` · Esfuerzo: `S`
>
> *Como jugador, quiero perder una vida al fallar un microjuego para que fallar tenga consecuencias.*
>
> Checklist de aceptación:
> - [ ] CA-04.1 Dado que tengo 2 vidas, cuando se agota el tiempo sin cumplir el objetivo, entonces me queda 1 vida y empieza otro microjuego.
>
> Requisito: RF-06 · Rama prevista: `features/perder-vida`
