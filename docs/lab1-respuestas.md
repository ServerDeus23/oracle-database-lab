# Preguntas de Comprobación - Lab 1: Git Fundamentals

**Alumno:** Francisco de Borja Nguema
**Profesor:** Richard Aviles Lopez
**Repositorio Remoto:** https://github.com/ServerDeus23/oracle-database-lab.git

---

### 1. ¿Cuál es la diferencia entre Working Directory, Staging Area y Local Repository? Da un ejemplo de un archivo pasando por las tres.
* **Working Directory (Directorio de Trabajo):** Es la carpeta real en tu ordenador donde creas y editas los archivos.
* **Staging Area (Área de Preparación):** Es la zona intermedia donde eliges qué cambios exactos vas a guardar en la foto (commit).
* **Local Repository (Repositorio Local):** Es la base de datos de Git en tu ordenador (la carpeta `.git`) donde se guardan las fotos (commits) con el historial completo.
* **Ejemplo:**
  1. Creas `notas.txt` en la carpeta -> está en el **Working Directory**.
  2. Ejecutas `git add notas.txt` -> pasa al **Staging Area**.
  3. Ejecutas `git commit -m "docs: add notas"` -> se guarda en el **Local Repository**.

---

### 2. Si modificas un archivo pero no haces git add, ¿aparece ese cambio en tu próximo commit? Explica por qué.
No, no aparece. Porque `git commit` solo guarda lo que has metido previamente en la Staging Area con el comando `git add`. Si no haces `git add`, el cambio se queda únicamente en tu Working Directory.

---

### 3. ¿Por qué git status no mostraba las carpetas vacías que creaste en la Parte C? ¿Qué truco usamos para solucionarlo?
Porque Git solo rastrea archivos y sus contenidos, no carpetas vacías. Para solucionarlo usamos el truco de crear un archivo oculto y vacío llamado `.gitkeep` dentro de cada carpeta.

---

### 4. Explica con tus palabras qué es HEAD.
HEAD es como un marcador o indicador de "dónde estás parado ahora mismo". Le dice a Git en qué rama y en qué commit exacto te encuentras trabajando en tu terminal.

---

### 5. ¿Qué diferencia hay entre crear una branch con git switch -c y crear una carpeta nueva con mkdir? ¿Cómo lo comprobamos en la Parte G?
* `mkdir` crea una carpeta física real en el disco duro.
* `git switch -c` crea una rama en Git, que es solo una etiqueta o puntero apuntando a un commit, sin duplicar carpetas en tu disco duro.
* **Comprobación:** En la Parte G vimos que al cambiar de rama los archivos de nuestro disco duro cambiaban según la rama activa, pero la carpeta del proyecto seguía siendo la misma.

---

### 6. Durante el conflicto de la Parte H, ¿qué representaba el contenido entre <<<<<<< HEAD y =======? ¿Y entre ======= y >>>>>>>?
* **Entre `<<<<<<< HEAD` y `=======`:** Es el código/texto que teníamos en nuestra rama actual (donde estábamos parados).
* **Entre `=======` y `>>>>>>>`:** Es el código/texto diferente que venía de la otra rama que intentábamos fusionar.

---

### 7. ¿Por qué NO se debe hacer git commit --amend sobre un commit que ya se subió con git push?
Porque `--amend` cambia el código identificador (hash) del commit y borra el antiguo. Si ya lo habías subido a GitHub, crearás dos historiales distintos y provocará fallos graves al trabajar con otras personas.

---

### 8. Si borras por accidente la carpeta .git de tu proyecto, ¿qué se pierde exactamente? ¿Se pierde también el código fuente que está en el disco?
* **Se pierde:** Todo el historial de commits, las ramas, los mensajes y la configuración de Git.
* **NO se pierde:** Los archivos de tu código fuente actual que están en tu disco duro se quedan intactos.

---

### 9. Explica con tus propias palabras la diferencia entre Git y GitHub, sin usar la palabra "nube".
* **Git** es el programa que instalas en tu propio ordenador para llevar el control de cambios de tus archivos.
* **GitHub** es una página web/servicio remoto donde subes tu proyecto para guardarle una copia de respaldo y compartirlo con otros programadores.

---

### 10. ¿Por qué no se debe subir un archivo .env con contraseñas reales a un repositorio, aunque el repositorio sea privado?
Porque se queda guardado para siempre en el historial de commits de Git. Si alguien consigue acceso al proyecto en el futuro, o si por error el repositorio se vuelve público, las claves quedarían al descubierto.

---

### 11. Un compañero te dice: "hice push y ahora GitHub me rechaza el segundo push con 'non-fast-forward'". ¿Qué ha ocurrido probablemente y qué comando ejecutarías primero?
* **Lo que ocurrió:** Alguien subió cambios a GitHub antes que él, por lo que su copia local está desactualizada respecto a la de GitHub.
* **Comando a ejecutar primero:** `git pull` (o `git fetch` y luego `git merge`) para traerse los cambios del servidor antes de intentar subir los suyos.

---

### 12. ¿Qué tipo de Conventional Commit (feat, fix, docs, test…) usarías para:
* **Añadir un índice de rendimiento a una tabla:** `feat:` (o `perf:`).
* **Corregir una restricción mal definida:** `fix:`.
* **Actualizar el README:** `docs:`.