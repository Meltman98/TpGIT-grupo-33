# git merge y git rebase

# git merge

El comando `git merge` sirve para unir dos ramas. Cuando terminas de trabajar
en una rama y queres incorporar los cambios a main, usas merge.

```bash
git merge nombre-de-la-rama
```

Hay dos tipos de merge:

**Fast-forward**: pasa cuando la rama principal no tuvo cambios desde que
creaste tu rama. git solo mueve el puntero hacia adelante, no crea
un commit de merge.

**3-way merge**: pasa cuando ambas ramas tuvieron cambios. git crea un commit
nuevo que une los dos historiales.

# git rebase

El comando `git rebase` sirve para integrar cambios de una rama a otra
pero de una manera diferente. En vez de crear un commit de merge,
mueve los commits arriba de la rama destino, como si hubieras empezado
a trabajar desde ese punto.

```bash
git rebase nombre-de-la-rama
```

# Diferencia entre merge y rebase

La diferencia principal es el historial que dejan. El merge conserva el
historial exacto de como pasaron las cosas, con el commit de union incluido.
El rebase deja un historial mas limpio y lineal, pero reescribe los commits.