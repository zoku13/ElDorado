# 📊 Modelos de predicción de generación eólica

Este repositorio contiene el código completo utilizado para entrenar y evaluar seis modelos de predicción de generación eólica horaria en el Parque El Dorado. Los modelos combinan dos algoritmos (Random Forest y LightGBM) con tres horizontes de anticipación (1, 2 y 3 días). Cada notebook ya está preparado para ejecutarse directamente sin necesidad de modificar rutas ni parámetros internos.

## 📁 Archivos incluidos

- `Entrega4_v3_v3_day1lghbm.ipynb`
- `Entrega4_v3_v3_day1rforest.ipynb`
- `Entrega4_v3_v3_day2lghbm.ipynb`
- `Entrega4_v3_v3_day2rforest.ipynb`
- `Entrega4_v3_v3_day3lghbm.ipynb`
- `Entrega4_v3_v3_day3rforest.ipynb`
- `merged_energy_forecast_previous_day.csv`: dataset con variables meteorológicas y energía generada (`ene_gen_mwh`)
- `requerimientos_software.txt`: archivo con las versiones exactas de Python y librerías utilizadas

## 🚀 Cómo ejecutar los notebooks

1. Abrí el notebook del modelo que quieras probar (por ejemplo, `Entrega4_v3_v3_day2lghbm.ipynb`) en **Google Colab**.
2. Subí el archivo `merged_energy_forecast_previous_day.csv` al entorno de ejecución o montá Google Drive si lo tenés guardado ahí.
3. Ejecutá las celdas en orden. Cada notebook:
   - Carga y prepara el dataset.
   - Ajusta las variables meteorológicas según el horizonte (Day 1, 2 o 3).
   - Genera variables derivadas: lags, deltas, componentes vectoriales, variables temporales.
   - Divide los datos en entrenamiento (hasta febrero 2025) y prueba (marzo 2025).
   - Entrena el modelo y ajusta hiperparámetros (en el caso de LightGBM).
   - Evalúa el rendimiento con métricas (RMSE, MAE, R²), grafica los resultados y calcula la importancia de variables.

## 💻 Requisitos del entorno

Este trabajo fue desarrollado en **Google Colab**, utilizando:

- Python 3.11.13  
- pandas 2.2.2  
- numpy 2.0.2  
- matplotlib 3.10.0  
- scikit-learn 1.6.1  
- lightgbm 4.5.0  

Estas dependencias están listadas en `requirements.txt` y pueden instalarse localmente con:

```bash
pip install -r requirements.txt
