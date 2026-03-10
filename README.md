# Challenge Telecom X: Predicción de Evasión

Este proyecto desarrolla un sistema de análisis predictivo para **Telecom X**, con el objetivo de identificar a los clientes con alta probabilidad de cancelar su servicio. A través de técnicas de Machine Learning, para buscar transformar datos históricos en estrategias de retención de clientes.

## Propósito del Proyecto
El objetivo principal es construir y evaluar modelos de clasificación que predigan la fuga de clientes basándose en variables demográficas, servicios contratados y métricas financieras. Se prioriza la detección temprana para reducir la pérdida de ingresos y optimizar el valor de vida del cliente.

## Estructura del Proyecto
challenge-telecomX-prediction  
│  
├── TelecomX_LATAM_2.ipynb   
├── TelecomX_Data_Procesado.csv  
└── README.md                

## Preparación de los datos
Para garantizar un entrenamiento efectivo, se siguieron estas etapas:
1.  **Clasificación de variables:**
    * **Numéricas:** Meses activo, Cargo mensual y Cargo total.
    * **Categóricas:** Tipo de contrato, Método de pago, Servicio de internet, Género, Adulto mayor, Tiene pareja, Dependientes, Lineas múltiples, Seguridad online, Respaldo online, Protección dispositivo, Soporte técnico, Televisión por cable, Streaming películas, Tipo contrato, Factura digital, Forma de pago. 
2.  **Codificación y Normalización:**
    * Se aplicó *One-Hot Encoding* a las variables categóricas para transformarlas en un formato legible por los modelos.
    * Se utilizó *StandardScaler* para normalizar las variables numéricas, un paso crítico para el modelo KNN, asegurando que todas las variables contribuyan equitativamente a la métrica de distancia.
3.  **División de datos:** El dataset se dividió en conjuntos de **entrenamiento (80%) y prueba (20%)**, asegurando que los modelos se evaluaran con datos no vistos previamente.


## Justificación de la modelización
Se evaluaron dos arquitecturas con fundamentos distintos:
* **Random Forest (RF):** Elegido como el modelo principal debido a su capacidad para manejar interacciones no lineales y su robustez frente al sobreajuste nos permitieron alcanzar un ***Recall de 74*.6%**, maximizando la detección de clientes en riesgo de cancelar.
* **K-Nearest Neighbors (KNN):** Utilizado para identificar grupos de clientes con comportamientos similares. Su enfoque geométrico proporcionó una alta precisión, validando los clústeres de usuarios propensos a la fuga.

**Priorización del Recall:** En Telecom X, es más costoso perder a un cliente real que realizar una acción de retención sobre una falsa alarma. Por ello, preferimos capturar a la mayoría de los desertores.

---

## Insights del análisis exploratorio (EDA)
Durante el análisis visual se obtuvieron hallazgos clave:

* **Barrera de los 12 meses:** Los clientes con menos de un año de antigüedad tienen la mayor tasa de cancelación.
* **Costo mensual:** Existe una correlación positiva entre cargos mensuales altos (>$70 USD) y la intención de salida.
* **Contratos:** El contrato "Mes a Mes" es el principal predictor de fuga, mientras que los contratos de dos años aseguran la lealtad.


## Estrategias de Retención Propuestas
1.  **Migración de contratos:** Incentivar el paso de planes mensuales a anuales.
2.  **Monitoreo de fibra óptica:** Revisar la calidad del servicio en este segmento, ya que presenta alta cancelación pese a ser tecnología de alta gam.
3.  **Digitalización de Ppgos:** Promover el cambio de cheque electrónico a domiciliación bancaria para reducir la fricción.

---

## Instrucciones para ejecutar el cuaderno

1. Clonar o descargar el repositorio

  * git clone <url_del_repositorio>

3. Abrir el notebook en Google Colab.

4. Cargar la base de datos
   
  * Asegurarse de que el archivo CSV esté dentro de la misma carpeta que el cuaderno.

5. Instalar librerías necesarias (si no las tienes instaladas)
   
* pandas

* numpy

* matplotlib

* seaborn

* scikit-learn

6. Ejecutar todas las celdas del cuaderno o ejecutar el cuaderno celda por celda para seguir el flujo de preprocesamiento, modelado y análisis de resultados.

## Autor

Nombre: Miguel Venegas Rocha

* Proyecto desarrollado como parte del desafío de análisis y predicción de cancelación de clientes de Telecom X de Alura.
