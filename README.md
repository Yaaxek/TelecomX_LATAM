# 📊 Análisis de Churn - TelecomX LATAM

## 📋 Descripción

Este proyecto analiza el comportamiento de los clientes de TelecomX LATAM para identificar los factores que influyen en la evasión (Churn). El objetivo es proporcionar insights accionables que ayuden a reducir la tasa de cancelación de clientes.

## 🎯 Objetivo

- Identificar patrones de comportamiento en clientes que cancelan el servicio
- Determinar las variables más influyentes en la evasión
- Proporcionar recomendaciones estratégicas basadas en datos

## 📁 Estructura del Proyecto
```
Yaaxek/
├── 01_distribucion_churn.png                     # Gráfico de distribución de Churn
├── 02_variables_categoricas.png                  # Gráfico de variables categóricas
├── 03_distribucion_numerica.png                  # Gráfico de distribución numérica
├── 04_correlacion.png                            # Matriz de correlación
├── README.md                                     # Documentación del proyecto
├── TelecomX_Data.json                            # Dataset original
└── TelecomX_LATAM.ipynb                          # Notebook con el análisis completo
└── Informe_Final_TelecomX_LATAM.pdf              # Informe Final de TelecomX LATAM
```

## 🛠️ Tecnologías Utilizadas

- Python 3.x
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Plotly

## 📦 Instalación

1. Clona el repositorio:
```bash
git clone https://github.com/Yaaxek/nombre-repositorio.git
```

2. Instala las dependencias:
```bash
pip install pandas numpy matplotlib seaborn plotly
```

## 🚀 Cómo Ejecutar

1. Abre Google Colab o Jupyter Notebook
2. Carga el archivo `TelecomX_LATAM.ipynb`
3. Sube el archivo `TelecomX_Data.json` al entorno
4. Ejecuta las celdas en orden secuencial
5. Los gráficos se generarán automáticamente

## 📊 Dataset

El dataset `TelecomX_Data.json` contiene 7,267 registros de clientes con las siguientes variables:

| Variable | Descripción |
|----------|-------------|
| customerID | Identificador único del cliente |
| Churn | Si el cliente canceló (1) o no (0) |
| tenure | Meses como cliente |
| Contract | Tipo de contrato (Mensual, Anual, Bianual) |
| PaymentMethod | Método de pago |
| Charges.Monthly | Cargo mensual |
| Charges.Total | Cargo total acumulado |
| InternetService | Tipo de servicio de internet |
| OnlineSecurity | Si tiene seguridad en línea |
| TechSupport | Si tiene soporte técnico |

## 🔍 Análisis Realizados

1. **Limpieza de Datos**
   - Tratamiento de 224 valores vacíos en Churn
   - Tratamiento de 11 valores vacíos en Charges.Total
   - Conversión de variables categóricas a numéricas
   - Creación de variables: Cuentas_Diarias y Cantidad_Servicios

2. **Análisis Exploratorio**
   - Distribución de Churn
   - Análisis de variables categóricas
   - Análisis de variables numéricas
   - Correlación entre variables

3. **Visualizaciones**
   - `01_distribucion_churn.png` - Gráfico de pie con distribución de Churn
   - `02_variables_categoricas.png` - Barras horizontales con tasa de cancelación
   - `03_distribucion_numerica.png` - Histograma, Boxplots y Violinplot
   - `04_correlacion.png` - Heatmap de correlación

## 📈 Principales Hallazgos

- **Tasa de Churn:** 26.5% de los clientes cancelaron (1,869 de 7,043)

- **Factores de riesgo críticos (≥35% cancelación):**
  - Cheque electrónico: 45.29%
  - Contrato mes a mes: 42.71%
  - Fibra óptica: 41.89%
  - Adulto mayor: 41.68%

- **Factores de estabilidad:**
  - Contrato 2 años: 2.83% cancelación
  - Pagos automáticos: 15-17% cancelación

## 💡 Recomendaciones

1. Enfocarse en retención durante los primeros 12 meses
2. Incentivar migración de cheque electrónico a pago automático
3. Promover contratos de largo plazo con descuentos
4. Incluir servicios de protección (Seguridad, Soporte Técnico)
5. Crear programa especial para adultos mayores
6. Revisar precio/calidad del servicio de fibra óptica

## ⚠️ Problemas Conocidos y Soluciones

| Problema | Solución |
|----------|----------|
| Error al cargar JSON | Usar `pd.json_normalize()` para aplanar estructura |
| Valores vacíos en Churn | Eliminar registros (no se puede asumir estado) |
| Valores vacíos en Charges.Total | Calcular: Charges.Monthly × tenure |
