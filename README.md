# Análisis de la dinámica salarial ante variaciones en el PIB, la productividad y la tasa de desempleo (2008-2023)

Este repositorio contiene el código, los datos y el análisis econométrico realizado para el estudio de los salarios en España, desarrollado en el marco del 
**Grado en Estadística Aplicada** de la Universidad Complutense de Madrid, utilizando datos oficiales de la **Contabilidad Nacional Trimestral (INE)** y estadísticas del 
**Ministerio de Trabajo**. 

## 📊 Resumen del Proyecto
El objetivo principal es entender cómo reaccionan los salarios ante la marcha de la economía y la situación de las empresas en España.El horizonte temporal abarca desde el primer trimestre de 2008 hasta el cuarto de 2023, capturando ciclos económicos críticos como la crisis financiera, la recuperación post-2014 y el shock del COVID-19.

### Hallazgos Principales:
* **Desacoplamiento:** Se detectó que los aumentos de productividad no se traducen necesariamente en subidas salariales, contradiciendo la teoría neoclásica.
* **Fuerza del SMI:** El Salario Mínimo Interprofesional aparece como la variable con mayor poder explicativo a corto plazo en el mercado español.
* **Relación de Cointegración:** Mediante el Test de Johansen, se confirmó que el Salario, el PIB, el Paro y el SMI mantienen una relación estable de equilibrio a largo plazo.


## 🔬 Modelos Evaluados y Problemas Detectados
Durante la investigación se descartaron varias especificaciones por problemas de significatividad o inconsistencia técnica[cite: 180, 192]:

| Modelo | Principales Problemas |
| :--- | :--- |
| PIB + Paro + Productividad | No significativos tras integrar las variables. |
| PIB + Paro + EBE | Inconsistencia por mezcla de órdenes de integración. |
| PIB + Paro + EBE + Salario + Impuestos | Falta de significatividad persistente. |

**Especificación Final:** Se optó por un modelo de cointegración para el largo plazo y un enfoque **ARIMA (1,0,0)(0,1,1)₄** para capturar la fuerte estacionalidad trimestral detectada.

## 🛠️ Requisitos
Para ejecutar los scripts, es necesario tener instalado R y los siguientes paquetes:
```r
install.packages(c("tidyverse", "tseries", "urca", "forecast", "lmtest"))
````

## 👥 Autores
* Carla Padrón Rodríguez
* Raquel Manglanos García
* Daniel Almazán Peña
