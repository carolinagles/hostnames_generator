# Generador Aleatorio de Hostnames

## Descripción

Este proyecto implementa un algoritmo para generar 1500 hostnames aleatorios siguiendo una estructura específica basada en sistemas operativos, entornos y países. Los hostnames generados se almacenan en un DataFrame de pandas y se exportan a un archivo CSV para su posterior análisis y visualización.

## Estructura del Proyecto

### 1. Importación de Librerías
- `random`: Generación de números aleatorios
- `pandas`: Manipulación y análisis de datos
- `numpy`: Operaciones numéricas
- `matplotlib.pyplot` y `seaborn`: Visualización de datos

### 2. Variables Globales
- `hostnames`: Lista para almacenar los hostnames generados
- `dataset`: Lista para almacenar los datos estructurados
- `df`: DataFrame principal

### 3. Composición de Hostnames

Cada hostname sigue la estructura de 8 caracteres:

| Posición | Componente | Códigos | Probabilidad |
|----------|------------|---------|--------------|
| 1 | Sistema Operativo | L (Linux), S (Solaris), A (AIX), H (HP-UX) | 40%, 30%, 20%, 10% |
| 2 | Entorno | D (Development), I (Integration), T (Testing), S (Staging), P (Production) | 10%, 10%, 25%, 25%, 30% |
| 3-5 | País | NOR, FRA, ITA, ESP, GER, IRL | 6%, 9%, 16%, 16%, 23%, 30% |
| 6-8 | Nodo | 001-999 | Uniforme |

**Ejemplo**: `AIGER789` (A → AIX | I → Integration | GER → Germany | 789 → Nodo)

### 4. Funciones Principales

- `set_hostnames(number_of_hosts)`: Genera hostnames aleatorios
- `get_os(hostname)`: Extrae el sistema operativo del hostname
- `get_environment(hostname)`: Extrae el entorno del hostname
- `get_country(hostname)`: Extrae el país del hostname
- `set_dataframe(count)`: Construye el DataFrame con todos los datos

### 5. Visualización de Datos

El proyecto incluye visualizaciones para analizar la distribución de:
- Hosts por país y entorno
- Sistemas operativos agrupados por país
- Totales de sistemas operativos
- Hosts por país agrupados por entorno

## Archivos Generados

- `hosts.csv`: Dataset completo con 1500 registros
- Gráficos de análisis de distribución

## Resultados Esperados

- Distribución proporcional según las probabilidades definidas
- Irlanda y Alemania como países con mayor número de hosts
- Testing, Staging y Production como entornos más representados
- Validación de la correcta implementación del algoritmo de generación

## Requisitos

- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn

Este proyecto demuestra habilidades en generación de datos aleatorios, manipulación de DataFrames, y visualización de datos para análisis de distribuciones.