# MiguelAPaezG_UCundi_ArqDat_PrimerETL

1. Eliminar las columans vacías:
	- PROGRAMA
	- ID BENEFICIO
	- CC TI BENEFICIARIO
	- NOMBRES
	- APELLIDOS
	- EMAIL

2. Eliminar las filas vacías:
	- 7% de filas vacías en la columna OBERVACIONES
 	- <1% de filas vaícas en la Columna META

3. Eliminar filas con error:
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
    
7. Detectar tipo de Datos para todas las columnas
8. Reordenar las columnas para mayor legibildiad al analizar la tabla
9. Añadir un índice para cada registro en favor de la ausencia de identificadores.
10. Añadier dos columnas "MES DE CONVENIO" y "MES DE VIGENCIA", debido a que el tiempo entre ambos es de 1 año, añadir los meses como datos derivados de la fecha, permitirá un analizar más preciso temporalmente.
11. Normlizar los nombres de las columnas todos en letras capitales y sin guiones bajos.
12.  Cambiar el tipo de dato del "MONTO COMPROMETIDO" de 'decimal' a 'entero' puesto que los centavos son irrelevantes para el objeto de estudio
13.  Añadir la columna calculada MONTO PER CAPITA que relaciona propocionalmente la cantidad del monto que le correspondería cada persona según la META del convenio asocidado al MONTO COMPROMETIDO
14.  Añadir las columnas calculadas globales de tipo Z SCORE (que permite conocer qué tanto se desvía la el dato en base al promedio global) respecto al MONTO COMPROMETIDO y MONTO PER CAPITA
15.  Añadir las columnas calculadas globales de tipo ranking  RANKING DE MONTO COMPROMETIDO y  RANKING DE MONTO PER CAPITA con Skip (cuál teniendo en cuenta valores empatados, calcula la posición real de siguiente valor único en base a cuántos empates anteriores se hallaron)
