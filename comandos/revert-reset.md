# git revert y git reset

## git revert

El comando `git revert` sirve para deshacer un commit pero sin borrarlo
del historial. Crea un commit nuevo que hace lo contrario al commit
que queres deshacer.

```bash
git revert hash-del-commit
```

## git reset

El comando `git reset` sirve para deshacer cambios moviendo el puntero
head hacia atras. A diferencia de revert, este si modifica el historial.

Para sacar archivos del staging area sin perder los cambios:

```bash
git reset HEAD nombre-del-archivo
```

Para volver a un commit anterior conservando los cambios en los archivos:

```bash
git reset --soft hash-del-commit
```

Para volver a un commit anterior y descartar todos los cambios:

```bash
git reset --hard hash-del-commit
```

## Diferencia entre revert y reset

La diferencia principal es que revert es seguro para usar en ramas
compartidas porque no reescribe el historial, solo agrega un commit nuevo.
Reset en cambio modifica el historial.esto es un error
