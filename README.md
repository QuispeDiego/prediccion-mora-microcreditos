# Predicción de mora temprana en microcréditos MYPE
 
Proyecto Integrador de Data Science – **Data Mining Tools (CC209)**, Universidad Peruana de Ciencias Aplicadas.
Entrega actual: **Trabajo Parcial (TP1)**.
 
**Integrantes:**
- Integrante 1
- Integrante 2
- Integrante 3
- Integrante 4
---
 
## Problema
 
Las microfinancieras peruanas financian a micro y pequeñas empresas que, en muchos casos, operan de manera informal y sin registros financieros ordenados. La evaluación crediticia depende en gran medida de la información declarada por el cliente, lo que dificulta anticipar qué créditos no serán pagados.
 
**Pregunta principal:** ¿puede un modelo estimar, al momento de la evaluación, la probabilidad de que un crédito MYPE supere los 30 días de atraso en sus primeros 6 meses, mejor que una regla simple?
 
- **Tipo de problema:** clasificación binaria supervisada, con clases desbalanceadas.
- **Usuario:** el comité de créditos. El modelo entrega una probabilidad de mora como apoyo; la decisión final sigue siendo del comité.
## Datos
 
El dataset es **sintético**, generado por el grupo con autorización del docente mediante `src/generar_datos.py` (semilla fija `2026`, por lo que siempre produce el mismo archivo). Simula los créditos MYPE desembolsados por una entidad microfinanciera peruana.
 
| Característica | Valor |
|---|---|
| Archivo | `data/raw/creditos_mype.csv` |
| Unidad de análisis | Un crédito desembolsado (un cliente puede tener varios) |
| Período | Enero 2022 – diciembre 2024 (corte de extracción: 30/06/2025) |
| Variable objetivo | `mora_30d_6m`: 1 si el crédito superó 30 días de atraso en sus primeros 6 meses |
| Diccionario de variables | `data/diccionario_datos.md` |
 
Al ser datos simulados, las conclusiones describen el proceso generado y no pueden extrapolarse a la población real de microempresarios.
 
## Estructura del repositorio
 
```
prediccion-mora-microcreditos/
├── data/
│   ├── raw/                  # Datos crudos (creditos_mype.csv)
│   ├── processed/            # Datos limpios generados por el notebook 02
│   └── diccionario_datos.md  # Descripción de las variables
├── notebooks/
│   ├── 01_problema_y_eda.ipynb           # Problema, dataset y análisis exploratorio
│   ├── 02_calidad_y_preparacion.ipynb    # Calidad y preparación de datos
│   └── 03_modelado_y_evaluacion.ipynb    # Separación, pipeline, modelos y evaluación
├── src/
│   └── generar_datos.py      # Generador del dataset sintético
├── models/                   # Artefactos de modelos (TF1)
├── reports/
│   └── figures/              # Figuras usadas en el informe y la presentación
├── README.md
└── requirements.txt
```
 
## Cómo ejecutar
 
1. Clonar el repositorio e instalar las dependencias (Python 3.10 o superior):
```bash
   pip install -r requirements.txt
```
 
2. *(Opcional)* Regenerar el dataset. El archivo ya está incluido en `data/raw/`, así que este paso solo es necesario si se quiere verificar su procedencia:
```bash
   python src/generar_datos.py
```
 
3. Ejecutar los notebooks **en orden**, ya que cada uno usa la salida del anterior:
   1. `01_problema_y_eda.ipynb`
   2. `02_calidad_y_preparacion.ipynb` → genera `data/processed/creditos_limpio.csv`
   3. `03_modelado_y_evaluacion.ipynb` → usa el archivo generado por el notebook 02