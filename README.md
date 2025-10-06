# MiguelAPaezG_UCundi_ArqDat_PrimerETL

### Miguel Ángel Páez García<br>

Programa de Ingeniería de Software, Facultad de Ingeniería<br>
Universidad de Cundinamarca - Extensión Soacha<br>
Grupo INFSOFT702, Arquitectura de Datos CAD652022720<br>
Jorge Armando Jurado Peralta<br>
Septiembre de 2025<br>


----

# 💻 Análisis del Perfil Poblacional respecto a otras Variables en el Programa Talento TI (2012–2017)

## 🧭 Introducción

Este proyecto forma parte de un proceso **ETL (Extracción, Transformación y Carga)** orientado al análisis del **perfil social, demográfico y económico** de los beneficiarios del programa **Talento TI (2012–2017)**, con base en los datos de inversión y convenios asociados.

A partir del **monto comprometido por convenio**, se busca comprender la relación entre el **presupuesto asignado**, las **características sociales de la población beneficiaria** y la **distribución institucional y geográfica** de los recursos.

---

## 📊 Resumen del Proyecto

El modelo fue construido y analizado en **Power BI**, integrando pasos de:
- Limpieza y normalización de datos.
- Estandarización de variables geográficas, académicas y demográficas.
- Cálculo de indicadores derivados mediante **DAX**, incluyendo:
  - **Presupuesto per cápita**
  - **Z-Score del monto comprometido**
  - **Ranking institucional y por programa**
  - **Segmentación socioeconómica por estrato y género**

### 🔍 Principales hallazgos

- **Distribución por género:** el 69,22% de los recursos fue destinado a hombres y el 30,78% a mujeres, revelando una brecha de participación significativa.  
- **Distribución por estrato:** los estratos **2, 3 y 1** concentraron el **86% del monto total**, evidenciando una orientación hacia sectores de menores ingresos.  
- **Distribución geográfica:** la mayor inversión se concentró en **Bogotá**, seguida por departamentos como **Risaralda, Caldas y Santander**.  
- **Instituciones con mayor asignación:** destacan el **Punto Vive Digital Sur Britalia**, la **Universidad de los Andes** y la **Pontificia Universidad Javeriana**, con los **Z-Score** más altos del estudio.  
- **Programas académicos predominantes:** Ingeniería de Sistemas y afines concentraron la mayoría de los recursos, seguidos por programas técnicos y tecnológicos en áreas informáticas.  

---

## 🧮 Conclusiones

El análisis permitió evidenciar **una correlación entre el nivel socioeconómico y la concentración presupuestal**, sugiriendo que, aunque el programa priorizó estratos bajos, las instituciones con mayor capacidad académica y tecnológica concentraron las inversiones más altas.

El uso del **Z-Score y del presupuesto per cápita** permitió medir de forma objetiva la **intensidad de inversión** por beneficiario e institución, proporcionando una visión más equilibrada sobre la **eficiencia y equidad del programa**.

---

## ⚙️ Tecnologías Utilizadas

- **Power BI Desktop**
- **Power Query (ETL)**
- **DAX (cálculos estadísticos y normalización)**
- **Excel / CSV (fuente de datos base)**

---

## 🗂️ Estructura del Proyecto
--
📁 TalentoTI_ETL_Analisis
┣ 📄 README.md ← Descripción general y documentación del proyecto
┣ 📊 MiguelAPaezG_UCundi_ArqDat_PrimerETL1.pbix ← Archivo principal de Power BI con el modelo, cálculos DAX y visualizaciones
┣ 📈 MiguelAPaezG_UCundi_ArqDat_PrimerETL1_Informe.pdf ← Informe final del análisis con visualizaciones y conclusiones
┣ 📄 Talento_TI_20250919.csv ← Dataset original sin procesar
┣ 📄 Talento_TI_20250919_CSVUTF8_ETL.csv ← Dataset limpio exportado en formato CSV UTF-8 (tras el proceso ETL)
┗ 📄 Talento_TI_20250919_CSVUTF8_ETL.xlsx ← Dataset limpio en formato Excel UTF-8 (versión tabular para compatibilidad)


> 📘 Nota:  
> Los archivos con sufijo **_ETL** representan los resultados del proceso de limpieza, normalización y transformación de datos.  
> El archivo **.pbix** contiene el modelo Power BI con las columnas calculadas, medidas DAX, visualizaciones y reportes interactivos.  
> El **informe PDF** resume los principales hallazgos y visualizaciones del tablero final.

---
##  ✅ PASOS APLICADOS DURANTE EL ETL


1. **Eliminar** las **columans** vacías:
	- PROGRAMA
	- ID BENEFICIO
	- CC TI BENEFICIARIO
	- NOMBRES
	- APELLIDOS
	- EMAIL

2. **Eliminar** las **filas** vacías:
	- 7% de filas vacías en la columna OBERVACIONES
 	- <1% de filas vaícas en la Columna META

3. **Eliminar** filas con **error**:
   - <1% de filas con errores en la columna CONVOCATORIA
   

5. **Eliminar** Columnas **irrelevantes**:
   - Columna OBSERVACIONES, ya que contiene comentarios muy variados entre sí sin algún patrón alguno o relevancia para el estudio
   - Columna ESTADO, pues todos los sujetos comparten el mismo estado 'ACTIVO'
   - Coluna TIPO INSTITUCIÓN , pues todas las filas comparten describen el mismo tipo 'S_I'
     
6. **Reemplazar** 'manualmente' todos los **caracteres no reconocidos** por los respectivos en cada una de las columnas alusivas (ya que con scripts se perdían datos), debido a que el dataset venía con caracteres corruptos originalmente:
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
    
7. **Detectar tipo de Datos** para todas las columnas+
8. **Reordenar** las columnas para mayor legibildiad al analizar la tabla
9. **Añadir** un **índice** para cada registro en favor de la ausencia de identificadores.
10. **Añadir** dos columnas **"MES DE CONVENIO" y "MES DE VIGENCIA"**, debido a que el tiempo entre ambos es de 1 año, añadir los meses como datos derivados de la fecha, permitirá un analizar más preciso temporalmente.
11. **Normalizar** los **nombres** de las **columnas** todos en letras capitales y sin guiones bajos.
12.  **Cambiar** el **tipo** de dato del **"MONTO COMPROMETIDO"** de 'decimal' **a 'entero'** puesto que los centavos son irrelevantes para el objeto de estudio
13.  **Añadir** la columna calculada **MONTO PER CAPITA** que relaciona propocionalmente la cantidad del monto que le correspondería cada persona según la META del convenio asocidado al MONTO COMPROMETIDO
14.  **Añadir** las columnas calculadas globales de tipo **Z SCORE** (que permite conocer qué tanto se desvía la el dato en base al promedio global) respecto al MONTO COMPROMETIDO y MONTO PER CAPITA
15.  **Añadir** las columnas calculadas globales de tipo **ranking**  RANKING DE **MONTO** COMPROMETIDO y  RANKING DE MONTO **PER CAPITA** con Skip (cuál teniendo en cuenta valores empatados, calcula la posición real de siguiente valor único en base a cuántos empates anteriores se hallaron)
16. **Cambiar** el **tipo** de dato del **"ESTRATO" a 'Texto'** para poder medirlo como categoría en vez de cifra.
17. **Cambiar** el **tipo** de dato del "**INDICE" a 'Texto'** ya que e sun identificador no una cifra que se operara.
18. **Crear Informes** Visuales:
    - Vista General de la **Inversión** del Programa Talento TI (2012 a 2017)
    - Vista General de la **Inversión por Género** en el Tiempo del Programa Talento TI (2012 a 2017)
    - Vista General de la **Inversión por Estrato** en el Tiempo del Programa Talento TI (2012 a 2017)
    - Vista General de la **Inversión por Institución** del Programa Talento TI (2012 a 2017)
    - Vista General de la **Inversión por Nivel** del Porgrama Académico del Programa Talento TI (2012 a 2017)
    - Vista General de la **Inversión por Porgrama** Académico del Programa Talento TI (2012 a 2017)
    - Vista General del **Z Score por Institución** Educativa del Programa Talento TI (2012 a 2017)
    - Vista General del **Z Score por Programa** Académico del Programa Talento TI (2012 a 2017)
19. **Exportar** los **informes** a PDF
20. **Exportar** el **dataset transformado** ediante el ETL realizado
    
