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


5. Eliminar Columnas irrelevantes:
   - Columna OBSERVACIONES, ya que contiene comentarios muy variados entre sí sin algún patrón alguno o relevancia para el estudio
   - Columna ESTADO, pues todos los sujetos comparten el mismo estado 'ACTIVO'
   - Coluna TIPO INSTITUCIÓN , pues todas las filas comparten describen el mismo tipo 'S_I'
6. Reemplazar 'manualmente' todos los caracteres no reconocidos por los respectivos en cada una de las columnas alusivas (ya que con scripts se perdían datos), debido a que el dataset venía con caracteres corruptos originalmente:
   - Columnas afectadas:
     - DEPARTAMENTO DE RESIDENCIA
     - CIUDAD DE RESIDENCIA
     - NOMBRE IE
     - PROGRAMA ACADEMICO
       
   - Palabras afactadas:
   		
	   - PE�OL > PEÑOL
	   - PE�ON > PEÑON
	   - PI�ON > PIÑON
	   - MONTA�ITA > MONTAÑITA
	   - PE�A > PEÑA
	   - MO�ITOS > MOÑITOS
	   - PIJI�O > PIJIÑO
	   - NARI�O > NARIÑO
	   - TUCH�N > TUCHÍN
	   - OCA�A > OCAÑA
	   - CARRE�O > CARREÑO
	   - SALDA�A > SALDAÑA
	   - DISE�O > DISEÑO
	   - SE�ORA > SEÑORA
	   - NU�EZ > NUÑEZ
	   - BRICE�O > BRICEÑO
	   - ENESE�ANZA > ENSEÑANZA
	   - CAMPA�A > CAMPAÑA
	   - PE�ALISA > PEÑALISA
	   - LE�A > LEÑA
	   - MA�ANA > MAÑANA
	   - CA�ASGORDAS > CAÑASGORDAS
	   - CA�O > CAÑO
	   - CONVE�AS > COVEÑAS
	   - CAMPI�A > CAMPIÑA
	   - YA�EZ > YAÑEZ
	   - MALA�A > MALAÑA
	   - ESPA�OL � ESPAÑOL
	   - NI�O > NIÑO
     
   
    
5. Detectar tipo de Datos para todas las columnas
6. Reordenar las columnas para mayor legibildiad al analizar la tabla
7. Añadir un índice para cada registro en favor de la ausencia de identificadores.
