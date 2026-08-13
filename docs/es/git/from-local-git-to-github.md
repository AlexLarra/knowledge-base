---
title: De Git local a GitHub
---

# De Git local a GitHub

Esta guía es una ampliación de [Git para niños](git-for-kids-cli.md).
Allí aprendiste a guardar tu historia localmente con `commit`, `branch` y `merge`.
Aquí veremos cómo llevar esos cambios a la nube y compartirlos.

## De local a la nube

Git por sí solo trabaja en tu ordenador. Pero si quieres:

- una copia de seguridad fuera de tu máquina,
- o trabajar con otras personas,

necesitas un **servicio de alojamiento** para tu repositorio.

GitHub es el más conocido y usado. GitLab es una alternativa muy válida,
especialmente en entornos profesionales y de código abierto que buscan
herramientas de integración continua más integradas.

## Lo que necesitas antes de empezar

- Una cuenta en GitHub (o GitLab).
- Un repositorio creado en la plataforma, ya sea clonando uno existente o
  iniciando uno nuevo.

No entraremos en detalles de la web; asumimos que ya tienes el repositorio
remoto listo.

## Los comandos nuevos

| Comando | Qué hace |
|---------|----------|
| `git clone URL` | Descarga un repositorio remoto a tu ordenador |
| `git push` | Sube tus commits locales al remoto |
| `git pull` | Baja los commits nuevos del remoto a tu rama local |

## Flujo de trabajo habitual

1. Trabajas en tu ordenador: editas archivos, haces `git add` y
   `git commit` (igual que aprendiste en la guía anterior).
2. Cuando quieres compartir tu progreso: `git push`.
3. Si otros han hecho cambios: `git pull` para traerlos antes de seguir.

Esto es lo mismo que el juego de la historia, pero ahora la historia vive en
la nube y varias personas pueden escribirla.

## Subir una rama nueva por primera vez

Cuando creas una rama local con `git switch -c` y haces commits en ella,
`git push` solo no funcionará porque Git aún no sabe a qué rama remota
pertenece.

Tienes que decirle dónde subirla la primera vez:

```bash
git push -u origin nombre_de_rama
```

La opción `-u` (o `--set-upstream`) crea el enlace entre tu rama local y la
remota. A partir de ahí, solo `git push` en esa rama será suficiente.

## Nota final sobre integración de cambios

Cuando bajes cambios con `git pull`, Git puede fusionarlos automáticamente o
pedirte que resuelvas conflictos, igual que con `git merge` local. Para
mantener un historial más limpio, conviene configurar Git para que use
**rebase por defecto** al hacer pull:

```bash
git config --global pull.rebase true
```

Con esto, tus commits locales se reaplican encima de los nuevos cambios
descargados, generando una línea de historia más ordenada.
