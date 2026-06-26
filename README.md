# AnalisisCuant

Herramienta web de **análisis estadístico cuantitativo** que funciona 100 % en el navegador, sin servidor ni instalación. Pensada para investigación académica (artículos, tesis, ALFIN) y para reportes de gestión institucional.

Un solo archivo HTML: `AnalisisCuant.html`. Lo abres con doble clic y ya está.

---

## Características

- **Dos modos de trabajo:**
  - 🔬 **Investigación** — estadística descriptiva e inferencial completa para estudios formales.
  - 📊 **Datos generales** — resúmenes y descriptivos para informes institucionales o de gestión.
- **8 plantillas CSV descargables** según el tipo de datos (Likert, comparación de grupos, variables continuas, categóricas, indicadores, series, frecuencias, tabla cruzada).
- **Carga flexible:** subir archivo CSV/TXT, arrastrar y soltar, o pegar los datos directamente.
- **Detección automática** de columnas numéricas y de la variable de agrupación.
- **Informe por secciones plegables** con tarjetas de estadísticos, tablas, interpretaciones en lenguaje natural y gráficas (Chart.js).
- **Exportación** a HTML (español e inglés), TXT e impresión/PDF.
- **Privacidad total:** los datos nunca salen del navegador.

---

## Cómo usarlo

El flujo tiene 4 pasos, visibles en la barra superior:

1. **Plantilla** — elige el modo y el tipo de datos. Descarga la plantilla CSV de ejemplo y reemplaza los datos con los tuyos.
2. **Cargar datos** — sube o pega tu CSV. Verás una vista previa y las columnas detectadas como numéricas (NUM) o texto (TXT).
3. **Configuración** — selecciona qué variables analizar, la variable de agrupación (para comparar grupos), el tipo de escala Likert, el nivel de significancia (α) y los metadatos del estudio. El título es obligatorio.
4. **Análisis** — ejecuta y consulta el informe. Desde aquí exportas o empiezas uno nuevo.

---

## Formato de los datos

Reglas generales del archivo CSV:

- La **primera fila** son los encabezados (nombres de las variables).
- **Una fila por caso** (un participante, un registro, un periodo).
- Para columnas numéricas, usa **punto** como separador decimal y no dejes celdas vacías.
- Las **categorías de texto** deben escribirse exactamente igual en todas las filas (`Bogotá` ≠ `bogota`).
- El separador puede ser coma, punto y coma o tabulación (se detecta solo).
- Las líneas que empiezan con `#` se ignoran (sirven como comentarios o instrucciones).

Ejemplo (plantilla Likert):

```
id,grupo,item1,item2,item3,item4
1,A,4,5,3,4
2,A,5,5,4,5
3,B,3,3,4,3
```

Cada plantilla incluye sus propias reglas en pantalla y datos de ejemplo listos para reemplazar.

---

## Análisis incluidos

| Sección | Contenido |
|---|---|
| **E1 · Descriptiva** | Media, mediana, moda, desviación estándar, varianza, mínimo, máximo, rango, cuartiles, IQR, coeficiente de variación, asimetría y curtosis. |
| **E2 · Distribución** | Histograma y prueba de normalidad (Shapiro-Wilk aproximado) con recomendación de prueba paramétrica vs. no paramétrica. |
| **E3 · Correlaciones** | Matriz de Pearson con código de color y detección de pares con asociación notable (\|r\| ≥ 0.5). |
| **E4 · Inferenciales** | Prueba t de Student (dos grupos) con tamaño del efecto (d de Cohen), y ANOVA de un factor (tres o más grupos). |
| **E5 · Likert** | Alfa de Cronbach (fiabilidad), índice general del instrumento y distribución de respuestas por ítem. |
| **E6 · Regresión** | Regresión lineal simple con β₀, β₁, r, R², error estándar y diagrama de dispersión con recta ajustada. |
| **E7 · Conclusiones** | Síntesis de hallazgos y recomendaciones metodológicas automáticas. |

---

## ⚠️ Sobre los p-valores

Las pruebas inferenciales (t, ANOVA, normalidad) usan **aproximaciones numéricas** de las distribuciones estadísticas, no las tablas exactas. Esto mantiene la app ligera y sin dependencias pesadas, pero significa que:

- Los **p-valores son orientativos**, útiles para exploración y docencia.
- Para resultados destinados a **publicación o evaluación formal**, confirma los valores con software estadístico estándar (R, SPSS, jamovi, JASP).

La herramienta deja esta advertencia explícita en la sección de conclusiones de cada informe.

---

## Exportación

Desde el panel de resultados:

- **HTML (ES)** y **HTML (EN)** — informe autónomo con estilos incluidos. La versión EN traduce los títulos principales.
- **TXT** — versión en texto plano para pegar en otros documentos.
- **🖨** — imprime o guarda como PDF desde el diálogo del navegador.

---

## Privacidad

Todo el procesamiento ocurre en tu navegador. No hay backend, no se sube nada a ningún servidor y no se guarda información entre sesiones. La única conexión externa es la carga de la librería de gráficas (Chart.js) y las fuentes, desde un CDN público.

---

## Requisitos técnicos

- Cualquier navegador moderno (Chrome, Edge, Firefox, Safari).
- Conexión a internet la primera vez, para cargar Chart.js y las fuentes desde el CDN. *(Si necesitas uso totalmente offline, se pueden incrustar esas librerías en el archivo.)*
- Sin instalación, sin dependencias locales, sin cuenta.

---

## Limitaciones conocidas

- En el menú de configuración aparecen **Mann-Whitney U** y **Chi-cuadrado** como opciones, pero el motor de cálculo todavía **no las ejecuta**: actualmente corre prueba t, ANOVA, correlaciones y regresión. *(Pendiente de implementar.)*
- La regresión es **lineal simple** (una variable predictora); no hay regresión múltiple.
- La prueba de normalidad es una **aproximación**, no el Shapiro-Wilk exacto.
- No maneja valores faltantes de forma avanzada: las celdas no numéricas simplemente se excluyen del cálculo de cada columna.

---

*AnalisisCuant · v1.0 — herramienta local de análisis cuantitativo.*
