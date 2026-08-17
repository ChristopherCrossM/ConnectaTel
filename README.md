# 📞 ConnectaTel - Análisis Exploratorio y Segmentación de Clientes

Este proyecto realiza un Análisis Exploratorio de Datos (EDA) y una segmentación estratégica sobre la base de clientes de la empresa de telecomunicaciones **ConnectaTel**. El objetivo principal es comprender las pautas de consumo (llamadas, minutos y mensajes), evaluar la presencia de valores atípicos (*outliers*) y categorizar a los usuarios según sus hábitos de uso y perfiles demográficos.

---

## 🚀 Estructura del Proyecto y Flujo de Análisis

El análisis está estructurado secuencialmente en las siguientes etapas clave:

1. **Limpieza y Preparación de Datos:**
   * Tratamiento de valores faltantes y nulos en columnas demográficas y operativas.
   * Formateo y estandarización de tipos de datos (fechas, cadenas e identificadores).

2. **Análisis de Distribuciones e Insights de Consumo:**
   * Evaluación de las variables de servicio (`cant_llamadas` y `cant_minutos_llamada`) mediante histogramas comparativos y curvas de densidad KDE segadas por tipo de plan (`Básico` vs `Premium`).

3. **Identificación y Tratamiento de Outliers:**
   * Análisis gráfico mediante **Boxplots** para las variables `age`, `cant_mensajes`, `cant_llamadas` y `cant_minutos_llamada`.
   * Cálculo de límites teóricos superiores utilizando el **Método del Rango Intercuartílico (IQR)**.
   * **Decisión de Negocio:** Conservación total de los valores extremos al confirmar que corresponden a comportamiento de uso real (*heavy users*) y no a errores de captura o migración de datos.

4. **Segmentación de Clientes:**
   * **Segmentación por Uso (`grupo_uso`):**
     * `Bajo uso`: < 5 llamadas y < 5 mensajes.
     * `Uso medio`: < 10 llamadas y < 10 mensajes.
     * `Alto uso`: Resto de las combinaciones de mayor volumen.
   * **Segmentación por Edad (`grupo_edad`):**
     * Categorización en `Joven` (<30 años), `Adulto` (30-59 años) y `Adulto Mayor` (60+ años).

5. **Visualización Segmentada:**
   * Gráficos de barras (`sns.countplot`) para estudiar la distribución volumétrica de los clientes dentro de cada grupo.

6. **Insight Ejecutivo para Stakeholders:**
   * Síntesis de hallazgos y recomendaciones estratégicas de negocio orientadas a retención, empaquetado de planes y estrategias de *upselling*.

---

## 🛠️ Tecnologías y Librerías Utilizadas

* **Lenguaje:** Python 3.9+
* **Procesamiento de Datos:** `pandas`, `numpy`
* **Visualización de Datos:** `matplotlib`, `seaborn`
* **Entorno:** Jupyter Notebook / Google Colab

---

## 💡 Principales Conclusiones y Recomendaciones de Negocio

* **Naturaleza de los Outliers:** Los consumos máximos (de hasta 155 minutos o 17 mensajes) son representativos de usuarios con una demanda de red intensiva. Recortar o eliminar estos datos distorsionaría las proyecciones de ingresos reales de la compañía.
* **Oportunidades Comerciales:**
  * **Plan Unlimited/Heavy Talker:** Diseñar paquetes con tarifas planas atractivas para proteger al segmento de alto uso de minutos frente al *churn*.
  * **Estrategias de Migración (Upselling):** Crear incentivos ajustados para escalar a los clientes con un perfil de *Bajo uso* hacia niveles intermedios de mayor monetización.
