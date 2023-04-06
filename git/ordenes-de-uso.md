## Órdenes de uso habitual de Git

### Commits

- Todas las ordenes se deben ejecutar dentro del repositorio (directorio)

Inicializar un repositorio

```
git init
```

Conocer el estado actual del repositorio

```
git status
```

Listar el histórico de versiones (commits)

```
git log
```

Añadir seguimiento y/o cambios sobre un  archivo o archivos

```
git add <file1.ext> <file2.ext> | mask | .
```

Descartar los cambios del archivo local

```
git restore <file1.ext> <file2.ext> | mask | .
```

Eliminar el seguimiento de un archivo o archivos, sin eliminar el local

```
git rm --cached <file1.ext> <file2.ext> | mask | .
```

Registrar los archivos en seguimiento permanentemente en el historial de versiones

```
git commit -m "Breve descripcion del archivo o los cambios del mismo"
```

Revisar un commit especifico temporalmente

```
git checkout <id_commit> | [master | headname]
```

Volver a un commit específico definitivamente. La opción hard aplica los cambios localmente

```
git reset <id_commit> [--hard]
```

### Ramas

Listar las ramas disponibles

```
git branch
```

Modificar el nombre de una rama

```
git branch --move <old_name> <new_name>
```

Crear una rama nueva a partir de una existente

```
git branch <branch_name>
```

Cambiar de rama activa

```
git checkout <branch_name>
```

Fusionar dos ramas

```
git checkout <branch_to_merge>
git merge <branch_from_merge>
```

Resolución de conflictos

```
Decidir que codigo se va a quedar en el archivo y realizar un commit normal
git commit -am "Solución al conflicto"
```

### Repositorio remoto

Listar los repositorios remotos asociados

```
git remote -v
```

Añadir y vincular repositorio remoto

```
git remote add <remote_repo_name> <url>
```

Sincronizar repositorio local -> remoto

```
git push <remote_repo_name> <branch_to_push>
```

Sincronizar repositorio remoto -> local

```
git pull <remote_repo_name> <branch_to_pull>
```

Comparar cambios repositorio remoto -> local

```
git fetch
git diff <remote_repo_name> <local_branch>
```

### Releases

Listar los tags (releases) actuales del proyecto

```
git tag
```

Añadir un tag

```
git tag -a <tag_name> -m "Breve descripción del tag/release" <id_commit>
```

Eliminar un tag

```
git tag -d <tag_name>
```

Sincronizar los tags con el repositorio remoto

```
git push <remote_repo_name> --tags
```

Eliminar un tag de un repositorio remoto

```
git push <remote_repo_name> :refs/tags/<tag_name>
```
