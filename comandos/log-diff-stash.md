# git log, git diff y git stash

# git log

El comando `git log` sirve para ver el historial de commits del repositorio.
Muestra el hash de cada commit, el autor, la fecha y el mensaje.

```bash
git log
```

Para verlo mas resumido, un commit por linea:

```bash
git log --oneline
```

# git diff

El comando `git diff` sirve para ver los cambios que todavia no fueron
agregados al staging area, es decir, lo que modificaste pero no hiciste
git add todavia.

```bash
git diff
```

Para ver los cambios que ya estan en staging:

```bash
git diff --staged
```

# git stash

El comando `git stash` sirve para guardar temporalmente los cambios que
todavia no commiteaste, sin perderlos. Es util cuando necesitas cambiar
de rama rapido pero no queres hacer un commit todavia..

Para guardar los cambios:

```bash
git stash
```

Para recuperarlos despues:

```bash
git stash pop
```

Para ver la lista de stash guardados:

```bash
git stash list
```
