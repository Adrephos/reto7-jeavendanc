# ST0256 Tópicos Especiales en Telemática

## Estudiante:
- Nombre: Juan Esteban Avendaño Castaño
- Correo: jeavendanc@eafit.edu.co

## Profesor:
- Nombre: Álvaro Ospina
- Correo: aeospinas@eafit.edu.co

# Reto 7 - Spark

## Spark en Colab
### Configuración
Primero instalamos las librerías necesarias para trabajar con Spark
y montamos el Google Drive:
![Instalar librerías](./images/mount_drive_install_dependencies.png)

Creamos la SparkSession y el SparkContext para trabajar con Spark:
![](./images/session_context_set_up.png)

Verificamos que la SparkSession y el SparkContext se hayan creado correctamente:
![](./images/session_context_verify.png)

Subimos la carpeta `datasets` a nuestro Google Drive:
![Subir datasets](./images/drive_upload.png)

Cargamos el dataset `sample_data.csv` a Spark:
![](./images/load_dataset.png)

Podemos verificamos que el dataset se haya cargado correctamente:
![](./images/df_characteristics.png)

### Consultas
Mostar las primeras 5 filas del dataset:
![](./images/show_rows.png)

Podemos seleccionar solo las columnas `age` y `mobile` del dataset:
![](./images/limit_columns.png)

Podemos hacer `describe` al dataset para ver las estadísticas de las columnas:
![](./images/describe_dataset.png)

También se pueden usar tipos de datos de SQL para hacer consultas, se importan de la siguiente forma:
![](./images/import_sql_types.png)

Se pueden usar por ejemplo para crear columnas con este tipo de datos y haciendo `cast` a las columnas del dataframe:
![](./images/sql_type_use.png)

Al crear columnas podemos operar con los datos de las columnas del dataframe, por ejemplo sumando 10 a la columna `age` para crear una nueva columna `age_after_10_yrs`:
![](./images/operate_column.png)

Se pueden tambien hacer filtros en el dataframe, deacuerdo a una condición, por ejemplo:
![](./images/filters.png)

Otra consulta util es el `distinct` para ver los valores únicos de una columna, también se puede hacer `count` para contar los valores únicos:  
![](./images/distinct_count.png)

Se pueden hacer `groupBy` para agrupar los datos de una columna y hacer operaciones sobre ellos, por ejemplo contar cuantos celulares hay de cada marca:
![](./images/group_by_1.png)

Con `groupBy` también se pueden hacer operaciones más complejas, por ejemplo sumar o sacar  un promedio a los valores de cada columna agrupados por la columna `mobile`:
![](./images/group_by_2.png)

Con `groupBy`, `max` y `min` se pueden sacar los valores máximos y mínimos de una columna:
![](./images/group_by_3.png)

Usando `agg` y `groupBy` se pueden hacer operaciones más complejas, por ejemplo sumar los valores de la columna `experience` agrupados por la columna `mobile`:
![](./images/group_by_4.png)

Otra de las cosas que podemos hacer con Spark, es hacer uso de funciones ya sean las funciones típicas de python o funciones lambda:
![](./images/functions_and_lambda.png)

Otro tipo de funciones que puede resultar utiles son las `User Defined Functions` de pandas que sirven para aplicar funciones a los datos de una columna:
![](./images/functions_udf.png)

Para terminar podemos hacer `drop` de columnas que no necesitemos en el dataframe, como por ejemplo duplicados:
![](./images/drop.png)

### Subir datos a S3
Primero instalamos las librerías necesarias para trabajar con S3:
![](./images/s3_libraries.png)

Configuramos las credenciales de AWS:
![](./images/aws_credentials.png)

Subimos el archivo `df.csv` a S3:
![](./images/csv_upload.png)

Subimos el archivo `df.parquet` a S3:
![](./images/parquet_upload.png)

Para terminar podemos ver los archivos subidos a S3:
![](./images/files_in_s3.png)


## Spark en EMR con Jupyter
Primero ingresamos a Jupyter en EMR y creamos un nuevo notebook:
![](./images/jupyter_login.png)

### Configuración
Primero importamos las librerías necesarias para trabajar con Spark, creamos la SparkSession, el SparkContext y leer el archivo `sample_data.csv` de S3:
![](./images/jupyter_setup.png)

Verificamos que se haya cargado correctamente el archivo y que el dataframe se haya creado:
![](./images/verify_jupyter.png)


### Consultas
Iguales a las realizadas en Colab.

### Subir datos a S3
Para subir los datos a S3 en formato `csv` se hace de la siguiente forma:
![](./images/csv_jupyter.png)

Para subir los datos a S3 en formato `parquet` se hace de la siguiente forma:
![](./images/parquet_jupyter.png)

Para terminar podemos ver los archivos subidos a S3:
![](./images/s3_jupyter.png)
Archivo `csv`:
![](./images/s3_jupyter_csv.png)
Archivo `parquet`:
![](./images/s3_jupyter_parquet.png)

## Conclusiones
- Spark es una herramienta muy poderosa para trabajar con grandes volúmenes de datos.
- Se pueden hacer consultas de forma muy similar a SQL.
- Se pueden hacer operaciones sobre los datos de forma muy sencilla.
