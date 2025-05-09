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