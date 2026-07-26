# Crear una sesión de `tmux` en un servidor conectado por SSH para scripts largos

Cuando tienes un script que tardará bastante en ejecutarse en un servidor, conviene usar `tmux` para mantener el proceso activo aunque cierres la conexión SSH. Aquí tienes una guía paso a paso.

## Paso 1: conéctate al servidor

Usa SSH para conectarte al servidor.

```
ssh user@your-server.com
```

Recuerda la máquina concreta a la que te conectaste (por ejemplo, `app01`). La sesión de `tmux` vive solo en esa máquina, así que cuando vuelvas a entrar confirma que estás en la misma.

## Paso 2: inicia una sesión de `tmux`

Inicia una sesión nueva de `tmux`. Puedes ponerle nombre para identificarla fácil.

```
tmux new -s script
```

## Paso 3: ejecuta tu script

```
cd /path/to/your/project
# Opción A: ejecutar un script/comando directo
./your-long-running-script.sh

# Opción B: abrir una consola interactiva y ejecutar ahí el script
bundle exec rails c -e production
# o (ejemplo)
python manage.py shell
```

Una vez dentro de la consola, pega o ejecuta el script que necesitas. Deja logs de progreso pequeños (por ejemplo `puts` en Ruby, `print` en Python) para validar que sigue avanzando.

## Paso 4: desacopla la sesión de `tmux`

Desacopla la sesión de `tmux` y deja el script corriendo en segundo plano.

```
Ctrl + b, luego d
```

Pulsa `Ctrl` y `b` al mismo tiempo, suelta ambas teclas y luego pulsa `d`. Eso desacopla la sesión.

## Paso 5: vuelve a entrar en la sesión de tmux

Para revisar el progreso del script o volver a entrar en cualquier momento, conéctate al servidor (confirmando que estás en la máquina correcta) y lista las sesiones activas de `tmux`:

```
tmux ls
```

Tu sesión `script` debería aparecer en la lista.

Vuelve a entrar con:

```
tmux attach -t script
```

## Paso 6: elimina una sesión de tmux

Cuando el script termine y ya no necesites la sesión, puedes eliminarla. Si ya estás dentro, usa `Ctrl + d` como siempre. Si estás fuera y quieres cerrarla en remoto, usa:

```
tmux kill-session -t script
```
