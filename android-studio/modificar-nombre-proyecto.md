## Modificar el nombre a un proyecto en Android Studio

Partimos de que hay que tener seleccionado el tipo de visualización del proyecto en Android

Hay 3 elementos diferenciados que se pueden querer renombrar en un proyecto:

- La carpeta contenedora

    Si se cambia el nombre de dicha carpeta el proyecto se sigue ejecutando correctamente, ya que no hay ninguna referencia interna hacia ese parámetro. Tan solo queda registrada en el IDE como proyecto abierto recientemente.

- El nombre del proyecto
    1. Modificar en el archivo settings.gradle:
        - `rootProject.name = "XYZ"`

            Éste parámetro es el nombre interno del proyecto.

    2. Modificar en el archivo strings.xml:
        - `<string name="app_name">XYZ</string>`

            Éste parámetro es el nombre de la aplicación, tanto en el launcher como en la info de la app.

    3. **[OPCIONAL]** Refactorizar las referencias internas de las funciones autogeneradas:
        - AndroidManifest.xml:
            - `android:theme="@style/Theme.XYZ"`
        - ui.theme/Theme.kt
            - `fun XYZTheme(`

          Para refactorizar, nos colocamos encima del elemento y presionamos Shift+F6

- El nombre del paquete raíz
    1. Situarse encima del paquete raíz del proyecto y pulsar Shift+F6
    2. Elegir todos los directorios
    3. Marcar "Buscar en comentarios y cadenas" y "Buscar ocurrencias en texto"
    4. Refactorizar, comprobar cambios y aplicar
    5. **[IMPORTANTE]** Cerrar el IDE y borrar la carpeta .idea del proyecto

- **[BONUS]** Cambiar el dominio del paquete raíz
    1. Situarse encima del paquete raíz del proyecto y pulsar F6
    2. Elegir a directorio
    3. Cambiar el dominio, a partir de `java/`
        - Ejemplo: `java/foo/bar/XYZ` -> `java/qux/baz/XYZ`
    4. Marcar la casilla "Buscar referencias"
    5. Refactorizar
    6. Eliminar la carpeta que ha quedado vacia
        - En el ejemplo: foo.bar
