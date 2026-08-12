---
title: Por qué usar Git
---

# Por qué usar Git

Imagina que estás escribiendo un cuento largo en tu ordenador.

Llevas varios párrafos, decides borrar uno porque no te gusta, y al día siguiente te das cuenta de que el original era mejor.

¿Puedes recuperarlo?

Si no hiciste una copia manual antes de borrarlo, probablemente no.

## El problema real

Cuando programamos, sucede lo mismo, pero con más frecuencia y más archivos.

- Pruebas una idea y el código deja de funcionar.
- Editas un archivo por la noche y al día siguiente no recuerdas qué cambiaste.
- Necesitas volver a una versión que funcionaba, pero ya no tienes forma de recuperarla.

Muchos principiantes resuelven esto creando copias manuales: `proyecto_final.py`, `proyecto_final2.py`, `proyecto_final2_DEFINITIVO.py`. Funciona, pero es lento, confuso y fácil de olvidar.

## La solución

Git es una herramienta que guarda automáticamente una "foto" de todos tus archivos cada vez que se lo pides.

Cada foto incluye qué archivos existían, qué contenían y cuándo se guardó. Puedes saltar entre esas fotos en cualquier momento, compararlas o incluso probar ideas en paralelo sin tocar tu trabajo principal.

Es como tener un control de guardado ilimitado en un videojuego, pero para tu código.

## Ventajas clave

**1. Puedes experimentar sin miedo**

Quieres probar una idea arriesgada. Si sale mal, simplemente vuelves a la foto anterior. Nada de lo que hiciste afecta tu trabajo principal hasta que decidas que está listo.

**2. Puedes volver atrás en cualquier momento**

Si descubres que algo dejó de funcionar hace tres días, puedes ver exactamente qué cambió y recuperar la versión anterior sin buscar entre carpetas duplicadas.

**3. Sabes qué cambiaste y por qué**

Cada foto lleva una etiqueta descriptiva que escribes tú mismo: "agregar botón de login", "corregir error en cálculo de precios". Esto te permite leer la historia de tu proyecto como si fuera un diario.

**4. Facilita trabajar con otras personas**

Cuando varias personas editan los mismos archivos, Git ayuda a combinar los cambios y avisar si dos personas modificaron la misma línea al mismo tiempo. Eso evita que alguien sobrescriba accidentalmente el trabajo de otro.

## ¿Cuándo empezar?

Desde el primer proyecto, por pequeño que sea.

No es necesario esperar a tener un trabajo grande o a formar parte de un equipo. Usar Git en proyectos personales te acostumbra a pensar en versiones y te da seguridad desde el primer día.

## ¿Y ahora qué?

Si quieres probarlo con tus propias manos, puedes seguir la guía práctica [Git para niños: ramas, commits y merges](git-for-kids-cli.md). Está diseñada para quienes nunca han usado Git: explica los conceptos paso a paso y te guía a través de tu primer repositorio.

