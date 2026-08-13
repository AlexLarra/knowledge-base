---
title: Crear un workspace con tmux
---

# Crear un workspace con tmux

Abrir terminales, navegar a cada proyecto y ejecutar comandos a mano cada mañana es repetitivo. Con un script de tmux puedes levantar tu entorno completo en segundos con un solo comando.

## El objetivo

Queremos que al escribir `tw` en la terminal ocurra esto:

- Si ya existe una sesión llamada `work`, tmux se conecta a ella.
- Si no existe, se crea automáticamente con dos ventanas preparadas para trabajar.

## Paso 1: crea el script de inicio

Guarda este archivo en tu home como `~/.tmux_work.zsh`:

```zsh
#!/bin/zsh

SESSION="work"

tmux new -s $SESSION -d

# Ventana 1: aplicación principal
tmux send-keys -t $SESSION 'cd ~/workspace/app1 && clear' C-m
tmux split-window -v
tmux send-keys -t $SESSION 'cd ~/workspace/app1 && clear' C-m
tmux send-keys -t $SESSION 'npm run dev' C-m
tmux select-pane -t 1

# Ventana 2: api o backend
tmux new-window -t $SESSION
tmux send-keys -t $SESSION 'cd ~/workspace/app2 && clear' C-m
tmux split-window -h
tmux send-keys -t $SESSION 'cd ~/workspace/app2 && clear' C-m
tmux send-keys -t $SESSION 'python manage.py runserver' C-m
tmux select-pane -t 1

tmux select-window -t $SESSION:1
tmux attach -t $SESSION
```

Ajusta las rutas (`~/workspace/app1`, `~/workspace/app2`) y los comandos (`npm run dev`, `python manage.py runserver`) a los que uses en tu día a día.

Dale permisos de ejecución:

```sh
chmod +x ~/.tmux_work.zsh
```

## Paso 2: crea el alias

Añade esto a tu `~/.zshrc` (o `~/.bashrc`):

```sh
alias tw="tmux attach -t work || sh ~/.tmux_work.zsh"
```

Recarga la configuración:

```sh
source ~/.zshrc
```

## Paso 3: úsalo

Escribe `tw` y tmux hará el resto.

```sh
tw
```

## Paso 4: cierra la sesión

Si quieres cerrar todo y eliminar la sesión:

```sh
tmux kill-session -t work
```

También puedes desacoplarla (`Ctrl + b`, luego `d`) para dejarla corriendo en segundo plano.

---

> Aunque añaden dependencias, también tienes alternativas como **tmuxinator** o **tmuxp** que permiten definir sesiones mediante archivos de configuración YAML.
