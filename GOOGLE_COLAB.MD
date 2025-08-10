# Guía práctica: Uso de Google Colab para Análisis con Python, pandas, NumPy, Matplotlib y Plotly

Paso a paso para Google Colab

1) Crear y configurar un nuevo Notebook

Ve a Google Colab

Inicia sesión con tu cuenta de Google.

Haz clic en Archivo > Nuevo cuaderno.

Opcional: Renombra el cuaderno para identificarlo.

2) Preparar el entorno de trabajo

Instala las librerías necesarias:

!pip install pandas numpy matplotlib plotly python-dotenv

3) Conectar Google Drive (persistencia de datos)

from google.colab import drive
drive.mount('/content/drive')
# Tus archivos estarán en /content/drive/MyDrive/

4) Subir archivos desde tu PC

from google.colab import files
uploaded = files.upload()  # Selecciona un archivo CSV

5) Leer datos con pandas

import pandas as pd
df = pd.read_csv('nombre_archivo.csv')
df.head()

6) Operaciones básicas con pandas y NumPy

import numpy as np
# Resumen
print(df.info())
print(df.describe())
# Crear nueva columna
df['total'] = df['cantidad'] * df['precio']
# Media usando NumPy
print(np.mean(df['total']))

7) Visualizar datos con Matplotlib

import matplotlib.pyplot as plt
plt.plot(df['fecha'], df['total'])
plt.title('Ventas en el tiempo')
plt.xlabel('Fecha')
plt.ylabel('Total')
plt.show()

8) Gráficos interactivos con Plotly

import plotly.express as px
fig = px.line(df, x='fecha', y='total', title='Ventas en el tiempo')
fig.show()

9) Guardar resultados en Drive

import plotly.io as pio
pio.write_html(fig, '/content/drive/MyDrive/ventas_interactivas.html')

10) Buenas prácticas en Colab

Guarda tu progreso: Archivo > Guardar una copia en Drive.

Usa celdas de texto para documentar pasos y conclusiones.

Evita subir claves o credenciales; usa variables temporales.

Descarga los notebooks listos: Archivo > Descargar .ipynb o .py.

