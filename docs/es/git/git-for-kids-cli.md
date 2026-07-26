# Git para peques: ramas, commits y merges (solo CLI)

Esta guía enseña Git como si fuera un juego de historias.

- Sin GitHub.
- Sin `push (subir cambios)` ni `pull (bajar cambios)`.
- Solo Git local.

## Idea en 30 segundos

- Un `commit (guardado)` es un checkpoint guardado (una foto de tus archivos en un momento).
- Una `rama (branch)` es un camino alternativo para probar ideas sin riesgo.
- Un `merge (unión)` une un camino de vuelta a otro.

Piénsalo como construir una historia con finales alternativos.

## 1) Crea tu proyecto de historia

```bash
mkdir mi-primera-historia-git
cd mi-primera-historia-git
git init
```

Ahora tienes un repositorio Git local vacío.

## 2) Primer commit (primer checkpoint)

Crea un archivo y guárdalo en Git:

```bash
echo "Había una vez un dragón" > historia.txt
git add historia.txt
git commit -m "inicio de la historia"
```

Qué pasó:

- `git add` le dice a Git: "pon este archivo en el área de preparación".
- El área de preparación es la sala de espera del siguiente `commit`.
- Entonces `git commit` guarda solo los archivos que están en esa sala de espera.

Forma rápida de pensarlo:

- Editar archivo = escribir ideas.
- `git add` = elegir que ideas van a la mochila.
- `git commit` = cerrar la mochila y ponerle etiqueta.

Revisión útil:

```bash
git status
```

Si un archivo no está agregado, no entrará en el commit.

## 3) Crea una rama (camino alternativo)

```bash
git switch -c final-dragon
```

Ahora estás en la rama `final-dragon`.

Agrega un final distinto y haz commit:

```bash
echo "El dragón aprendió a cocinar" >> historia.txt
git add historia.txt
git commit -m "agregar final gracioso"
```

## 4) Vuelve a main y agrega otro cambio

```bash
git switch main
echo "Fin" >> historia.txt
git add historia.txt
git commit -m "agregar final principal"
```

Ahora ambas ramas cambiaron el mismo archivo de formas distintas.

## 5) Haz merge de ramas

```bash
git merge final-dragon
```

Si Git puede combinar cambios automáticamente, el merge termina al instante.
Si ambas ramas cambiaron las mismas líneas, Git te pedirá resolver un conflicto primero.

## 6) Visualiza el historial

```bash
git log --oneline --graph --all
```

Forma típica:

```text
*   9f3a2d1 merge branch 'final-dragon'
|\
| * 41ac0be agregar final gracioso
* | 82f9b77 agregar final principal
|/
* 57de301 inicio de la historia
```

## Dibujo simple de ramas

Antes del merge:

```text
*---*---*   (final-dragon)
     \
      *---* (main)
```

Después del merge:

```text
*---*---*\
     \    M  (main)
      *---*/
```

## Resumen rápido

- `commit (guardado)` = guardar checkpoint
- `rama (branch)` = camino nuevo
- `merge (unión)` = unir caminos

Eso es el núcleo de Git.
