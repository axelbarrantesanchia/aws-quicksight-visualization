# Proyecto: Análisis de datos con Amazon QuickSight y archivos de Netflix

Este proyecto guía paso a paso cómo cargar archivos CSV desde S3 y analizarlos visualmente con Amazon QuickSight. Aprenderás a crear un bucket, configurar permisos, subir un archivo manifest, conectarlo con QuickSight, visualizar dashboards, y al final, **eliminar tu cuenta de QuickSight para evitar cargos**.

---

## Paso Setup: Descargar archivos necesarios

Descarga el archivo `proyecto_quicksight.rar`, descomprímelo y obtendrás dos archivos:  
- `netflix_titles.csv`  
- `manifest.json`

![Paso Setup](quicksight-pasos/pasosetup.png)

---

## Paso 1: Iniciar sesión en AWS y buscar S3

Ingresa a tu cuenta de AWS y en la barra superior escribe “S3” para buscar el servicio.

![Paso 1](quicksight-pasos/paso1.png)

---

## Paso 2: Crear un bucket

Haz clic en **Create bucket** y nómbralo `quicksight-project-tuNombre`.

![Paso 2](quicksight-pasos/paso2.png)

---

## Paso 3: Dejar configuraciones por defecto

Presiona **Create bucket** sin cambiar configuraciones por defecto.

![Paso 3](quicksight-pasos/paso3.png)

---

## Paso 4: Subir archivos descomprimidos

Dentro del bucket creado, haz clic en **Upload** y sube `netflix_titles.csv` y `manifest.json` (sin comprimir, por separado).

![Paso 4](quicksight-pasos/paso4.png)

---

## Paso 5: Verificar carga exitosa

Asegúrate de que ambos archivos estén cargados correctamente.

![Paso 5](quicksight-pasos/paso5.png)
![Paso 6](quicksight-pasos/paso6.png)

---

## Paso 6: Copiar URI de S3

Haz clic en `netflix_titles.csv` y copia su URI.

![Paso 7](quicksight-pasos/paso7.png)

---

## Paso 7: Editar manifest.json

Abre `manifest.json` con VS Code o un editor de texto.  
Reemplaza el campo `"Uri"` en `fileLocations` por el URI del paso anterior.

> **Explicación**:
> - `format`: `"CSV"`
> - `delimiter`: `","`
> - `textQualifier`: `"\""` → se usa para indicar si los campos están entre comillas dobles.
> - `containsHeader`: `true`

![Paso 7](quicksight-pasos/paso8.png)

---

## Paso 8: Subir manifest.json editado

Haz clic en **Upload** y vuelve a subir `manifest.json`.

![Paso 8](quicksight-pasos/paso9.png)

---

## Paso 9: Confirmar reemplazo

S3 reemplazará automáticamente el archivo anterior.

![Paso 9](quicksight-pasos/paso10.png)

---

## Paso 10: Ver mensaje de éxito

Verifica el mensaje "Upload succeeded".

![Paso 10](quicksight-pasos/paso11.png)

---

## Paso 11: Buscar QuickSight en la consola

En la barra de búsqueda escribe “Quicksight”.

![Paso 11](quicksight-pasos/paso12.png)

---

## Paso 12: Registrarse en QuickSight

Haz clic en **Sign up for QuickSight** (es gratis por 30 días).

![Paso 12](quicksight-pasos/paso12.png)

---

## Paso 13: Llenar Contact Information

Usa tu correo de AWS. Método de autenticación: déjalo por defecto.

![Paso 13](quicksight-pasos/paso13.png)

---

## Paso 14: Seleccionar región

Escoge la misma región que estás utilizando en tu consola de AWS.

![Paso 14](quicksight-pasos/paso14.png)

---

## Paso 15: Nombre y permisos

En `QuickSight account name`, coloca tu nombre + “-Quicksight”.  
Activa solo S3 y **selecciona el bucket creado**.

![Paso 15](quicksight-pasos/paso15.png)

---

## Paso 16: Desmarcar Add-on

Quita la selección de **AddPixelPerfect Reports** para evitar cargos.

![Paso 16](quicksight-pasos/paso16.png)

---

## Paso 17: Finalizar configuración

Presiona **Finish**.

![Paso 17](quicksight-pasos/paso17.png)

---

## Paso 18: Esperar creación de cuenta

Aparecerá "Creating your account...".

![Paso 18](quicksight-pasos/paso18.png)

---

## Paso 19: Ir a QuickSight

Una vez creada la cuenta, haz clic en **Go to QuickSight**.

![Paso 19](quicksight-pasos/paso19.png)

---

## Paso 20: Ir a Datasets

En el menú lateral, selecciona **Datasets**.

![Paso 20](quicksight-pasos/paso20.png)

---

## Paso 21: Crear nuevo Dataset

Haz clic en **Create new dataset**.

![Paso 21](quicksight-pasos/paso21.png)

---

## Paso 22: Elegir S3 como fuente

Escoge S3 entre las fuentes disponibles.

![Paso 22](quicksight-pasos/paso22.png)

---

## Paso 23: Nombrar fuente de datos

Data source name: `Kaggle-netflix-data`.

![Paso 23](quicksight-pasos/paso23.png)

---

## Paso 24: Usar URI del manifest.json

Copia y pega el URI de `manifest.json`.

![Paso 24](quicksight-pasos/paso24.png)

---

## Paso 25: Conectar

Haz clic en **Connect**.

![Paso 25](quicksight-pasos/paso25.png)

---

## Paso 26: Visualizar

Haz clic en **Visualize**.

![Paso 26](quicksight-pasos/paso26.png)

---

## Paso 27: Crear análisis

Aparecerá una nueva ventana, toca **Create**.

![Paso 27](quicksight-pasos/paso27.png)

---

## Paso 28: Explorar columnas

En la izquierda verás los campos del CSV como `cast`, `country`, `date_added`, etc.

![Paso 28](quicksight-pasos/paso28.png)

---

## Paso 29: Agregar visualización

Haz clic en **Add** en la sección Visuals.

![Paso 29](quicksight-pasos/paso29.png)

---

## Paso 30: Añadir campo `release_year`

Arrástralo al área de visualización.

![Paso 30](quicksight-pasos/paso30.png)

---

## Paso 31: Resultado

Verás una gráfica por año.

![Paso 31](quicksight-pasos/paso31.png)

---

## Paso 32: Añadir campo `type`

Arrástralo a la sección de **Group/Color**.

![Paso 32](quicksight-pasos/paso32.png)

---

## Paso 33: Explicación de QuickSight

Ahora puedes ver por tipo (`Movie` o `TV Show`) y por año.  
QuickSight es una herramienta de BI (Business Intelligence) de AWS que permite transformar datos crudos en dashboards interactivos para tomar decisiones basadas en datos.

![Paso 33](quicksight-pasos/paso33.png)

---

## Paso 34: Visualizaciones de ejemplo

Múltiples cuadros permiten analizar duración, directores, ratings, y top por país.

![Paso 34](quicksight-pasos/paso34.png)

---

## Paso 35: Agregar nueva visualización en forma de tabla

![Paso 35](quicksight-pasos/paso35.png)

---

## Paso 36: Usar campo `country` como valor

Verás muchos valores vacíos.

![Paso 36](quicksight-pasos/paso36.png)

---

## Paso 37: Notar datos incompletos

Para un mejor análisis se necesita información más completa.

![Paso 37](quicksight-pasos/paso37.png)

---

## Paso 38: Subir archivo actualizado

Sube `netflix_titles_updated.json` al bucket.

![Paso 38](quicksight-pasos/paso38.png)

---

## Paso 39: Verificar subida

![Paso 39](quicksight-pasos/paso39.png)

---

## Paso 40: Confirmar subida exitosa

![Paso 40](quicksight-pasos/paso40.png)

---

## Paso 41: Editar manifest.json

Cambia el URI al del nuevo archivo.

![Paso 41](quicksight-pasos/paso41.png)

---

## Paso 42: Refrescar navegador

Vuelve a la pestaña donde está QuickSight.

![Paso 42](quicksight-pasos/paso42.png)

---

## Paso 43: No se reflejan cambios aún

![Paso 43](quicksight-pasos/paso43.png)

---

## Paso 44: Ir a Datasets

Ve a Data > Datasets.

![Paso 44](quicksight-pasos/paso44.png)

---

## Paso 45: Editar dataset

Toca los tres puntos > Edit.

![Paso 45](quicksight-pasos/paso45.png)

---

## Paso 46: Ver nuevos datos reflejados

Ahora el campo `country` tiene mejor información.

![Paso 46](quicksight-pasos/paso46.png)

---

## Paso 47: Refrescar

Haz clic en **Refresh** abajo a la izquierda.

![Paso 47](quicksight-pasos/paso47.png)

---

## Paso 48: Marcar Full Refresh

Presiona **Refresh** otra vez.

![Paso 48](quicksight-pasos/paso48.png)

---

## Paso 49: Aceptar advertencia

Esto reemplaza los datos antiguos con los nuevos.

![Paso 49](quicksight-pasos/paso49.png)

---

## Paso 50: ¡Datos actualizados!

Listo, puedes ver los cambios.

![Paso 50](quicksight-pasos/paso50.png)

---

## Paso 51: Eliminar cuenta de QuickSight

Haz clic en el ícono de perfil.

![Paso 51](quicksight-pasos/paso51.png)

---

## Paso 52: Ir a Manage QuickSight

![Paso 52](quicksight-pasos/paso52.png)

---

## Paso 53: Ir a Account Settings

![Paso 53](quicksight-pasos/paso53.png)

---

## Paso 54: Desactivar protección y eliminar

En "Account termination", escribe `confirm` y elimina la cuenta.

![Paso 54](quicksight-pasos/paso54.png)

---

## Paso 55: Confirmación de eliminación

Verás el mensaje "Unsubscribe Successful".

![Paso 55](quicksight-pasos/paso55.png)

---

## Paso 56: Eliminar bucket S3

Ve a S3 y elimina el bucket para cerrar el proyecto.

![Paso 56](quicksight-pasos/paso56.png)

---

## Paso 57: ¡Proyecto terminado!

¡Gracias por completar este proyecto con QuickSight!

![Paso 57](quicksight-pasos/paso57.png)
