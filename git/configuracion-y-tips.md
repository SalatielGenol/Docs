### Configuraciones típicas y tips para Git

#### Configurar la identidad del usuario de git

```
git config --global user.name "Paco Porras"
git config --global user.email paco@porras.org
```

#### .gitignore

En la carpeta raiz del proyecto, o subcarpeta:

```
echo {"file_to_ignore" | "/folder/to/ignore"} >> .gitignore
git add .gitignore
git commit -m "Comentario sobre .gitignore"
```

#### Mantener una carpeta vacía en el proyecto

Añadir dentro de la carpeta un .gitignore con el siguiente contenido:
```
*
!.gitignore
```

#### README.md

README.md es un archivo que se ubica en la raíz del proyecto y que debe incluir una descripción del mismo, así como toda la documentación que sea relevante para entender su construcción o manejo.

Se puede implementar en HTML puro o con Markdown, que es el mayormente utilizado debido a su facilidad de lectura tanto en texto plano, como interpretado mediante el navegador (a través de webs que lo permiten, como Github, etc).

Un buen editor online de archivos Markdown es [Editor.md](https://pandao.github.io/editor.md/en.html)
