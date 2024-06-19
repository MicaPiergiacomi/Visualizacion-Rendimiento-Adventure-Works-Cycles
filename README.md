# Visualizando el Rendimiento Adventure Works Cycles

Adventure Works Cycles (AWC) es una empresa multinacional líder en la fabricación y distribución de bicicletas, piezas y accesorios. 

El presente informe tiene como objetivo proporcionar una visión integral y detallada del rendimiento de ventas de AWC mediante el uso de la plataforma Power BI. A través de análisis exhaustivos y visualizaciones interactivas, este informe permitirá a los usuarios finales comprender mejor los factores que influyen en las ventas, los costos asociados y la rentabilidad general de la empresa. Además, servirá como una herramienta invaluable para la toma de decisiones estratégicas, al proporcionar información clave y perspicaz para identificar áreas de mejora y oportunidades de crecimiento.

### Objetivos:

• **Mejora de la calidad de los datos**: A través de procesos de limpieza y validación de datos efectivos, se garantiza la fiabilidad y precisión de la información utilizada en el análisis.

• **Modelado de datos relacional**: Se desarrolla un modelo de datos robusto y relacional que refleja las complejas interacciones entre diferentes aspectos del negocio, permitiendo un análisis integrado y coherente.

• **Cálculo de métricas clave con DAX**: Se utilizan expresiones de análisis de datos (DAX) para calcular métricas clave relacionadas con las ventas, los costos y la rentabilidad, proporcionando una comprensión más profunda del rendimiento empresarial.

• **Diseño de informes informativos y visuales**: Se diseñan informes visuales atractivos y fáciles de entender, que destacan los KPIs más relevantes y facilitan la identificación de tendencias y patrones significativos.


## Desarrollo del proyecto

### Avance 1:

-	Se restauró en SQL la base ‘AdventureWorksDW2019’, se descargó la fuente de datos “DimCustomer”.
-	
-	En Power BI se conectó de la base restaurada las tablas: ‘DimProduct’, ‘DimProductcategory’. ‘DimProductSubcategory’, ‘DimDate’, ‘DimPromotion’, ‘DimSalesTerritory’, ‘DimGeography’ y ‘FactInternetSales’. Se conectó también la tabla ‘DimCustomer’.
-	
-	Se verificó que los encabezados de todas las tablas estén bien.
-	
-	Acciones: Eliminación de filas en blanco; Eliminación de columnas vacías (‘Columna 18’, ‘Columna 31’, Columna ‘Surfix’, SpanishOccupation’, ‘FrenchOccupation’, SpanishEducation’, ‘FrenchEducation’); unificación de columnas ‘CountryRegionCode’ en una sola; eliminación de columna ‘Title’ porque tiene menos de 1% de válidos.

Combinación de tablas.

-	Se combinó la tabla ‘DimCustomer’ con la tabla ‘DimGeography’ para expandir las columnas ‘City’ y ‘StateProvincename’.
-	
-	Se combinó en la tabla ‘DimProduct’ las tablas ‘ProductCategory’ y ‘ProductSubcategory’. Primero, en la tabla ‘DimProduct’ desde Combinar Consultas se unificó desde la columna ‘ProductSubcategoryKey’ a la tabla ‘DimSubcategory’ y luego se expandió la tabla trayendo las columnas ‘EnglishProductSubcategoryName’ y ‘ProductCategoryKey’. En segundo lugar, desde Combinar Consultas se unificó desde la columna traída recientemente ‘ProductCategoryKey’ la tabla ‘DimCategory’ y se extendió la tabla trayendo la columna ‘EnglishProductcategoryName’.
-	
-	Se reemplazo los valores ‘null’ de las columnas ‘EnglishProductCategotyName’ y ‘EnglishProductSubcategoryName’ por ‘Without Category’ y ‘Without Subcategory’.


### Avance 2: 

-En este segundo avance del proyecto, se centró en el diseño tanto del modelo relacional eficiente en Power BI como en la creación de un mockup del informe que guiará el producto final. Para abordar el problema de negocio planteado, se buscó desarrollar un reporte que ofreciera una visión clara y detallada de los ingresos, costos, rentabilidad y otros indicadores clave a nivel de la compañía, con un enfoque especial en el mercado de Estados Unidos.

-El reporte diseñado debe responder a una serie de preguntas clave, incluyendo el total de ingresos del período actual y anterior, cantidad vendida, utilidad bruta y neta, costo de los bienes vendidos, distribución geográfica de clientes, distribución mensual de ingresos, COGS y utilidad, utilidad por segmento y subcategoría de producto, entre otros.

-Creación de MockUp, un diseño preliminar del informe interactivo.



### Avance 3: 

- Se creó una nueva tabla para Calendario desde la primera fecha de orden.
- 
- En Power Query: se agregó una columna personalizada con el nombre del mes en formato corto (primeras 3 letras de nombre del mes).


### Avance 4: 

- Se creó el reporte final en Power BI, centrado en los ingresos, costos y rentabilidad, tanto a nivel global como en el mercado de Estados Unidos.
  
- Con la herramienta Figma realicé los fondos de lienzo con las medidas personalizadas Alto: 1080, Ancho: 1920.
  
- Utilice las visualizaciones del mockup como guía para crear las visualizaciones en Power BI.
  
- Luego generé Parámetros de Campo desde la pestaña "Modelo" y creé un nuevo parámetro de campos llamado "Indicadores". Agregue las medidas requeridas (Ingresos, Utilidad Neta, Utilidad Bruta, COGS, "% Margen Neto, "% Margen Bruta, Costo de Envío"). Luego lo agregué como un segmentador visual y lo usé para filtrar la información en los mapas que muestran los clientes por país.
  
- Se creó un grupo de cálculo llamado "Variacion_Tiempo" que agrupe las medidas relacionadas con el período actual, el período anterior, la variación y la variación porcentual. 

