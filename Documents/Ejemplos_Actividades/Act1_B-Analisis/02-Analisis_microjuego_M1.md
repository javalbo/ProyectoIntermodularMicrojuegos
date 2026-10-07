# Planeta en Juego · Análisis de requisitos

> **Documento de ejemplo.** Recoge los requisitos del microjuego M1, «¡No malgastes agua!».

**Prioridad:** Alta = imprescindible para la v1.0 · Media = importante, pero el juego funciona sin ello · Baja = solo si da tiempo.
**Origen:** *Enunciado* = lo pide la práctica · *Ten Pages* = lo decidió el grupo en [01-Ten_pages.md](01-Ten_pages.md).

## 1 Requisitos funcionales del microjuego M1: ¡No malgastes agua!

| ID | Descripción | Tipo | Prioridad | Origen |
| --- | --- | --- | --- | --- |
| RF-M1-01 | El vaso sustituye al cursor y sigue su posición horizontal; las flechas ← y → también lo mueven. | Funcional | Alta | Ten Pages (D-07) |
| RF-M1-02 | Las gotas aparecen arriba, en posiciones horizontales aleatorias, a intervalos fijos según el nivel. | Funcional | Alta | Ten Pages |
| RF-M1-03 | Una gota que entra en el vaso desaparece y sube el nivel de agua una unidad; una gota que cae fuera desaparece sin efecto. | Funcional | Alta | Ten Pages (D-05) |

## 2. Historias de usuario
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
