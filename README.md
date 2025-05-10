# Git & GitHub:Guía Completa Completa 🐙

[![Git](https://img.shields.io/badge/Git-2.37+-f14e32?style=for-the-badge&logo=git&logoColor=white&labelColor=101010)](https://git-scm.com/)
[![GitHub](https://img.shields.io/badge/GitHub-Web-blue?style=for-the-badge&logo=github&logoColor=white&labelColor=101010)](https://github.com/)

## Introducción

Git es un sistema de control de versiones distribuido que permite a los programadores rastrear y administrar los cambios en su código fuente. Te proporciona una forma de guardar y documentar todas las modificaciones realizadas en tus archivos, lo que facilita la colaboración con otros desarrolladores y te ayuda a mantener un historial completo de tu proyecto.
Una de las principales ventajas de Git es su enfoque distribuido, lo que significa que todos los desarrolladores tienen una copia local completa del repositorio. Esto permite trabajar de manera independiente, sin depender de una conexión a Internet o un servidor.

## Comandos mis usados de Git y GitHub

### Configuración inicial

| Comando | Descripción |
| ------- | ----------- |
| `git config --global user.name "TuNombre"` | Configura el nombre que aparecerá en tus commits |
| `git config --global user.email tu@email.com` | Configura el email asociado a tus commits |
| `git config --global core.editor "editor"` | Configura el editor de texto predeterminado |
| `git config --list` | Muestra la configuración actual de Git |

### Crear y clonar repositorios

| Comando | Descripción |
| ------- | ----------- |
| `git init` | Inicia un nuevo repositorio local en el directorio actual |
| `git clone <url>` | Crea una copia local de un repositorio remoto |

### Estado y seguimiento de archivos

| Comando | Descripción |
| ------- | ----------- |
| `git status` | Muestra el estado de los archivos en el directorio de trabajo |
| `git add <archivo>` | Añade un archivo específico al área de preparación (staging) |
| `git add .` o `git add --all` | Añade todos los archivos modificados al área de preparación |
| `git rm <archivo>` | Elimina archivos del directorio de trabajo y del área de preparación |
| `git mv <original> <nuevo>` | Mueve o renombra un archivo |

### Commits y historial

| Comando | Descripción |
| ------- | ----------- |
| `git commit -m "mensaje"` | Confirma los cambios preparados con un mensaje descriptivo |
| `git commit` | Abre el editor configurado para escribir un mensaje de commit más elaborado |
| `git log` | Muestra el historial de commits |
| `git log --oneline` | Muestra el historial de commits en formato resumido |
| `git diff` | Muestra los cambios entre el directorio de trabajo y el área de preparación |
| `git diff --staged` | Muestra los cambios entre el área de preparación y el último commit |

### Ramas

| Comando | Descripción |
| ------- | ----------- |
| `git branch` | Lista todas las ramas locales |
| `git branch <nombre>` | Crea una nueva rama |
| `git branch -d <nombre>` | Elimina una rama |
| `git branch -M main` | Renombra la rama actual a "main" |
| `git checkout <rama>` | Cambia a la rama especificada |
| `git switch <rama>` | Cambia a la rama especificada (alternativa más reciente a checkout) |
| `git merge <rama>` | Fusiona la rama especificada con la rama actual |

### Deshacer cambios

| Comando | Descripción |
| ------- | ----------- |
| `git reset <commit>` | Deshace todos los commits posteriores al especificado, preservando los cambios localmente |
| `git reset --hard <commit>` | Deshace todos los commits posteriores al especificado, descartando todos los cambios |
| `git revert <commit>` | Crea un nuevo commit que deshace los cambios del commit especificado |
| `git checkout -- <archivo>` | Descarta los cambios en un archivo del directorio de trabajo |
| `git restore <archivo>` | Descarta los cambios en un archivo (alternativa más reciente) |

### Almacenamiento temporal

| Comando | Descripción |
| ------- | ----------- |
| `git stash` | Guarda temporalmente los cambios no confirmados |
| `git stash list` | Lista todos los stashes guardados |
| `git stash apply` | Aplica el último stash sin eliminarlo |
| `git stash pop` | Aplica el último stash y lo elimina |

### Trabajo con remotos

| Comando | Descripción |
| ------- | ----------- |
| `git remote` | Lista todos los repositorios remotos configurados |
| `git remote add <nombre> <url>` | Añade un nuevo repositorio remoto |
| `git remote -v` | Lista todos los repositorios remotos con sus URLs |
| `git remote show <nombre>` | Muestra información detallada de un remoto específico |
| `git fetch <remoto>` | Descarga contenido del repositorio remoto sin aplicar cambios |
| `git pull <remoto> <rama>` | Descarga contenido del repositorio remoto y lo integra automáticamente |
| `git push <remoto> <rama>` | Sube los commits locales a un repositorio remoto |
| `git push -u <remoto> <rama>` | Sube una rama y configura el seguimiento para futuros push/pull |
| `git push -u <remoto> --all` | Sube todas las ramas locales al remoto |

### Etiquetas

| Comando | Descripción |
| ------- | ----------- |
| `git tag` | Lista todas las etiquetas |
| `git tag <nombre>` | Crea una etiqueta ligera en el commit actual |
| `git tag -a <nombre> -m "mensaje"` | Crea una etiqueta anotada con mensaje |
| `git push <remoto> <tag>` | Sube una etiqueta específica al remoto |
| `git push <remoto> --tags` | Sube todas las etiquetas al remoto |

### Comandos avanzados

| Comando | Descripción |
| ------- | ----------- |
| `git cherry-pick <commit>` | Aplica los cambios de un commit específico en la rama actual |
| `git rebase <rama>` | Reaplica commits de la rama actual sobre otra rama |
| `git reflog` | Muestra un registro de todos los cambios en HEAD (útil para recuperar commits perdidos) |
| `git blame <archivo>` | Muestra quién modificó cada línea de un archivo y cuándo |
| `git bisect` | Herramienta para encontrar el commit que introdujo un bug |

## Flujo de trabajo con GitHub

### Flujo básico para contribuir a proyectos

1. **Fork**: Crear una copia del repositorio en tu cuenta de GitHub
2. **Clone**: Clonar tu fork a tu máquina local
3. **Branch**: Crear una rama para tus cambios
4. **Commit**: Hacer cambios y confirmarlos
5. **Push**: Subir tus cambios a tu fork
6. **Pull Request**: Solicitar que tus cambios sean incorporados al repositorio original

### Sincronizar un fork con el repositorio original

```bash
git remote add upstream <url-original>
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

## Enlaces de interés

- [Web oficial Git](https://git-scm.com) (Documentación, descarga...)
- [Libro de Git en Español](https://git-scm.com/book/es/v2) (Gratis)
- [Web oficial GitHub](https://github.com)
- [Documentación de GitHub](https://docs.github.com/es)
- [Configuración SSH para GitHub](https://docs.github.com/es/authentication/connecting-to-github-with-ssh/about-ssh)
- [Markdown en GitHub](https://docs.github.com/es/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
- [GitHub Pages](https://pages.github.com/)
- [GitHub Actions](https://github.com/features/actions)

---

Este README fusiona la información de varios repositorios educativos sobre Git y GitHub para proporcionar una referencia rápida de los comandos más utilizados. Si quieres aprender más en profundidad, te recomendamos seguir alguno de los cursos o tutoriales mencionados en los enlaces.
