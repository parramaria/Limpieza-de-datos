

Este proyecto aborda la limpieza y preprocesamiento del conjunto de datos **AB\_NYC\_2019**, el cual contiene información detallada sobre alojamientos en la ciudad de Nueva York. El objetivo es optimizar la calidad de los datos para su posterior análisis y modelado, eliminando inconsistencias y estandarizando información clave.


## 📂 **Estructura del Proyecto**

1. **Carga de Datos:**
   Se utiliza `pandas` para importar el dataset en un DataFrame, estableciendo la columna `id` como índice principal.

   ```python
   import pandas as pd
   df = pd.read_csv("./Ejercicio_3/AB_NYC_2019.csv", index_col=["id"])
   ```

2. **Limpieza de Datos:**

   * Imputación de valores nulos:

     * En `reviews_per_month`, los valores faltantes se completan con `0` si el número de reseñas es igual a `0`.
     * En las columnas `name` y `host_name`, se asigna el valor **Desconocido** cuando están vacías.
   * Eliminación de valores extremos:

     * Se descartan propiedades con un precio superior a **\$1000** por noche.
     * Se filtran estancias mínimas superiores a **365 noches**.
   * Conversión de formatos:

     * La columna `last_review` se convierte al formato de fecha (`datetime`).
   * Estandarización de texto:

     * Los campos `room_type`, `neighbourhood_group` y `neighbourhood` se transforman a minúsculas y se eliminan espacios en blanco.

3. **Exportación del Dataset Limpio:**
   Los datos procesados se exportan a un nuevo archivo CSV para su posterior análisis:

   ```python
   df.to_csv("AB_NYC_2019_limpio.csv", index=False)
   ```

---

## ✅ **Resultados Esperados**

* Un conjunto de datos libre de valores nulos críticos.
* Estándares de escritura uniformes.
* Eliminación de outliers que puedan distorsionar el análisis.
* Formatos de fecha correctamente establecidos para futuros estudios temporales.

---

## 🚀 **Ejecución**

1. Clonar el repositorio.
2. Instalar las dependencias necesarias:

   ```bash
   pip install pandas
   ```
3. Ejecutar el notebook para generar el archivo limpio.

---

## ✒️ **Autor**

Proyecto desarrollado como parte de un ejercicio de limpieza de datos en Python 2025-1 Maria Paula Sanchez


