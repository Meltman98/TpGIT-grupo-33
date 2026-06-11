# Git Add y Git Commit

`git add` y `git commit` son de los comandos mas importantes de Git.
Trabajan en conjuntos para guardar cambios en el historial del repositorio:

- **`git add`**: Prepara cambios para ser guardados y los pone en el staging area, algo asi como poner en escenario a los actores.
- **`git commit`**: Registra los cambios preparados en el historial del repositorio y pone un titulo descriptivo de los cambios.

---

## Git Add

El comando `git add` mueve archivos modificados al staging area o index. Esto te permite elegir exactamente qué cambios queres incluir en el próximo commit.

### Sintaxis básica

```bash
git add <archivo>          # Añade un archivo específico
git add <archivo1> <archivo2>  # Añade múltiples archivos
git add .                  # Añade todos los cambios
git add *.js               # Añade todos los .js
git add -A                 # Añade todos los cambios (equivalente a git add .)
git add -p                 # Modo interactivo (revisar cambios antes de añadir)
```

### Estados de un archivo

```
Untracked (no rastreado) → git add → Staged (preparado)
Modified (modificado) → git add → Staged
Staged → git commit → Committed (confirmado)
```

---

## Git Commit

### ¿Qué hace?

El comando `git commit` guarda permanentemente los cambios que están en el área de preparación. Crea un nuevo punto de referencia en el historial del repositorio.

### Sintaxis básica

```bash
git commit -m "mensaje"           # Commit con mensaje en línea
git commit -m "título" -m "descripción"  # Commit con título y descripción
git commit --allow-empty -m "mensaje"    # Commit vacío
git commit --amend                # Modificar el último commit
git commit --amend --no-edit      # Añadir cambios al último commit sin editar mensaje
```

### Importancia de buenos mensajes de Commit

Un buen mensaje de commit:

- Explica qué cambió y por qué
- Facilita la búsqueda en el historial
- Ayuda a otros (y a tu yo futuro) a entender el contexto
- Es esencial para mantener un historial limpio y profesional

## Conventional Commits

### ¿Qué son?

Es una especificación para añadir significado a los mensajes de commit usando una estructura específica.

### Formato

```
<tipo>[alcance opcional]: <descripción>

[cuerpo opcional]

[pie(s) opcional(es)]
```

### Tipos comunes

| Tipo       | Descripción                             | Versión       |
| ---------- | --------------------------------------- | ------------- |
| `feat`     | Nueva característica                    | Minor (1.1.0) |
| `fix`      | Corrección de bug                       | Patch (1.0.1) |
| `docs`     | Cambios en documentación                | -             |
| `style`    | Cambios de formato (sin lógica)         | -             |
| `refactor` | Refactorización sin cambios funcionales | -             |
| `perf`     | Mejoras de rendimiento                  | Patch         |
| `test`     | Agregar o actualizar tests              | -             |
| `chore`    | Tareas mantenimiento, dependencias      | -             |
| `ci`       | Cambios en CI/CD                        | -             |

## Flujo típico completo

```bash
# 1. Ver qué ha cambiado
git status

# 2. Preparar cambios específicos
git add src/feature.js
git add tests/feature.test.js

# 3. Revisar cambios preparados
git diff --staged

# 4. Hacer commit con mensaje descriptivo
git commit -m "feat(feature): implementar nueva funcionalidad"

# 5. Verificar el commit
git log --oneline -1
```

## Referencias

- [Documentación oficial de Git](https://git-scm.com/docs)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [How to Write a Git Commit Message - Chris Beams](https://chris.beams.io/posts/git-commit/)
