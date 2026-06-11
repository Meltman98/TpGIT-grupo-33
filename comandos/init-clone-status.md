# Git: init, clone, status

## git init

- Inicializa un repositorio Git en la carpeta actual en donde me haya parado con cd.
- Crea una carpeta oculta llamada `.git` dentro del proyecto.
- Uso básico:
  - `git init`
- A partir de este momento, Git puede controlar los cambios de los archivos en esa carpeta.
- Sirve para empezar a rastrear cambios en un proyecto nuevo.
- Ejemplo de como se emplea:
  | -`mkdir TpGIT-grupo-33`
  | -`cd /TpGIT-grupo-33`
  | -`git init`

## git clone

- Copia un repo remoto a la máquina local.
- Crea una carpeta con el proyecto y descarga el historial.
- Configura tmabien la conexión automática con Github.
- Uso básico:
  - `git clone <url-del-repositorio>`
- Ejemplo para el repo del proyecto:
  - `git clone https://github.com/Meltman98/TpGIT-grupo-33.git`
- Opcionalmente clona una rama específica:
  - `git clone -b <rama> <url>`

## git status

- Muestra el estado actual del repositorio.
- Indica archivos modificados, sin seguimiento y preparados para commit.
- Uso básico:
  - `git status`
- Ayuda a saber qué cambios faltan por agregar o confirmar.
- Ayuda a saber en que rama se esta parado y si esta actualizada con los datos remotos.
