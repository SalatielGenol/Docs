## Mantener actualizadas las dependencias de un proyecto

Nota: ésto no es obligatorio, y habrá veces que no se deba realizar ya que parte de nuestro código
esté implementado con librerías que, de actualizarse, romperán el buen funcionamiento de la aplicación.

Por lo que para ello es necesario documentarse sobre que cambios han hecho en la librería, y aplicarlos
a nuestro código una vez actualizada la dependencia.

1. Modificar en el archivo build.gradle del módulo (en éste caso app):
    - `implementation 'androidx.core:core-ktx:X.X.X'`
        - https://developer.android.com/jetpack/androidx/releases/core
    - `implementation 'androidx.lifecycle:lifecycle-runtime-ktx:X.X.X'`
        - https://developer.android.com/jetpack/androidx/releases/lifecycle
    - `implementation 'androidx.activity:activity-compose:X.X.X'`
        - https://developer.android.com/jetpack/androidx/releases/activity
    - `implementation 'androidx.compose.material:material:X.X.X'`
        - https://developer.android.com/jetpack/androidx/releases/compose-material

        Para modificar los valores de las versiones no es necesario ir visitando los enlaces, bastará con pulsar Alt+Enter encima de la librería que queramos actualizar, y el IDE nos hará la sugerencia de la última versión disponible.

    - `kotlinCompilerExtensionVersion 'X.X.X'`
        - https://developer.android.com/jetpack/androidx/releases/compose-compiler

    Éste es el compilador de compose, y está directamente relacionado con la versión de kotlin que se utiliza en el proyecto, que se trata en el siguiente punto.

2. Modificar en el archivo build.graddle del proyecto:
    - `compose_ui_version = 'X.X.X'`
        - https://developer.android.com/jetpack/androidx/releases/compose-ui

    **[OPCIONAL]**
    - `id 'com.android.application' version 'X.X.X' apply false`
    - `id 'com.android.library' version 'X.X.X' apply false`
        - https://developer.android.com/reference/tools/gradle-api
        - https://developer.android.com/build/releases/gradle-plugin

    Éstos dos parámetros se refieren al plugin de gradle dentro de android studio, y su versión está relacionada directamente con la versión de gradle utilizada (tratada en el punto 3).


    **[/OPCIONAL]**
    - `id 'org.jetbrains.kotlin.android' version 'X.X.X' apply false`
        - https://kotlinlang.org/docs/releases.html#release-details

    La versión de kotlin que utilicemos debe estar soportada por el compilador de compose. Para saber cual es la adecuada, en la documentación hay un mapa de compatibilidad:
        https://developer.android.com/jetpack/androidx/releases/compose-kotlin

3. **[OPCIONAL]** Modificar en el archivo gradle-wrapper.properties:
    - `distributionUrl=https\://services.gradle.org/distributions/gradle-X.X-bin.zip`
        - https://docs.gradle.org/current/userguide/compatibility.html
        - https://gradle.org/releases/

    Es la versión de gradle que se utiliza en el proyecto, y que para determinar su versión tenemos que tener en cuenta la versión del plugin que se ha configurado anteriormente, y el JDK que estemos utilizando.

4. Sincronizar el proyecto
5. **[OPCIONAL]** Ejecutar el análisis de migración del código
