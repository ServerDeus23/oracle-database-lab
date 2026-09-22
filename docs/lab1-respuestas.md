# Mis Respuestas de Comprobación - Lab 1: Git Fundamentals

**Alumno:** Francisco de Borja Nguema
**Profesor:** Richard Aviles Lopez
**Mi Repositorio:** https://github.com/ServerDeus23/oracle-database-lab.git

---

### 1. ¿Cuál es la diferencia entre Working Directory, Staging Area y Local Repository? Da un ejemplo de un archivo pasando por las tres.
* **Working Directory:** Es simplemente la carpeta de mi ordenador donde trabajo, creo archivos y edito código en el día a día.
* **Staging Area:** Es como un borrador o un paso intermedio donde voy preparando y seleccionando los cambios exactos que quiero guardar.
* **Local Repository:** Es la base de datos interna de Git (la carpeta `.git`) donde ya se quedan guardadas todas mis capturas de pantalla (commits) con el historial del proyecto.
* **Ejemplo con un archivo mío:**
  1. Creo el archivo `notas.txt` en mi carpeta de trabajo -> está en mi **Working Directory**.
  2. Hago `git add notas.txt` -> lo muevo al **Staging Area** para dejarlo listo.
  3. Ejecuto `git commit -m "docs: add notas"` -> se guarda definitivamente en mi **Local Repository**.

---

### 2. Si modificas un archivo pero no haces git add, ¿aparece ese cambio en tu próximo commit? Explica por qué.
No, para nada. Me di cuenta de que Git solo guarda en el commit lo que he metido antes en el Staging Area usando `git add`. Si se me olvida hacer el `git add`, ese cambio se queda solo en mi carpeta de trabajo y Git no lo incluye en la "foto".

---

### 3. ¿Por qué git status no mostraba las carpetas vacías que creaste en la Parte C? ¿Qué truco usamos para solucionarlo?
Porque Git solo rastrea archivos y lo que hay dentro de ellos, las carpetas vacías pasa de ellas. Para solucionar esto y obligar a Git a guardar la estructura de carpetas, usé el truco de meter un archivo oculto y vacío llamado `.gitkeep` dentro de cada una.

---

### 4. Explica con tus palabras qué es HEAD.
Para mí HEAD es básicamente el indicador de "dónde estoy parado ahora mismo". Le dice a Git en qué rama y en qué commit concreto estoy trabajando en mi terminal.

---

### 5. ¿Qué diferencia hay entre crear una branch con git switch -c y crear una carpeta nueva con mkdir? ¿Cómo lo comprobamos en la Parte G?
* `mkdir` te crea una carpeta física de verdad en tu disco duro.
* `git switch -c` crea una rama en Git, que es solo un puntero o una etiqueta que apunta a un momento del proyecto, sin andar duplicando carpetas en la máquina.
* **Cómo lo comprobé:** En la Parte G vi que al cambiar de rama con `git switch`, los archivos de mi carpeta cambiaban según la rama en la que me pusiera, pero la carpeta física de mi proyecto en el disco era siempre la misma.

---

### 6. Durante el conflicto de la Parte H, ¿qué representaba el contenido entre <<<<<<< HEAD y =======? ¿Y entre ======= y >>>>>>>?
* **Entre `<<<<<<< HEAD` y `=======`:** Era el texto que yo tenía en mi rama actual (donde estaba parado).
* **Entre `=======` y `>>>>>>>`:** Era el texto diferente que Venía de la otra rama que estaba intentando juntar.

---

### 7. ¿Por qué NO se debe hacer git commit --amend sobre un commit que ya se subió con git push?
Porque `--amend` lo que hace es modificar el commit y cambiarle su código identificador (el hash). Si ya lo había subido a GitHub y le cambio el ID en local, la lío porque creo dos historiales diferentes y luego da fallos al trabajar con más gente.

---

### 8. Si borras por accidente la carpeta .git de tu proyecto, ¿qué se pierde exactamente? ¿Se pierde también el código fuente que está en el disco?
* **Lo que pierdo:** Todo el historial de commits, las ramas que he creado, los mensajes y la configuración de Git.
* **Lo que NO pierdo:** Mi código y los archivos que tengo en la carpeta del ordenador no se borran, se quedan tal cual están.

---

### 9. Explica con tus propias palabras la diferencia entre Git y GitHub, sin usar la palabra "nube".
* **Git** es la herramienta/programa que tengo instalado en mi ordenador para controlar los cambios de mi código.
* **GitHub** es la página web donde subo mi proyecto para tener una copia de seguridad online y poder enseñarlo o trabajar con otros compañeros.

---

### 10. ¿Por qué no se debe subir un archivo .env con contraseñas reales a un repositorio, aunque el repositorio sea privado?
Porque se queda grabado para siempre en el historial de commits de Git. Si más adelante le doy acceso a alguien o el repositorio se vuelve público por error, cualquiera podría ver mis contraseñas o claves secretas.

---

### 11. Un compañero te dice: "hice push y ahora GitHub me rechaza el segundo push con 'non-fast-forward'". ¿Qué ha ocurrido probablemente y qué comando ejecutarías primero?
* **Lo que ha pasado:** Alguien ha subido cambios a GitHub antes que él, así que su versión local se ha quedado atrasada con respecto a la del servidor.
* **Lo que le diría que haga:** Que ejecute primero un `git pull` para bajarse los cambios del servidor, juntarlos con lo suyo y ya después hacer el `git push`.

---

### 12. ¿Qué tipo de Conventional Commit (feat, fix, docs, test…) usarías para:
* **Añadir un índice de rendimiento a una tabla:** `feat:` (o `perf:`).
* **Corregir una restricción mal definida:** `fix:`.
* **Actualizar el README:** `docs:`.