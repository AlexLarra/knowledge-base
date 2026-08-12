---
title: diff-so-fancy (opcional)
---

# diff-so-fancy

> **Nota:** Esto es completamente opcional. No es necesario para usar Git. Es una mejora de comodidad para quienes ya llevan un tiempo trabajando con `git diff` y quieren que la salida sea más legible.

## Qué hace

`diff-so-fancy` mejora la presentación de los diffs de Git. Convierte la salida cruda de `git diff` en algo más limpio, con colores diferenciados y sin los símbolos `+` y `-` al inicio de cada línea.

Es útil cuando revisas cambios con frecuencia y prefieres una lectura más amable.

## Instalación

Antes de instalar por otros medios, comprueba si tu distribución lo incluye en sus repositorios oficiales.

### Linux

**Arch Linux:**

```bash
sudo pacman -S diff-so-fancy
```

**Debian / Ubuntu:**

```bash
sudo apt install diff-so-fancy
```

### macOS

```bash
brew install diff-so-fancy
```

### Si no está en los repositorios

Puedes instalarlo vía npm:

```bash
npm install -g diff-so-fancy
```

O descargar el script directamente desde su [repositorio oficial](https://github.com/so-fancy/diff-so-fancy).

## Configuración con `.gitconfig`

La forma habitual de usarlo es configurando Git para que pase la salida de `git diff` (y comandos relacionados) a través de `diff-so-fancy`.

Añade o modifica las siguientes secciones en tu archivo `~/.gitconfig`:

```ini
[core]
    pager = diff-so-fancy | less --tabs=4 -RFX

[color]
    ui = true

[color "diff-highlight"]
    oldNormal = red bold
    oldHighlight = red bold 52
    newNormal = green bold
    newHighlight = green bold 22

[color "diff"]
    meta = 11
    frag = magenta bold
    commit = yellow bold
    old = red bold
    new = green bold
    whitespace = red reverse
```

Con esto, comandos como `git diff`, `git log -p` o `git show` usarán automáticamente `diff-so-fancy`.

## ¿Y ahora qué?

Abre cualquier repositorio y ejecuta `git diff`. Si todo está configurado, verás una salida más limpia y con mejor uso del color.

Si algo no funciona, verifica que `diff-so-fancy` esté en tu `PATH` ejecutando `which diff-so-fancy`.
