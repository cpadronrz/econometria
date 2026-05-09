# Análisis de la dinámica salarial ante variaciones en el PIB, la productividad y la tasa de desempleo (2008-2023)

Este repositorio contiene el código, los datos y el análisis econométrico realizado para el estudio de los salarios en España, desarrollado en el marco del 
**Grado en Estadística Aplicada** de la Universidad Complutense de Madrid.

## 👥 Autores
* Carla Padrón Rodríguez
* Raquel Manglanos García
* Daniel Almazán Peña

## 📊 Resumen del Proyecto
[cite_start]El objetivo principal es entender cómo reaccionan los salarios ante la marcha de la economía y la situación de las empresas en España[cite: 14, 24]. [cite_start]El horizonte temporal abarca desde el primer trimestre de 2008 hasta el cuarto de 2023, capturando ciclos económicos críticos como la crisis financiera, la recuperación post-2014 y el shock del COVID-19[cite: 42, 43].

### Hallazgos Principales:
* [cite_start]**Desacoplamiento:** Se detectó que los aumentos de productividad no se traducen necesariamente en subidas salariales, contradiciendo la teoría neoclásica[cite: 311, 312].
* [cite_start]**Fuerza del SMI:** El Salario Mínimo Interprofesional aparece como la variable con mayor poder explicativo a corto plazo en el mercado español[cite: 205, 308].
* [cite_start]**Relación de Cointegración:** Mediante el Test de Johansen, se confirmó que el Salario, el PIB, el Paro y el SMI mantienen una relación estable de equilibrio a largo plazo[cite: 238, 239].

## 💻 Contenido del Repositorio
El análisis se divide en tres scripts fundamentales desarrollados en **R**:

1.  [cite_start]**`creacion_base.Rmd`**: Limpieza de datos del INE y Ministerio de Trabajo, alineación temporal y tratamiento de valores atípicos[cite: 60, 61].
2.  [cite_start]**`Analisis_econometrico_inicial.Rmd`**: Pruebas de raíces unitarias (Test ADF) y Test de Causalidad de Granger[cite: 164, 212].
3.  [cite_start]**`creacion_modelo.Rmd`**: Estimación del modelo final de cointegración y el modelo ARIMA para el corto plazo[cite: 233, 271].

## 🔬 Modelos Evaluados y Problemas Detectados
[cite_start]Durante la investigación se descartaron varias especificaciones por problemas de significatividad o inconsistencia técnica[cite: 180, 192]:

| Modelo | [cite_start]Principales Problemas [cite: 362] |
| :--- | :--- |
| PIB + Paro + Productividad | No significativos tras integrar las variables. |
| PIB + Paro + EBE | Inconsistencia por mezcla de órdenes de integración. |
| PIB + Paro + EBE + Salario + Impuestos | Falta de significatividad persistente. |

[cite_start]**Especificación Final:** Se optó por un modelo de cointegración para el largo plazo y un enfoque **ARIMA (1,0,0)(0,1,1)₄** para capturar la fuerte estacionalidad trimestral detectada[cite: 206, 289].

## 🛠️ Requisitos
Para ejecutar los scripts, es necesario tener instalado R y los siguientes paquetes:
```r
install.packages(c("tidyverse", "tseries", "urca", "forecast", "lmtest"))
