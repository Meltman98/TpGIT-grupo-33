# Push, Pull, Fetch y Remote

## Descripción general

Los comandos `git push`, `git pull`, `git fetch` y `git remote` son los que dejan sincronizar el repositorio local con el remoto y trabajar con ramas compartidas.

- `git remote`: administra referencias a repositorios remotos.
- `git fetch`: descarga cambios del remoto sin integrarlos automáticamente.
- `git pull`: descarga e integra cambios automáticamente.
- `git push`: sube commits locales al remoto.

---

## `git remote`

### ¿Qué hace?

`git remote` muestra y configura repositorios remotos asociados a tu repositorio local. Un remoto es simplemente un alias para una URL.

### Comandos comunes

```bash
git remote     # lista todos los repos remotos configurados con sus nombres

git remote -v     # lista remotos con URLs

git remote add origin https://github.com/usuario/repo.git   # agrega un remoto con nombre origin

git remote remove origin   # elimina un remoto con nombre origin

git remote set-url origin https://github.com/usuario/nuevo.git   # cambia la URL del remoto origin
```

### Uso típico

- `origin`: nombre convencional para el remoto principal.

- `upstream`: nombre convencional para el repositorio original cuando se trabaja en fork de otro proyecto.

---

## `git fetch`

### ¿Qué hace?

`git fetch` descarga las referencias y commits del remoto al local, pero no cambia la rama activa. Esto actualiza las ramas remotas como `origin/main`, permitiéndo revisar los cambios antes de integrarlos y resolver los conflitos.

### Sintaxis básica

```bash
git fetch       # obtiene cambios de todos los remotos

git fetch origin      # cambios solo de origin

git fetch origin main     # solo la rama main de origin
```

### ¿Por qué usarlo?

- Ver qué cambios está haciendo el equipo sin mezclarlos de inmediato.
- Actualizar referencias remotas antes de comparar o rebasar.
- Evitar sorpresas en `pull` si hay conflictos.
- Preparar el terreno para un merge o rebase manual.

## `git pull`

### ¿Qué hace?

El `git pull` es parecido a `git fetch` seguido de `git merge`. Descarga los cambios remotos y luego los integra en la rama local activa.

### Sintaxis básica

```bash
git pull                  # obtiene e integra cambios del remoto configurado
git pull origin main      # obtiene e integra origin/main
git pull --rebase          # obtiene y rebasa tus commits sobre los cambios remotos
```

### Cuándo usarlo

- Cuando quieres sincronizar tu rama local con la rama remota rápidamente.
- En flujos donde aceptas merge automático o rebase.

## `git push`

### ¿Qué hace?

`git push` sube los commits confirmados de la rama local a la remota. Cambia el historial remoto para incluir tus cambios.

### Sintaxis básica

```bash
git push                 # empuja la rama local actual al remoto configurado
git push origin main     # empuja main a origin
git push -u origin feature/nueva  # crea la rama remota y la asocia con la local
git push --force         # fuerza la actualización remota y "pisa" los cambios de otros.
git push --force-with-lease  # fuerza solo si el remoto no ha cambiado desde tu última actualización
```

---

## Escenarios típicos

### 1. Ver cambios antes de integrar

```bash
git fetch origin

git diff HEAD origin/main

git log --oneline HEAD..origin/main
```

### 2. Actualizar tu rama local con seguridad

```bash
git fetch origin
git merge origin/main
```

### 3. Sincronizar y subir tu trabajo

```bash
git add .
git commit -m "feat: implementar nueva funcionalidad"
git push origin feature/nueva
```

### 4. Trabajar con forks

```bash
git remote add upstream https://github.com/proyecto/original.git
git fetch upstream
git merge upstream/main
git push origin main
```

## Referencias

- [Documentación oficial de Git](https://git-scm.com/docs)
- [w3schools Git Tutorial Push](https://www.w3schools.com/git/git_push_to_remote.asp?remote=github)
- [w3schools Git Tutorial Pull](https://www.w3schools.com/git/git_pull.asp?remote=github)
- [w3schools Git Tutorial Fetch](https://www.w3schools.com/git/git_fetch.asp?remote=github)
