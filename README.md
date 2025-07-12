# Proyecto de Predicción de Visibilidad en los Lagos de Covadonga

Este repositorio contiene un proyecto que utiliza datos meteorológicos y observaciones directas para predecir si habrá suficiente visibilidad para visitar los Lagos de Covadonga (Asturias, España) en un día determinado.

## Descripción del Proyecto

El sistema combina:
- Datos meteorológicos oficiales de la AEMET (Agencia Estatal de Meteorología) para la zona de Cangas de Onís y los Lagos de Covadonga
- Observaciones directas recopiladas manualmente de días anteriores
- Imágenes de la webcam en los lagos (https://www.webcamsdeasturias.com/asturias/oriente/cangas-de-onis/cangas-de-onis/lagos-de-covadonga-lago-enol-hd/159/)

Con estos datos, se construye un modelo de Machine Learning que predice la probabilidad de que haya niebla densa que dificulte la visita a los lagos.

🚀 **Objetivo principal**: Predecir si habrá suficiente visibilidad para visitar los lagos o si estará demasiado nublado o con niebla.

## Estructura del Repositorio

```
.
├── data/                   
│   ├── raw/                # Datos sin procesar de AEMET
│   └── processed/          # Datos combinados y limpios
├── models/                 # Modelos entrenados
├── notebooks/              # Jupyter notebooks de análisis
├── keys/                   # Almacenar API keys
├── requirements.txt        # Requisitos en Python
└── README.md               # Este archivo
```

## Flujo de Trabajo

1. Recolección de datos:
   - Obtención automática de datos meteorológicos de la API de AEMET.
   - Incorporación de observaciones manuales recopiladas previamente.

2. Procesamiento:
   - Limpieza y normalización de datos.
   - Combinación en un único dataframe.
   - Exportación a CSV para análisis.

3. Modelado:
   - Entrenamiento de modelo predictivo (clasificación binaria: "subible"/"no subible").
   - Evaluación del rendimiento del modelo.
   - Exportación del modelo entrenado.

4. Predicción:
   - Uso del modelo para predecir condiciones futuras basadas en pronósticos
  
## Uso:

1. Instalar dependencias:
```bash
pip install -r requirements.txt
```

2. Crear en el directorio `keys` un fichero `api_key.py` que contenga la variable `api_key` cuyo valor sea la API key de la AEMET (personal).

3. Ejecutar el notebook para generar datos, abriendo el notebook `data_from_aemet.ipynb` para generar los CSV pertinentes. Completar con los datos "manuales" que hagan falta.
   > IMPORTANTE: Si se ejecuta, se necesita tener un modelo de Ollama ejecutándose en local, dado que el notebook hace uso de un LLM en local.

## Contribución
Las contribuciones son bienvenidas. Por favor, abre un issue para discutir cambios importantes antes de hacer un pull request.

Desarrollado enteramente por Jorge Ruiz López ([jorge.ruizl@um.es](mailto:jorge.ruizl@um.es) por fines personales y educativos.

