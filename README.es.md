# AnalisisCuant 📊

[🇬🇧 English](README.md) | 🇪🇸 **Español**

**Herramienta de análisis cuantitativo 100% en el navegador — sin backend, sin instalación, sin servidor.**

AnalisisCuant es una aplicación web de una sola página (HTML + JS) para realizar análisis estadístico cuantitativo de forma local. Todos los cálculos ocurren directamente en tu navegador: tus datos nunca salen de tu computador.

![Captura de AnalisisCuant](docs/screenshot.png)

---

## 🚀 Demo rápida

> **[Pruébala en vivo →](https://REKOL08.github.io/AnalisisCuant/)**

Abre el archivo `index.html` en cualquier navegador moderno (Chrome, Firefox, Edge, Safari) y empieza a usarlo de inmediato. No requiere servidor ni conexión a internet.

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
index.html   ← Toda la aplicación (HTML + CSS + JS en un solo archivo)
README.md    ← Versión en inglés
README.es.md ← Este documento
LICENSE      ← Licencia MIT
```

---

## 📖 Guía de uso paso a paso

La aplicación está organizada en **4 pasos** accesibles desde la barra de navegación superior.

---

### Paso 1 — Plantilla

Antes de cargar datos, descarga la plantilla que corresponde a tu tipo de análisis.

#### 1.1 Selecciona el modo

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

Haz clic en **⬇ Descargar plantilla y continuar →**. El archivo descargado es un CSV que ya contiene la estructura de columnas correcta, datos de ejemplo que puedes reemplazar con los tuyos, y comentarios explicativos (líneas que empiezan con `#`, que se ignoran automáticamente al cargar).

---

### Paso 2 — Datos

Una vez lista tu base de datos, cárgala en la aplicación de dos formas posibles:

- **Subir archivo:** arrastra tu `.csv` o `.txt`, o haz clic para seleccionarlo. El separador (coma, punto y coma o tabulación) se detecta automáticamente.
- **Pegar datos:** copia y pega tus datos directamente desde Excel, Google Sheets u otra fuente. La primera fila debe contener los nombres de las columnas.

Tras cargar los datos verás un chip verde con filas/columnas detectadas, una vista previa de las primeras 5 filas, y la identificación automática de columnas numéricas (`NUM`) y de texto (`TXT`).

> ⚠️ **Importante:** tu archivo no debe tener celdas combinadas, fórmulas ni totales intermedios. Solo datos crudos con encabezados en la primera fila.

---

### Paso 3 — Configuración

Selecciona las variables a analizar, la variable de agrupación (para prueba t o ANOVA), el tipo de escala Likert, el nivel de significancia (α, por defecto 0.05) y la prueba inferencial principal (o déjala en "Automática"). Completa el título del estudio (obligatorio) y, opcionalmente, institución, hipótesis, tamaño muestral, técnica de muestreo y notas metodológicas.

---

### Paso 4 — Análisis (Resultados)

El informe se organiza en secciones colapsables:

- **E1 — Estadística descriptiva:** media, mediana, moda, desviación estándar, varianza, mínimo/máximo, rango, CV%, cuartiles, IQR, asimetría, curtosis, con interpretación automática.
- **E2 — Distribución y normalidad:** prueba de Shapiro-Wilk aproximada, recomendación de prueba paramétrica o no paramétrica, histograma.
- **E3 — Matriz de correlaciones:** matriz completa de Pearson con codificación por color, pares con correlación notable (|r| ≥ 0.5).
- **E4 — Pruebas inferenciales:** prueba t de Student (con d de Cohen), ANOVA de un factor, decisión estadística clara.
- **E5 — Escala Likert:** alfa de Cronbach, clasificación de fiabilidad, índice general, gráficas de barras apiladas por ítem.
- **E6 — Regresión lineal simple:** β₀, β₁, r de Pearson, R², error estándar, gráfica de dispersión con línea de regresión.
- **E7 — Síntesis y conclusiones:** resumen integrado, recomendaciones metodológicas, nota de cautela sobre las aproximaciones numéricas usadas.

---

## 💾 Exportar el informe

| Botón | Acción |
|---|---|
| 📄 HTML (ES) | Informe completo en español, autocontenido |
| 📄 HTML (EN) | Informe completo traducido al inglés |
| 📝 TXT | Texto plano del informe |
| 🖨 | Abre el diálogo de impresión del navegador |
| + Nuevo | Reinicia la herramienta para un análisis nuevo |

Los archivos HTML exportados son **autocontenidos**: se pueden abrir en cualquier navegador, enviar por correo o adjuntar en un documento sin dependencias externas.

---

## 📐 Reglas del archivo CSV

- ✅ Primera fila = nombres de las columnas (encabezados)
- ✅ Una observación / participante / registro por fila
- ✅ Separador: coma `,`, punto y coma `;` o tabulación (se detecta automáticamente)
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

## 🤝 Contribuciones

Los issues y pull requests son bienvenidos. Si quieres agregar una nueva prueba estadística, plantilla o traducción, abre primero un issue para discutir el enfoque.

## 👤 Autor

Desarrollado por **[REKOL08](https://github.com/REKOL08)**
Proyecto académico — Bibliotecas Areandina / BIDIG
Fundación Universitaria del Área Andina

## 📄 Licencia

Publicado bajo la [Licencia MIT](LICENSE) — libre de usar, adaptar y redistribuir para fines académicos e institucionales. Se agradece mencionar la fuente original.

---

*AnalisisCuant v1.0 · Procesamiento 100% local · ES/EN*
