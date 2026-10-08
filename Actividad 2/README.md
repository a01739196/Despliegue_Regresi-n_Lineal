# Dashboard GAC Motor · Etapa I y Etapa II

Dashboard en **Streamlit** con los datos de GAC Motor (agencia Angelópolis), construido en Visual Studio Code.

## Contenido del repositorio

| Archivo | Qué es |
|---|---|
| `Dashboard_GAC_v6.ipynb` | Notebook principal: análisis de la Etapa II (correlaciones, regresión lineal simple y múltiple) y celda que genera `app.py` |
| `app.py` | Código del dashboard (Etapa I + Etapa II) |
| `*_Limpio.csv` | Bases limpias de la Etapa I |
| `Funnel_Ventas_Mensual.csv`, `MKT_Digital_Mensual.csv`, `Ventas_por_Asesor_Mensual.csv` | Bases mensuales nuevas de la Etapa II |
| `logo_gac.png`, `auto fondo.jpeg`, `disco_freno.png`, `fibra_carbono.png`, `brillo_dona.png` | Imágenes del diseño |

## Etapa I · Extracción de características
Análisis univariado de 15 variables (6 categóricas y 9 numéricas discretas):
- **Hallazgos principales:** las 5 respuestas más importantes.
- **Análisis univariado:** dos gráficas por variable (barras, lollipop, treemap, dona, histograma, boxplot, violín, velocímetro, línea).
- **Comparación por periodo:** cambio por año o por mes y mapa de calor.

## Etapa II · Modelado predictivo
- **Resumen de modelos:** mejor regresión simple y regresión múltiple de **todas las bases** en una sola vista.
- **a) Análisis de correlaciones:** mapa de calor y ranking de correlación con la variable a predecir.
- **Regresión lineal simple:** dispersión real + recta de regresión + **dispersión de los datos predichos superpuesta**, ecuación, r, R², p-valor, ranking de todas las X y simulador.
- **Regresión lineal múltiple:** real vs predicho, **dispersión real y predicha superpuesta** contra cada X, tabla de coeficientes (p-valor y VIF), comparación simple vs múltiple y simulador.
- En ambas regresiones: KPIs en fila arriba, la gráfica y debajo los selectores de Y y X; y al final va la **ecuación estimada** con la interpretación de cada coeficiente.

Resultado principal (base mensual combinada, Y = Ventas): Citas efectivas sola explica R² = 0.62; el modelo múltiple con Leads, Citas efectivas, Pruebas de manejo y Solicitudes aprobadas explica **R² = 0.90** (R² ajustado = 0.88).

## Widgets extra (bonus)
Radio de etapa, selectores de vista/base/canal/variable, filtros de año y mes, multiselect de X, pestañas, heatmaps, boxplots, tablas con barras de progreso, tarjetas de indicadores, simuladores de predicción, paleta de color GAC e íconos (logo, disco de freno, fibra de carbono).

## Cómo correrlo
```bash
pip install streamlit plotly pandas scipy matplotlib
python -m streamlit run app.py
```
Todos los archivos deben estar en la misma carpeta que `app.py`.
