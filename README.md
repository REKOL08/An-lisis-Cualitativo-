# AnálisisCual

**Herramienta de análisis cualitativo estructurado para investigadores.**  
Sin API. Sin servidor. Sin costo. Todo ocurre en tu navegador.

🔗 **Demo:** `https://[tu-usuario].github.io/[nombre-del-repo]`

---

## ¿Qué hace?

AnálisisCual toma tus datos cualitativos en texto plano (entrevistas, notas de campo, documentos, corpus mixtos) y genera un **informe estructurado en 8 fases metodológicas**, siguiendo los estándares de la investigación cualitativa rigurosa:

| Fase | Descripción |
|------|-------------|
| 1 | Organización e inventario del corpus |
| 2 | Codificación de datos con frecuencia |
| 3 | Categorización y construcción de subcategorías |
| 4 | Interpretación de hallazgos |
| 5 | Relación con el marco teórico |
| 6 | Uso de evidencias y citas textuales |
| 7 | Evaluación del rigor científico (credibilidad, transferibilidad, dependabilidad, confirmabilidad) |
| 8 | Presentación de resultados y conclusiones |

---

## Inicio rápido

### 1. Clonar o descargar

```bash
git clone https://github.com/[tu-usuario]/[nombre-del-repo].git
```

O descarga el archivo `index.html` directamente y ábrelo en tu navegador.

### 2. Publicar en GitHub Pages

1. Sube `index.html` a la raíz de tu repositorio
2. Ve a **Settings → Pages**
3. En *Source*, selecciona `Deploy from a branch`
4. Selecciona la rama `main` y la carpeta `/ (root)`
5. Haz clic en **Save**

La herramienta quedará disponible en:
```
https://[tu-usuario].github.io/[nombre-del-repo]
```

---

## Cómo usar la herramienta

### Paso 1 — Elige la plantilla adecuada

La herramienta ofrece 4 tipos de plantilla según tu fuente de datos:

| Tipo | Cuándo usarlo |
|------|---------------|
| **Entrevista / Transcripción** | Diálogos con participantes, grupos focales, historias de vida |
| **Notas de campo / Observación** | Etnografía, observación participante, diarios de campo |
| **Análisis documental** | Políticas, actas, informes, archivos institucionales |
| **Múltiples fuentes / Mixto** | Combinación de entrevistas + observación + documentos |

Descarga la plantilla, llénala con tus datos y guárdala como `.txt` o `.md`.

### Paso 2 — Estructura tu archivo según la plantilla

Cada tipo de plantilla tiene una estructura específica. El campo más importante es el **identificador de participante**, que permite al sistema extraer actores y citas:

```
P1: Cuando me dijeron que debía incorporar IA en mis clases, lo primero que sentí fue pánico.
E:  ¿Y cómo resolvió esa situación?
P1: Me apoyé en colegas más jóvenes. Fue un aprendizaje entre pares.
```

Los identificadores válidos son: `P1:`, `P2:`, `E:` (entrevistador), `A1:`, `A2:` (actores en observación), `DOCENTE:`, etc.  
Para documentos, usa `[CITA]` antes de los fragmentos textuales clave.

### Paso 3 — Carga el archivo y define el contexto

- Arrastra uno o más archivos `.txt` / `.md` a la zona de carga
- El sistema valida automáticamente que el archivo tenga la estructura correcta
- Completa la pregunta de investigación, objetivos, marco teórico y metodología

### Paso 4 — Ejecuta el análisis y exporta

El análisis se ejecuta localmente en tu navegador. Al finalizar puedes:
- Ver el informe completo por fases, expandibles y colapsables
- Exportar en **HTML** (informe visual navegable)
- Exportar en **TXT** (texto plano para edición)
- **Imprimir** directamente con estilos limpios

---

## Estructura del repositorio

```
/
├── index.html       # Aplicación completa (una sola página)
└── README.md        # Este archivo
```

No se requieren dependencias, build tools, ni Node.js. Un solo archivo HTML es suficiente.

---

## Requisitos técnicos

| Requisito | Detalle |
|-----------|---------|
| Navegador | Chrome 90+, Firefox 88+, Edge 90+, Safari 14+ |
| Conexión a internet | Solo para cargar las fuentes tipográficas (Google Fonts). El análisis es 100% offline. |
| API key | No se requiere ninguna |
| Backend | No existe — todo es frontend puro |

---

## Privacidad

> Tus datos nunca salen de tu navegador.

El procesamiento ocurre completamente en el cliente. Ningún archivo, texto o resultado se envía a ningún servidor externo. La herramienta no usa cookies, no registra sesiones y no almacena información.

---

## Códigos de análisis incluidos

El motor detecta automáticamente los siguientes patrones en el corpus:

| Código | Dimensión |
|--------|-----------|
| `RESIST_CAMBIO` | Resistencia al cambio |
| `APREND_AUTOPROPULSADO` | Aprendizaje autónomo |
| `APOYO_INSTITUCIONAL` | Apoyo institucional |
| `COMPET_DIGITAL` | Competencia digital |
| `EXPERIENCIA_POSITIVA` | Experiencia positiva |
| `BRECHA_GENERACIONAL` | Brecha generacional |
| `IMPACTO_PEDAGÓGICO` | Impacto pedagógico |
| `IDENTIDAD_PROFESIONAL` | Identidad y rol profesional |
| `CONTEXTO_INSTITUCIONAL` | Contexto institucional |
| `COMUNICACION_PARES` | Comunicación entre pares |
| `TIEMPO_RECURSO` | Tiempo y recursos |
| `EMOCIONES` | Emociones y afectos |

Estos códigos están pensados para investigaciones en educación, ciencias sociales y humanidades. El sistema mide la frecuencia de cada código en el corpus y lo clasifica como `alta`, `media` o `baja`.

---

## Rigor científico evaluado

La herramienta evalúa automáticamente cuatro criterios de Lincoln y Guba (1985):

- **Credibilidad:** ¿Los hallazgos reflejan adecuadamente la realidad estudiada?
- **Transferibilidad:** ¿Es posible aplicar los resultados en contextos similares?
- **Dependabilidad:** ¿El proceso investigativo es consistente y reproducible?
- **Confirmabilidad:** ¿Los resultados se fundamentan en los datos y no en sesgos del investigador?

Cada criterio recibe un nivel (`alto`, `medio`, `bajo`) con justificación basada en las características reales del corpus cargado.

---

## Limitaciones

- El análisis es **orientador**, no sustituto del juicio del investigador. Los resultados deben ser revisados, validados e interpretados por el investigador.
- El motor de codificación usa búsqueda de términos en español. Corpus en otros idiomas requerirán adaptación.
- Archivos muy extensos (más de 200.000 caracteres por fuente) se procesan parcialmente.
- Los formatos aceptados son únicamente `.txt` y `.md`. Para documentos Word o PDF, exporta primero a texto plano.

---

## Créditos

Desarrollado como herramienta de apoyo a la investigación cualitativa.  
Construido con HTML, CSS y JavaScript puro — sin frameworks, sin dependencias.  
Tipografía: [Inter](https://fonts.google.com/specimen/Inter) + [Lora](https://fonts.google.com/specimen/Lora) vía Google Fonts.

---

## Licencia

MIT — libre para usar, modificar y distribuir con atribución.
