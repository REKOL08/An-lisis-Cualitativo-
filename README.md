# AnalisisCuant 📊

**Herramienta de análisis cuantitativo 100% en el navegador — sin backend, sin instalación, sin servidor.**

AnalisisCuant es una aplicación web de una sola página (HTML + JS) para realizar análisis estadístico cuantitativo de forma local. Todos los cálculos ocurren directamente en tu navegador: tus datos nunca salen de tu computador.

---

## 🚀 Demo rápida

> Abre el archivo `index.html` en cualquier navegador moderno (Chrome, Firefox, Edge, Safari) y empieza a usarlo de inmediato. No requiere servidor ni conexión a internet.

---

## ✨ Características principales

| Característica | Detalle |
|---|---|
| 🔒 100% local | Los datos nunca salen del navegador |
| 📋 Plantillas incluidas | 8 plantillas CSV listas para descargar |
| 📊 Estadística descriptiva | Media, mediana, moda, desviación, asimetría, curtosis, IQR, CV |
| 📈 Normalidad | Prueba de Shapiro-Wilk aproximada |
| 🔗 Correlaciones | Matriz de Pearson con visualización por colores |
| 🧪 Pruebas inferenciales | Prueba t de Student, Mann-Whitney, ANOVA de un factor |
| 📋 Escala Likert | Alfa de Cronbach, índice general, distribución por ítem |
| 📉 Regresión | Regresión lineal simple con gráfica de dispersión |
| 🌐 Exportación | HTML (español/inglés) y TXT |
| 📱 Responsive | Compatible con pantallas pequeñas |

---

## 🗂️ Estructura del archivo

```
index.html         ← Toda la aplicación (HTML + CSS + JS en un solo archivo)
README.md          ← Este documento
```

---

## 📖 Guía de uso paso a paso

La aplicación está organizada en **4 pasos** accesibles desde la barra de navegación superior.

---

### Paso 1 — Plantilla

Antes de cargar datos, descarga la plantilla que corresponde a tu tipo de análisis.

#### 1.1 Selecciona el modo

En la barra superior encontrarás dos modos:

- **🔬 Investigación** — Para estudios académicos, tesis e investigación científica. Incluye pruebas inferenciales, Likert y regresión.
- **📊 Datos generales** — Para reportes institucionales, empresariales o de gestión. Se enfoca en descriptivos y tendencias.

#### 1.2 Selecciona el tipo de datos

**En modo Investigación** aparecen 4 opciones:

| Tipo | Cuándo usarlo |
|---|---|
| 📋 Escala Likert / Encuesta | Instrumentos con respuestas del 1 al 5 (o 1 al 7). Calcula alfa de Cronbach. |
| 👥 Comparación de grupos | Variables numéricas segmentadas por grupo (control vs. experimental). Para prueba t o ANOVA. |
| 📉 Variables continuas | Múltiples variables numéricas para correlación y regresión. |
| 🏷 Variables categóricas | Frecuencias, tablas cruzadas y chi-cuadrado. |

**En modo Datos generales** aparecen 4 opciones adicionales:

| Tipo | Cuándo usarlo |
|---|---|
| 📑 Indicadores de gestión | KPIs, metas vs. resultados, variación porcentual. |
| 📦 Series / Tendencias | Datos por período (mes, trimestre, año). |
| 📊 Frecuencias y conteos | Distribución de respuestas o eventos por categoría. |
| 🔀 Tabla cruzada | Relación entre dos variables categóricas. |

#### 1.3 Descarga la plantilla

Haz clic en **⬇ Descargar plantilla y continuar →** o en el botón dentro del encabezado de color.

El archivo descargado es un CSV que ya contiene:
- La estructura de columnas correcta
- Datos de ejemplo que puedes reemplazar con los tuyos
- Comentarios explicativos (líneas que empiezan con `#`, que se ignoran automáticamente al cargar)

---

### Paso 2 — Datos

Una vez lista tu base de datos, cárgala en la aplicación. Tienes dos formas:

#### Opción A: Subir archivo

1. Haz clic en la zona punteada **"Arrastra el archivo aquí"** o arrastra tu archivo directamente.
2. El archivo debe ser `.csv` o `.txt`.
3. La aplicación detecta automáticamente el separador (coma, punto y coma o tabulación).

#### Opción B: Pegar datos

1. Haz clic en la pestaña **✏ Pegar datos**.
2. Copia y pega tus datos directamente desde Excel, Google Sheets u otra fuente.
3. La primera fila debe contener los nombres de las columnas.

#### ¿Qué ocurre tras cargar los datos?

- Aparece un chip verde confirmando cuántas filas y columnas se detectaron.
- Se muestra una **vista previa de las primeras 5 filas**.
- La aplicación identifica automáticamente qué columnas son numéricas (etiqueta `NUM`) y cuáles son texto (etiqueta `TXT`).

> ⚠️ **Importante:** Tu archivo no debe tener celdas combinadas, fórmulas ni totales intermedios. Solo datos crudos con encabezados en la primera fila.

---

### Paso 3 — Configuración

Aquí personalizas el análisis antes de ejecutarlo.

#### 3.1 Selecciona las variables a analizar

Verás un selector de chips con todas las columnas detectadas. Las columnas marcadas en **azul-índigo** están seleccionadas. Haz clic en un chip para incluir o excluir una variable del análisis.

> Las columnas `TXT` (texto) se pueden incluir como variable de agrupación, pero no participan en los cálculos estadísticos directamente.

#### 3.2 Parámetros del análisis (modo Investigación)

| Campo | Descripción |
|---|---|
| Variable de agrupación | Columna categórica que define los grupos (ej. "grupo", "sede", "sexo"). Necesaria para prueba t y ANOVA. |
| Tipo de escala Likert | Selecciona el rango de tu instrumento (1–4, 1–5 o 1–7) si aplica. |
| Nivel de significancia (α) | Umbral para las pruebas de hipótesis. Por defecto: 0.05. |
| Prueba inferencial principal | Deja en "Automática" para que la herramienta decida según los datos, o elige manualmente. |

#### 3.3 Información del estudio

Completa el **Título del estudio** (campo obligatorio) y opcionalmente: institución, hipótesis, tamaño muestral, técnica de muestreo y notas metodológicas. Esta información aparece en el informe final.

#### 3.4 Ejecutar

Haz clic en **⚙ Ejecutar análisis** para iniciar el procesamiento. Verás una barra de progreso mientras se calculan todos los estadísticos.

---

### Paso 4 — Análisis (Resultados)

El informe se organiza en secciones colapsables. Puedes navegar entre ellas desde la barra lateral izquierda.

#### E1 — Estadística descriptiva

Para cada variable numérica seleccionada se reportan:

- **Media** (x̄), **mediana** y **moda**
- **Desviación estándar** y **varianza**
- **Mínimo**, **máximo** y **rango**
- **Coeficiente de variación** (CV%) — indica homogeneidad vs. dispersión
- **Cuartiles** Q1, Q3 e **IQR** (rango intercuartílico)
- **Asimetría** (skewness) y **curtosis** — forma de la distribución
- Interpretación automática en texto

Se incluye una **gráfica comparativa de medias y medianas** para todas las variables.

#### E2 — Distribución y normalidad

- **Prueba de Shapiro-Wilk** (aproximación numérica) para cada variable
- Indicación de si la distribución es normal o no (con respecto al α elegido)
- Recomendación automática de prueba paramétrica o no paramétrica
- **Histograma** de la primera variable seleccionada

#### E3 — Matriz de correlaciones

- **Matriz completa de correlaciones de Pearson (r)** entre todas las variables seleccionadas
- Codificación visual por color: verde (correlación positiva), rojo (negativa), gris (baja)
- Lista de **pares con correlación notable** (|r| ≥ 0.5) con interpretación verbal
- Gráfica de barras de correlaciones notables

> La diagonal siempre es 1 (autocorrelación). Esta sección solo aparece si seleccionas 2 o más variables numéricas.

#### E4 — Pruebas inferenciales

Dependiendo de los datos y la configuración:

- **Prueba t de Student** (dos grupos): reporta t, grados de libertad, p-valor y **d de Cohen** (tamaño del efecto)
- **ANOVA de un factor** (tres o más grupos): reporta F, grados de libertad, p-valor
- Decisión estadística clara: **se rechaza H₀** (diferencia significativa) o **no se rechaza H₀**
- Interpretación en lenguaje natural

#### E5 — Análisis de escala Likert *(solo si se configura)*

- **Alfa de Cronbach** (consistencia interna del instrumento)
- Clasificación: inaceptable / cuestionable / aceptable / buena / excelente
- **Índice general** (porcentaje del máximo posible)
- **Gráficas de barras apiladas** por ítem mostrando la distribución de respuestas (1 a 5 con colores)

#### E6 — Regresión lineal simple *(si hay ≥ 2 variables numéricas)*

- **β₀** (intercepto) y **β₁** (pendiente)
- **r de Pearson** y **R²** (varianza explicada)
- **Error estándar** del modelo
- Ecuación del modelo: `ŷ = β₀ + β₁·x`
- **Gráfica de dispersión** con línea de regresión superpuesta
- Interpretación automática de la bondad de ajuste

#### E7 — Síntesis y conclusiones

- Resumen integrado de todos los hallazgos en texto estructurado
- Lista de recomendaciones metodológicas (muestra pequeña, no normalidad, alfa bajo, etc.)
- Nota de cautela sobre las aproximaciones numéricas usadas

---

## 💾 Exportar el informe

Al terminar el análisis, en la esquina superior derecha del panel de resultados encontrarás:

| Botón | Acción |
|---|---|
| 📄 HTML (ES) | Descarga el informe completo en español como página web |
| 📄 HTML (EN) | Descarga el informe completo traducido al inglés |
| 📝 TXT | Descarga el texto plano del informe |
| 🖨 | Abre el diálogo de impresión del navegador |
| + Nuevo | Reinicia la herramienta para un análisis nuevo |

Los archivos HTML exportados son **autocontenidos**: se pueden abrir en cualquier navegador, enviar por correo o adjuntar en un documento sin dependencias externas.

---

## 📐 Reglas del archivo CSV

Para que la herramienta lea correctamente tus datos:

- ✅ Primera fila = nombres de las columnas (encabezados)
- ✅ Una observación / participante / registro por fila
- ✅ Separador: coma `,`, punto y coma `;` o tabulación `TAB` (se detecta automáticamente)
- ✅ Decimal: punto `.` (ejemplo: `3.75`)
- ✅ Texto en columnas categóricas (ej. `"Bogotá"`, `"Control"`)
- ❌ Sin celdas combinadas
- ❌ Sin filas de totales o subtotales
- ❌ Sin fórmulas de Excel
- ❌ Sin espacios extra al inicio/fin de las celdas

---

## ⚙️ Pruebas estadísticas disponibles

| Prueba | Condición de uso |
|---|---|
| Shapiro-Wilk (aprox.) | Siempre, para cada variable numérica |
| Pearson r | Con ≥ 2 variables numéricas |
| Prueba t de Welch | Variable de agrupación con exactamente 2 grupos |
| ANOVA de un factor | Variable de agrupación con ≥ 3 grupos |
| Alfa de Cronbach | Escala Likert configurada con ≥ 2 ítems |
| Regresión lineal simple | Con ≥ 2 variables numéricas (usa las dos primeras seleccionadas) |

---

## 🔒 Privacidad y seguridad

- **Ningún dato se transmite a ningún servidor.** Todo el procesamiento es local en tu navegador.
- No se usa ningún backend, API externa ni base de datos.
- La única dependencia externa es la fuente tipográfica (Google Fonts) y la librería de gráficas (Chart.js desde CDN). Si necesitas operar completamente offline, puedes descargarlas e incrustarlas en el archivo HTML.

---

## 🌐 Compatibilidad

| Navegador | Estado |
|---|---|
| Google Chrome 90+ | ✅ Recomendado |
| Mozilla Firefox 88+ | ✅ Compatible |
| Microsoft Edge 90+ | ✅ Compatible |
| Safari 14+ | ✅ Compatible |
| Opera 76+ | ✅ Compatible |

---

## ⚠️ Limitaciones y advertencias

- Las pruebas de Shapiro-Wilk y las distribuciones t y F se calculan mediante **aproximaciones numéricas**. Para publicaciones académicas formales, confirma los p-valores con software especializado (R, SPSS, jamovi, STATA).
- La regresión lineal incluida es **simple** (una variable predictora). Para regresión múltiple usa software estadístico.
- El tamaño muestral recomendado es **n ≥ 30** para pruebas inferenciales. Con muestras pequeñas, la herramienta muestra una advertencia en las conclusiones.
- La herramienta no guarda los datos entre sesiones. Al cerrar o recargar la página, deberás cargar los datos nuevamente.

---

## 🛠️ Tecnologías utilizadas

- **HTML5 / CSS3 / JavaScript** — sin frameworks
- **[Chart.js 4.4.1](https://www.chartjs.org/)** — gráficas interactivas
- **[Google Fonts](https://fonts.google.com/)** — Inter + JetBrains Mono
- Sin dependencias de Node.js, npm ni ningún entorno de compilación

---

## 👤 Autor

Desarrollado por **[REKOL08](https://github.com/REKOL08)**  
Proyecto académico — Bibliotecas Areandina / BIDIG  
Fundación Universitaria del Área Andina

---

## 📄 Licencia

Este proyecto es de uso libre para fines académicos e institucionales. Si lo adaptas o redistribuyes, menciona la fuente original.

---

*AnalisisCuant v1.0 · Procesamiento 100% local · ES/EN*
