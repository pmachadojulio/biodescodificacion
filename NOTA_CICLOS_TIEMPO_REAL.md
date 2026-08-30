# Idea — Ciclos y tiempo real

> 2026-08-30 — Para desarrollo posterior (no bloquea uso actual).

## Objetivo
Que al tipear o grabar, la ficha **detecte sola** un posible ciclo/lealtad y lo pinte como badge, sin que yo tenga que comparar a ojo edades/fechas.

## Panel "Ciclos detectados" (arriba de la ficha, debajo de datos principales)
- Compara: `edad actual` + `timeline (eventos con edad/fecha)` vs `árbol (padre/madre edades al tenerte, hermanos, aborto previo, fechas de muerte/nacimiento)`.
- Reglas v1 (simples, sin IA):
  - Misma edad: síntoma a los 32 = madre a los 32 al tenerte → badge `lealtad por edad`.
  - Misma fecha ±7/10 días: evento tuyo en febrero = muerte/nacimiento ancestro en febrero ±7d → `aniversario`.
  - Repetidor: 10/11 en tu historia y en tu hijo/hermano.
- Si hay match, muestra: `¡Posible lealtad! Tu [evento] a los [X] coincide con [pariente] a los [X] — ¿qué no pudo hacer/decir esa persona?` + botón para crear repregunta.

## Grabación → Embudo en tiempo real
- Hoy: grabación queda como audio guardado en la sesión.
- Idea: al detener grabación, ofrecer **Transcribir con Whisper** (modelo base ya usado para audios de WhatsApp, 97 audios). El texto transcripto entra directo a `ctxAll` y dispara repreguntas/biblio/cerebro en vivo, igual que si lo hubieras tipeado.
- En esta MacBook con WisprFlow, el dictado ya alimenta el embudo al tipear; la grabación continua sería el mismo flujo pero sin tipear.
- Pendiente: probar Whisper en browser (WebAssembly) vs. paso por `ffmpeg + whisper base` local. Por privacidad, mantener todo local.

## Estado actual
- Timeline y árbol ya por consultante, con auto-extracción (10/11, 5ta, aborto, FUPU) y `+ Evento` manual.
- Embudo y cerebro ya leen `timeline + árbol + guía + sesiones` en vivo.

