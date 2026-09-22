# Respuestas de la Práctica 1 - Git Fundamentals

**Alumno:** Francisco de Borja Nguema
**Profesor:** Richard Aviles Lopez
**Repositorio de GitHub:** https://github.com/ServerDeus23/oracle-database-lab.git

---

## Respuestas del Laboratorio

### 1. ¿Por qué usamos archivos .gitkeep?
Git no guarda carpetas que estén vacías. Para que Git pueda guardar las carpetas del proyecto (como `database/` o `scripts/`), le ponemos un archivo vacío dentro llamado `.gitkeep`.

### 2. ¿Para qué sirve la Staging Area (el área de preparación)?
Es como una caja intermedia. Sirve para revisar y elegir qué archivos queremos guardar antes de hacer el commit final. Con el comando `git add` metemos los archivos en esa caja.

### 3. ¿Cuándo se puede usar "git commit --amend" y cuándo no?
* **Sí se puede usar:** Cuando te equivocas en el mensaje de un commit que aún está en tu ordenador (local) y no lo has subido a GitHub.
* **No se debe usar:** Si el commit ya lo subiste a GitHub, porque le cambia la identificación al commit y causa fallos si trabajas con más gente.

### 4. ¿Qué pasa cuando cambias de rama con "git switch"?
Una rama es solo una marca que apunta a un momento del proyecto. Cuando cambias de rama, Git cambia los archivos que ves en tu carpeta para mostrarte exactamente cómo estaban en esa rama.

### 5. ¿Qué significan las marcas de conflicto (<<<<<<<, =======, >>>>>>>)?
* `<<<<<<< HEAD`: Es el principio de los cambios que tenías en tu rama actual.
* `=======`: Es la línea que separa tu versión de la versión que viene de la otra rama.
* `>>>>>>> nombre_rama`: Es el final de los cambios de la otra rama que intentabas juntar.
