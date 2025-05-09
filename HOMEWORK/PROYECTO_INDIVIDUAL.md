# PROYECTO INDIVIDUAL - FIGUEREDO MANCILLA JOSE ARMANDO

## EJERCICIO UNO - A

### Diferencia entre sistemas de control de versiones centralizados y distribuidos

#### Sistemas de Control de Versiones Centralizados (CVCS)

En un sistema centralizado, existe un único repositorio central que contiene todos los archivos versionados. Los desarrolladores "extraen" (checkout) los archivos del servidor central, los modifican localmente y luego "envían" (commit) los cambios de vuelta al servidor central. Ejemplos notables incluyen:

- **SVN (Subversion)**: Desarrollado como sucesor de CVS, ofrece commits atómicos y versionado de directorios.
- **CVS (Concurrent Versions System)**: Uno de los primeros sistemas populares de control de versiones.
- **Perforce**: Popular en industrias que manejan archivos grandes como videojuegos y diseño.

**Característica clave**: Todos los usuarios dependen de la disponibilidad del servidor central para realizar operaciones de control de versiones.

#### Sistemas de Control de Versiones Distribuidos (DVCS)

En un sistema distribuido, cada desarrollador tiene una copia completa del repositorio, incluyendo todo el historial. Esto permite trabajar de forma completamente independiente y sin conexión, ya que todas las operaciones (excepto compartir cambios) ocurren localmente. Ejemplos populares incluyen:

- **Git**: Desarrollado por Linus Torvalds para el desarrollo del kernel de Linux.
- **Mercurial**: Similar a Git en muchos aspectos, con énfasis en rendimiento y escalabilidad.
- **Bazaar**: Desarrollado por Canonical, utilizado en proyectos como Ubuntu.

**Característica clave**: La distribución completa del repositorio elimina el punto único de fallo y permite un trabajo más flexible y descentralizado.

## EJERCICIO UNO - B

### Verificación de instalación de Git

#### Comando utilizado:
```git --version```

#### Resultado obtenido:
![Captura de pantalla de verificación](/RESOURCES/version.png)

## EJERCICIO UNO - C

### Creación de Repositorio ProyectoInicial

Aunque ya estamos trabajando dentro de un repositorio Git, este ejercicio documenta cómo se crearía un nuevo repositorio desde cero:

#### Paso 1: Crear el directorio para el proyecto simulado
1. **Crea el directorio para el proyecto "ProyectoInicial"**
```mkdir ProyectoInicial```
```cd ProyectoInicial```

2. **En un caso real, inicializaría el repositorio Git:**
```git init```

Nota: Este paso se omite en la simulación ya que estamos dentro de un repositorio existente.
3. **Creación del archivo de presentación:**
```echo "Nombre: Tu Nombre" > presentacion.txt```
```echo "Descripción: Una breve descripción sobre ti o tus intereses en programación" >> presentacion.txt```

4. **En un caso real, agregaria el archivo al stating area**
```git add .```

5. **Realizar el commit inicial**
```git commit -m "Mensaje Descriptivo"```

#### Resultado obtenido:
![Captura de pantalla de verificación](/RESOURCES/creation.png)

## EJERCICIO DOS - A

### 5 buenas prácticas esenciales para trabajar con Git en equipo:

1. **Convención para nombres de ramas:**
   - Utilizar prefijos descriptivos como `feature/`, `bugfix/`, `hotfix/`, `release/`
   - Incluir el número de ticket/issue cuando sea aplicable: `feature/GIT-123-login-page`
   - Usar guiones para separar palabras: `feature/add-payment-integration`

2. **Mensajes de commit claros y estructurados:**
   - Usar formato imperativo: "Add feature" en lugar de "Added feature"
   - Limitar la primera línea a 50 caracteres como máximo
   - Incluir un cuerpo detallado separado por una línea en blanco cuando sea necesario
   - Referenciar issues/tickets: "Fix login error (closes #123)"

3. **Integración y sincronización frecuente:**
   - Hacer pull de la rama principal diariamente para evitar conflictos grandes
   - Mantener los commits pequeños y enfocados en un solo cambio lógico
   - Integrar cambios al menos una vez al día en proyectos de desarrollo activo

4. **Revisión de código y Pull Requests:**
   - No hacer merge de tus propios Pull Requests sin revisión
   - Incluir descripciones detalladas en los PR con contexto y propósito
   - Responder a comentarios de revisión con nuevos commits, no sobrescribiendo historial

5. **Gestión de conflictos:**
   - Resolver conflictos localmente antes de subir cambios
   - Documentar decisiones importantes tomadas durante la resolución de conflictos
   - Realizar pruebas después de resolver conflictos para verificar la integridad

## EJERCICIO DOS - B

### ¿Qué es un archivo .gitignore?

Un archivo `.gitignore` permite especificar archivos y directorios que Git debe ignorar y no rastrear. Esto es útil para:

- Excluir archivos generados automáticamente
- Evitar archivos de configuraciones personales
- Excluir directorios de dependencias que se pueden regenerar
- Evitar añadir archivos compilados o temporales
- Prevenir la inclusión accidental de información sensible

#### Patrones comunes en .gitignore

- `*` - Comodín que coincide con cualquier número de caracteres
- `?` - Comodín que coincide con un solo carácter
- `[abc]` - Coincide con cualquier carácter dentro de los corchetes
- `**` - Coincide con directorios anidados (ej: `logs/**/*.log`)
- `/ejemplo` - Ignora "ejemplo" solo en el directorio raíz
- `ejemplo/` - Ignora todos los directorios llamados "ejemplo"
- `!ejemplo.txt` - Negación: incluye este archivo aunque coincida con otro    patrón

### Creación de archivo .gitignore

He creado un archivo `.gitignore`. El archivo se encuentra en la raíz del repositorio y contiene los siguientes patrones:

#### Estructura del .gitignore implementado
![Captura de pantalla de verificación](/RESOURCES/ignore.png)

## EJERCICIO DOS - C

### ¿Qué es Versionado Semántico?

El Versionado Semántico (SemVer) es un conjunto de reglas que especifican cómo asignar y aumentar los números de versión. Sigue el formato: **X.Y.Z** (MAYOR.MENOR.PARCHE)

### Implementación de SemVer en un proyecto Git
![Captura de pantalla de verificación](/RESOURCES/tag.png)

#### 1. Estructura de versiones

- **X (MAYOR)**: Incrementar cuando se realizan cambios incompatibles con versiones anteriores
- **Y (MENOR)**: Incrementar cuando se añade funcionalidad nueva compatible con versiones anteriores
- **Z (PARCHE)**: Incrementar cuando se corrigen errores compatible con versiones anteriores

#### 2. Etiquetado de versiones en Git

```# Para la versión inicial```
```git tag -a v1.0.1 -m "Hasta ejercicio 2C"```

## EJERCICIO TRES - A

### ¿Qué es git revert?
El comando git revert permite deshacer cambios realizados en commits anteriores sin alterar el historial de Git. A diferencia de otros métodos para deshacer cambios, git revert crea un nuevo commit que deshace los cambios del commit especificado.
#### Implementación de git revert
#``` Supongamos que queremos revertir el commit con hash abc123```
```git revert abc123```

![Captura de pantalla de verificación](/RESOURCES/revert.png)

### Diferencias con otros métodos para deshacer cambios
![Captura de pantalla de verificación](/RESOURCES/table-revert.png)

### Ventajas de git revert:
- Es seguro para ramas compartidas
- Mantiene un registro completo de acciones
- No destruye el historial del proyecto
- Permite deshacer cambios específicos manteniendo los posteriores

## EJERCICIO TRES - B

### ¿Qué es git reset?
El comando git reset permite mover el puntero HEAD y la rama actual a un commit específico, con diferentes opciones para manejar el índice y el directorio de trabajo.

#### Las tres variantes principales de git reset:
1. **git reset --soft**
```git reset --soft HEAD~1```

- Efecto: Mueve solo HEAD al commit especificado
- Conserva: Cambios en el staging area y directorio de trabajo
- Uso común: Combinar varios commits en uno solo o reescribir mensajes de commit

2. **git reset --mixed (opción por defecto)**
```git reset HEAD~1```
 o
```git reset --mixed HEAD~1```

- Efecto: Mueve HEAD y actualiza el índice (staging area)
- Conserva: Cambios en el directorio de trabajo
- Uso común: Deshacer un git add o reorganizar cambios

3. **git reset --hard**
```git reset --hard HEAD~1```

- Efecto: Mueve HEAD, actualiza el índice y el directorio de trabajo
- Conserva: Nada, descarta todos los cambios
- Uso común: Descartar completamente commits erróneos (¡usar con precaución!)

#### Tabla comparativa de opciones:
![Captura de pantalla de verificación](/RESOURCES/table-reset.png)

⚠️ ADVERTENCIA: git reset --hard es potencialmente destructivo. Los cambios descartados pueden ser difíciles de recuperar si no se han guardado en otro lugar.

## EJERCICIO TRES - C

### ¿Qué es git reflog?
git reflog (reference log) es una herramienta que registra cuándo se actualizaron las referencias de Git (por ejemplo, ramas) en tu repositorio local. Actúa como una "red de seguridad" que permite recuperar commits que de otra manera podrían perderse.

#### Explorando reflog
```bash
# Ver el historial de referencias
git reflog

# Ver el historial de referencias para una rama específica
git reflog show main
```

#### Utilidad para recuperar cambios:

1. **Recuperar después de un reset destructivo:**

```bash
# Supongamos que hicimos un reset --hard accidental
git reset --hard HEAD~3  # Oops! Perdimos 3 commits


# Usamos reflog para ver el historial de referencias
git reflog
# Identificamos el commit donde estábamos antes del reset
# (ejemplo: HEAD@{5})

# Recuperamos los cambios
git reset --hard HEAD@{5}
```

2. **Recuperar una rama eliminada:**

```bash
# Si eliminamos una rama accidentalmente
git branch -D feature-branch  # Eliminación accidental

# Encontramos el último commit de esa rama en reflog
git reflog
# Localizamos el último commit de feature-branch (ej: abcd123)

# Recreamos la rama
git checkout -b feature-branch abcd123
```

#### Tiempo de retención:
Por defecto, las entradas de reflog se conservan:

- 30 días para entradas no expiradas
- 90 días para entradas accesibles desde refs

## EJERCICIO CUATRO - A

### ¿Qué son los aliases en Git?
Los aliases son atajos personalizados para comandos Git que usamos frecuentemente. Permiten definir comandos más cortos o combinar varios comandos en uno solo, aumentando significativamente la productividad.
#### Implementación de un alias para historial de commits
He implementado un alias personalizado llamado lg (log graphic) que muestra el historial de commits de manera gráfica, condensada y fácil de leer:
```git config --global alias.lg "log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative"```

![Captura de pantalla de verificación](/RESOURCES/aliases.png)
#### Otros aliases útiles implementados:
```bash
# Alias para verificar el estado de forma concisa
git config --global alias.st "status -sb"

# Alias para ver el último commit
git config --global alias.last "log -1 HEAD --stat"

# Alias para listar todos los aliases configurados
git config --global alias.aliases "config --get-regexp ^alias\."

# Alias para commits rápidos
git config --global alias.cm "commit -m"

# Alias para ver ramas con información adicional
git config --global alias.branches "branch -a -v"
```

#### Verificación de aliases configurados:
```bash
$ git aliases
alias.lg log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative
alias.st status -sb
alias.last log -1 HEAD --stat
alias.aliases config --get-regexp ^alias\.
alias.cm commit -m
alias.branches branch -a -v
```

## EJERCICIO CUATRO - A

### ¿Qué es git stash?
Git stash permite guardar temporalmente cambios que no están listos para commit, limpiando el área de trabajo sin perder modificaciones. Es especialmente útil cuando necesitas cambiar rápidamente de contexto o rama.
##### Uso básico de stash:
```bash
# Guardar cambios actuales en el stash
git stash

# Listar stashes guardados
git stash list

# Aplicar el último stash y mantenerlo en la lista
git stash apply

# Aplicar el último stash y eliminarlo de la lista
git stash pop

# Aplicar un stash específico
git stash apply stash@{2}
```
#### Opciones avanzadas de stash:
- Guardar con un mensaje descriptivo
```git stash save "Implementación parcial de login"```
- Guardar incluyendo archivos no rastreados
```bash
git stash -u
# o
git stash --include-untracked
```
- Guardar solo ciertos archivos
```git stash push -m "Cambios en funcionalidad X" path/to/file1 path/to/file2```
- Ver contenido de un stash
```git stash show -p stash@{0}```
- Crear una rama desde un stash
```git stash branch nueva-rama stash@{1}```
- Eliminar stashes
```bash
# Eliminar un stash específico
git stash drop stash@{2}

# Eliminar todos los stashes
git stash clear
```