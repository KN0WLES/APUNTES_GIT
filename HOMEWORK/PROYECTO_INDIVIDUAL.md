# PROYECTO INDIVIDUAL - FIGUEREDO MANCILLA JOSE ARMANDO

## EJERCICIO UNO

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