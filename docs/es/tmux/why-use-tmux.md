# Por qué usar tmux

Imagina que estás ejecutando un script en un servidor remoto por SSH.

Lleva veinte minutos procesando datos. Te despides del ordenador, cierras la laptop, y al volver descubres que la conexión se cortó y el script se detuvo.

¿Tienes que empezar de nuevo?

Si no tomaste precauciones, probablemente sí.

## El problema real

Cuando trabajamos en la terminal, todo depende de que esa ventana siga abierta.

- Cerramos la terminal sin querer y perdemos todo lo que estaba corriendo.
- Se corta la conexión Wi-Fi y una descarga o instalación se interrumpe.
- Nos desconectamos de un servidor remoto y el proceso que dejamos ahí muere al instante.

Muchos principiantes resuelven esto dejando la computadora encendida durante horas o volviendo a ejecutar todo desde el principio. Funciona, pero es incómodo, lento y propenso a errores.

## La solución

Tmux es una herramienta que crea sesiones de terminal que **siguen vivas** aunque cierres la ventana o pierdas la conexión.

Puedes iniciar un proceso dentro de tmux, desconectarte tranquilamente, apagar tu ordenador si quieres, y al volver —desde la misma máquina o desde otro lugar— retomar exactamente donde lo dejaste.

Es como dejar algo cocinando en la cocina mientras sales a hacer otras tareas. La olla sigue ahí, el fuego sigue encendido, y cuando vuelves todo está como lo dejaste.

## Ventajas clave

**1. No pierdes el trabajo si se cierra la terminal**

Tmux mantiene la sesión activa en el servidor. Aunque cierres la ventana de tu ordenador, el proceso sigue corriendo en segundo plano.

**2. Puedes desconectarte y volver más tarde**

Empiezas una tarea larga en la oficina, te desconectas, y desde casa vuelves a entrar en la misma sesión para verificar el progreso. Nada se pierde en el camino.

**3. Varias ventanas dentro de una misma sesión**

Tmux te permite dividir la pantalla o abrir pestañas, como si tuvieras varias terminales dentro de una sola. Esto es útil cuando necesitas ver logs en una ventana mientras editas archivos en otra.

**4. Útil tanto en local como en remoto**

Aunque brilla especialmente en servidores por SSH, también puedes usar tmux en tu propio ordenador para organizar tareas y evitar que un cierre accidental de terminal arruine lo que estabas haciendo.

## ¿Cuándo empezar?

Desde el primer script que tarde más de unos minutos en ejecutarse, o desde tu primera conexión remota a un servidor.

No es necesario esperar a proyectos grandes o entornos profesionales. Usar tmux en tareas pequeñas te acostumbra a trabajar con seguridad y te ahorra frustraciones desde el primer día.

## ¿Y ahora qué?

Si quieres probarlo con tus propias manos, puedes seguir la guía práctica [Crear una sesión de tmux para scripts largos](use-tmux-for-production-scripts.md). Está diseñada para quienes nunca han usado tmux: explica los pasos uno a uno y te guía a través de tu primera sesión en un servidor remoto.

