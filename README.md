# 🌱 Análisis de Energías Renovables — Dataset IRENA 2023

Análisis de la evolución del sistema energético mundial a partir de los datos oficiales de la **International Renewable Energy Agency (IRENA)**, con foco en el crecimiento de las energías renovables y su relación con el **ODS 7** de la Agenda 2030.

---

## 📌 Objetivo

- Analizar la evolución del mix energético mundial entre 2000 y 2023
- Estudiar el peso de las principales tecnologías renovables: solar, eólica, hidráulica y bioenergía
- Evaluar el aprovechamiento real de la capacidad instalada mediante el **factor de capacidad**
- Relacionar los resultados con el indicador **ODS 7.b.1** (capacidad renovable per cápita)

---

## 🗂️ Fuente de datos

- **Dataset:** IRENA Renewable Energy Statistics
- **Enlace oficial:** https://www.irena.org/Publications/2023/Jul/Renewable-energy-statistics-2023
- **Cobertura:** Mundial, por país, tecnología y año
- **Variables principales:** Generación eléctrica (GWh), Capacidad instalada (MW), Generación térmica (TJ), Indicador ODS 7.b.1

---

## 🏗️ Arquitectura del proyecto

El proyecto sigue una **arquitectura medallón** implementada en **Microsoft Fabric**:

<img width="1349" height="213" alt="image" src="https://github.com/user-attachments/assets/8410e7c9-e9e9-438c-990e-9104abe9e1f3" />


| Capa | Descripción |
|---|---|
| **Bronze** | Datos crudos cargados desde el fichero original IRENA |
| **Silver** | Datos limpios, tipados y transformados |
| **Modelo Semántico** | Modelo dimensional con tabla de hechos y dimensiones |
| **Visualización** | Informe interactivo en Power BI |

---

## 🔄 Transformaciones principales

- Limpieza y tipado de datos en **Power Query**
- Tratamiento de valores nulos
- Conversión de unidades: generación térmica de TJ a GWh (1 GWh = 3,6 TJ)
- Modelado dimensional: tabla de hechos + dimensiones de calendario, país y tecnología
- Creación de medidas DAX para métricas clave

---

## 📐 Métricas clave

**Factor de capacidad**
> Mide el aprovechamiento real de una instalación eléctrica frente a su máximo teórico

```
Factor de capacidad = Generación eléctrica (GWh) / (Capacidad instalada (MW) × 8.760 horas)
```

**Porcentaje de renovables**
> Proporción de generación renovable sobre el total de electricidad generada

**ODS 7.b.1**
> Capacidad renovable instalada por habitante (W/habitante)

---

## 📊 Visualizaciones

### Presencia de las energías renovables
<img width="2446" height="1284" alt="image" src="https://github.com/user-attachments/assets/11078839-382b-49d3-9272-0dc24cd1b9f7" />


### Evolución por tecnología
<img width="2456" height="1328" alt="image" src="https://github.com/user-attachments/assets/e155f497-7348-4a88-9161-6a42cdf07732" />


### Factor de capacidad
<img width="2454" height="1358" alt="image" src="https://github.com/user-attachments/assets/133f47f0-05a3-4008-a722-bc94802ac265" />


### ODS 7 — Capacidad renovable per cápita
<img width="2450" height="1214" alt="image" src="https://github.com/user-attachments/assets/499d249b-4d11-443a-9fd4-826a85b6d966" />


---

## 💡 Principales conclusiones

- Las energías renovables muestran una **tendencia creciente sostenida** desde 2000
- La **energía solar y eólica** lideran el crecimiento en las últimas dos décadas
- La **bioenergía** presenta los mayores factores de capacidad entre las renovables
- El aumento de la capacidad renovable per cápita indica **progreso hacia el ODS 7**
- La generación hidráulica, aunque dominante históricamente, pierde peso relativo frente a solar y eólica

---

## 🛠️ Tecnologías utilizadas

![Microsoft Fabric](https://img.shields.io/badge/Microsoft_Fabric-0078D4?style=flat&logo=microsoft&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![Power Query](https://img.shields.io/badge/Power_Query-217346?style=flat&logo=microsoft&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=flat&logo=microsoft&logoColor=white)

- **Microsoft Fabric** — Lakehouse con arquitectura medallón (Bronze / Silver)
- **Power Query** — Transformación y limpieza de datos
- **Power BI Service** — Modelo semántico y visualización interactiva
- **DAX** — Métricas y medidas calculadas

---

## 📁 Estructura del repositorio

```
├── img/
│   ├── arquitectura_medallon.png
│   ├── dashboard_presencia.png
│   ├── dashboard_evolucion.png
│   ├── dashboard_factor_capacidad.png
│   └── dashboard_ods7.png
└── README.md
```

---

## 👤 Autor

**Rosa Sierra** (2025-2026)
