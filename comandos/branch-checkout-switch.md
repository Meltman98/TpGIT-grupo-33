# git branch, git checkout y git switch

# git branch

El comando `git branch` se usa para ver las ramas que existen en el repositorio
o para crear una nueva.

Para ver todas las ramas:
```bash
git branch
```

Para crear una rama nueva:
```bash
git branch nombre-de-la-rama
```

Para eliminar una rama:
```bash
git branch -d nombre-de-la-rama
```

# git checkout

El comando `git checkout` sirve para moverse entre ramas. Tambien se puede usar
para crear una rama y moverse a ella al mismo tiempo con el flag `-b`.

Para moverse a una rama existente:
```bash
git checkout nombre-de-la-rama
```

Para crear una rama nueva y moverse a ella:
```bash
git checkout -b nombre-de-la-rama
```

# git switch

`git switch` es básicamente lo mismo que `git checkout` pero más moderno y
específico para cambiar de rama. sirve para separar
funcionalidades que antes estaban todas en `git checkout`.

Para moverse a una rama:
```bash
git switch nombre-de-la-rama
```

Para crear una rama nueva y moverse:
```bash
git switch -c nombre-de-la-rama
```

# Diferencia entre checkout y switch

La diferencia principal es que `git switch` solo sirve para cambiar de rama,
mientras que `git checkout` hace eso y otras cosas más (como restaurar archivos).
Por eso se recomienda usar `git switch` cuando solo queres cambiar de rama,
ya que es más claro.