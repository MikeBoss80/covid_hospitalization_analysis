# Data Analysis Architecture - COVID Hospitalization
## Estructura Simplificada para Análisis de Datos

---

## 📊 Project Structure (Simplified)

```
covid_hospitalization_analysis/
│
├── 01_Data/                          # Archivos de datos
│   └── *.xlsx, *.csv                 # Fuentes de datos (temporales, demográficos)
│
├── 02_Dashboards/                    # Visualizaciones & Reportes
│   ├── PowerBI/                      # Dashboards interactivos (.pbix)
│   ├── Excel/                        # Reportes estáticos (.xlsx)
│   └── Images/                       # Screenshots de dashboards
│
├── 03_Documentation/                 # Documentación
│   └── *.md                          # Guías y referencias
│
└── README.md                         # Inicio rápido
```

---

## 🔄 Simple Data Workflow

```
Data Sources
(Hospital Systems, CDC, etc.)
         ↓
    01_Data/
    (CSV, Excel files)
         ↓
Power BI ←→ Excel
(dashboards)  (reports)
         ↓
   📊 Visualizations
   📈 Analysis
```

---

## 📁 What Goes Where

### **01_Data/** - Data Files
- **Location**: C:\laragon\www\covid_hospitalization_analysis\01_Data\
- **Contains**: 
  - `.xlsx` files con datos fuente
  - `.csv` exports si es necesario
  - Archivos temporales de análisis
- **Naming**: `COVID_Analysis_YYYY-MM-DD.xlsx` o similar
- **Note**: Nunca edites directamente, guarda cambios en versiones nuevas

### **02_Dashboards/PowerBI/** - Power BI Reports
- **Dashboards interactivos** (.pbix)
- **Nombres**:
  - `Temporal_Trends_Analysis.pbix`
  - `Demographic_Risk_Dashboard.pbix`
  - `State_Risk_Volatility.pbix`
- **Conexión**: Directa a CSV/Excel en `01_Data/`
- **Refresh**: Manual o automático diario

### **02_Dashboards/Excel/** - Excel Reports
- **Reportes estáticos** (.xlsx)
- **Contiene**: Análisis, gráficos, tablas
- **Nombres**: `Weekly_Report_YYYY-MM-DD.xlsx`

### **02_Dashboards/Images/** - Screenshots
- **Capturas** de dashboards para presentaciones
- **Formato**: PNG o JPG
- **Propósito**: Documentación y sharing rápido

### **03_Documentation/** - Guías & Referencias
- `DATA_FIELDS.md` - Definición de campos
- `ANALYSIS_GUIDE.md` - Cómo usar los dashboards
- `UPDATE_PROCESS.md` - Pasos para actualizar datos

---

### 1. **Temporal Trends & Volatility Analysis**
- Quarterly pandemic rate comparison (2020-2026)
- 3-month moving average trends
- Seasonal monthly patterns
- Pandemic volatility over time

### 2. **Demographic Risk Analysis**
- Mortalidad por raza (Race)
- Mortalidad por edad (Age groups)
- Mortalidad por género (Sex)
- Interactive filters por año

### 3. **State Risk vs Volatility**
- Cada estado como punto en gráfico
- X-axis: Volatilidad promedio mensual
- Y-axis: Riesgo (mortalidad/incidentes)
- Identificar patrones por estado

### 4. **Racial Risk vs Volatility**
- Análisis por grupo racial
- Tasas mensuales vs volatilidad demográfica

### 5. **Age Group Risk vs Volatility**
- Distribución por grupos de edad
- Análisis de riesgo-volatilidad

---

## 🚀 Quick Start in 5 Steps

### Step 1: Organizar tus datos
```
1. Coloca tus archivos .xlsx en: 01_Data/
2. Nómbralos claro: COVID_Source_2026-05-27.xlsx
3. Guarda frecuentemente con versión nueva
```

### Step 2: Crear Dashboards en Power BI
```
1. Abre Power BI Desktop
2. Get Data → Excel → Selecciona archivo en 01_Data/
3. Crea visualizaciones (ya tienes los modelos)
4. Guarda en: 02_Dashboards/PowerBI/
```

### Step 3: Crear Reportes en Excel
```
1. Abre Excel con el archivo de datos
2. Crea tablas pivote y gráficos
3. Guarda en: 02_Dashboards/Excel/
```

### Step 4: Capturar screenshots
```
1. De cada dashboard
2. Guarda en: 02_Dashboards/Images/
3. Usa para presentaciones y documentación
```

### Step 5: Actualizar documentación
```
1. Edita 03_Documentation/DATA_FIELDS.md
2. Documenta nuevos campos si los añades
3. Mantén un log de cambios
```
