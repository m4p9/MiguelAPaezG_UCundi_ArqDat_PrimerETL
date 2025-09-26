# MiguelAPaezG_UCundi_ArqDat_PrimerETL

1. Eliminar las columans vacías:
	- PROGRAMA
	- ID BENEFICIO
	- CC TI BENEFICIARIO
	- NOMBRES
	- APELLIDOS
	- EMAIL

3. Eliminar las filas vacías:
	- 7% de filas vacías en la columna OBERVACIONES

4. Eliminar filas con error:
	- <1% de filas con errores en la columna CONVOCATORIA

5. Detectar tipo de Datos para todas las columnas
6. Eliminar Columnas irrelevantes:
   - Columna OBSERVACIONES, ya que contiene comentarios muy variados entre sí sin algún patrón alguno o relevancia para el estudio
   - Columna ESTADO, pues todos los sujetos comparten el mismo estado 'ACTIVO'
	- Coluna TIPO INSTITUCIÓN , pues todas las filas comparten describen el mismo tipo 'S_I'
    
