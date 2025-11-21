# Online Store Recommendation A/B Test

Este proyecto analiza el experimento A/B **recommender_system_test**, cuyo objetivo es evaluar el impacto de un nuevo sistema de recomendaciones en una tienda en línea. El análisis incluye inspección del diseño experimental, revisión del calendario de marketing, exploración del funnel de eventos y pruebas estadísticas que permiten determinar si la nueva funcionalidad mejora o afecta la conversión de los usuarios.

---

## 📌 Objetivo

- Evaluar el impacto del sistema de recomendaciones propuesto.
- Verificar la validez del experimento A/B y su diseño.
- Identificar posibles interferencias provenientes de campañas de marketing activas.
- Analizar el funnel completo y compararlo entre los grupos A y B.
- Realizar pruebas estadísticas para validar la significancia de las diferencias en conversión.

---

## 🗄️ Descripción de los datos

El proyecto utiliza tres archivos:

### **1. ab_project_marketing_events_us.csv**  
Calendario de eventos de marketing:
- Nombre del evento  
- Fecha de inicio y fin  
- Tipo de campaña  

### **2. final_ab_new_users_upd_us.csv**  
Usuarios seleccionados para el experimento:
- `user_id`  
- `first_date` (primera interacción)  
- `group` (A o B)

### **3. final_ab_events_upd_us.csv**  
Eventos de los usuarios dentro del experimento:
- `event_time`  
- `event_name` (product_page, product_cart, purchase)
- `user_id`  
- `group`

---

## 🧹 Preparación y Limpieza de Datos

- Conversión de columnas con fechas a formato `datetime64`.
- Validación del periodo experimental (2020-12-07 al 2021-01-04).
- Revisión de usuarios que interactuaron fuera del marco temporal.
- Eliminación de interacciones que coinciden con campañas de marketing activas.
- Verificación del equilibrio entre grupos A y B en número de usuarios.
- Confirmación de que ambos grupos tienen representación similar durante todo el experimento.

---

## 📊 Análisis Exploratorio (EDA)

### Marketing
- Identificación de campañas activas durante el experimento.
- Detección de campañas que podrían sesgar los resultados.
- Se encuentra que la campaña *Christmas & New Year Promo* inicia el **25 de diciembre**, afectando eventos posteriores.

### Actividad del usuario
- Conteo de eventos por grupo y por etapa del funnel.
- Los usuarios del grupo A muestran mayor volumen de interacción.
- Los usuarios del grupo B generan menos eventos totales.

### Funnel (product_page → product_cart → purchase)
- Ninguna etapa del embudo muestra mejora para el grupo B.
- El grupo B presenta menor compra final.
- Se visualizan caídas claras en el proceso para el grupo experimental.

---

## 📈 Resultados Preliminares

- El sistema de recomendaciones **no mejora la conversión**.
- Usuarios expuestos al sistema (grupo B) realizan menos compras.
- Existen diferencias en el volumen de interacción entre los grupos.

---

## 🧪 Pruebas Estadísticas

- Pruebas de diferencia de proporciones para cada etapa del funnel.
- Evaluación de conversión global A vs. B.
- Cálculo de p-values para validar significancia.
- Resultados indican que el sistema de recomendaciones **no tiene un efecto positivo**.

---

## 🧩 Conclusiones

- El diseño experimental es válido, pero la campaña navideña introduce potencial sesgo temporal.
- El grupo B muestra menor actividad y menor conversión.
- El nuevo sistema de recomendaciones **no debería implementarse**.
- Se recomienda una fase adicional de diseño para mejorar el algoritmo antes de repetir el experimento.

---

## 🛠 Tecnologías Utilizadas

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib / Seaborn**
- **Statsmodels / SciPy**
- **Jupyter Notebook**

---

## 📁 Archivos del Proyecto

- `online-store-recommendation-ab-test.ipynb` — Notebook con todo el análisis.
- Archivos de marketing, usuarios y eventos.

---

## 📬 Contacto

Proyecto desarrollado como parte del portafolio analítico de **Monica Baca**.
