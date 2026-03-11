# telecom-analysis
# 📊 Análisis de Clientes y Segmentación – ConnectaTel

## 🎯 Objetivo
Analizar el comportamiento de los clientes de ConnectaTel para:
- Detectar problemas de datos (nulos, sentinels, outliers).  
- Segmentar clientes por **edad** y **nivel de uso**.  
- Identificar patrones de alto consumo y oportunidades comerciales.  

---

## 📂 Datasets
| Dataset | Descripción | Columnas clave |
|---------|------------|----------------|
| `users.csv` | Datos de clientes | user_id, age, city, plan, reg_date, churn_date |
| `usage.csv` | Historial de uso | user_id, type (call/text), date, duration, length |
| `plans.csv` | Información de planes | plan_id, plan_name, monthly_fee, included_minutes, included_messages |

---

## 🛠 Etapas del análisis
1. **Carga y exploración de datos**: revisión de tipos y nulos.  
2. **Limpieza de datos**: sentinels (`age=-999`), fechas futuras, valores inválidos (`city='?'`).  
3. **Detección de nulos y MAR**: `duration` y `length` dependen de `type`.  
4. **Outliers**: boxplots + método IQR; se mantienen los extremos válidos.  
5. **Segmentación de clientes**:
   - **Por edad:** Joven (<30), Adulto (30–59), Adulto Mayor (≥60)  
   - **Por uso:** Bajo (<5), Medio (<10), Alto (resto)  
6. **Visualización**: histogramas, boxplots, countplots.  
7. **Insights y recomendaciones**: segmentos de alto valor y oportunidades de planes.

---

## 📈 Insights clave
- **Segmentos por edad**: usuarios jóvenes más activos en mensajes; adultos mayores menos uso.  
- **Segmentos por uso**: Premium = alto uso; Básico = bajo/medio uso.  
- **Outliers**: algunos usuarios extremos generan mucho tráfico; representan oportunidades para planes especiales.  
- **Recomendaciones**:
  - Optimizar planes Premium y crear opciones para usuarios de alto consumo.  
  - Dirigir marketing a jóvenes y usuarios de uso medio para upgrades.  
  - Monitorear churn y hábitos por segmento.

---

## 🚀 Ejecución del Notebook
1. Abrir en **[Google Colab](https://colab.research.google.com/)** o **Jupyter Notebook**.  
2. Subir los datasets (`users.csv`, `usage.csv`, `plans.csv`).  
3. Instalar librerías si no están disponibles:
   ```bash
   pip install pandas seaborn matplotlib numpy
