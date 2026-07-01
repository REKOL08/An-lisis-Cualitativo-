# AnalisisCuant 📊

🇬🇧 **English** | [🇪🇸 Español](README.es.md)

**A 100% browser-based quantitative statistics tool — no backend, no install, no server.**

AnalisisCuant is a single-page web app (HTML + JS) for running quantitative statistical analysis locally. Every calculation happens directly in your browser: your data never leaves your computer.

![AnalisisCuant screenshot]([docs/screenshot.png])

---

## 🚀 Quick demo

> **[Try it live →](https://REKOL08.github.io/AnalisisCuant/)**

Or open `index.html` in any modern browser (Chrome, Firefox, Edge, Safari) and start using it immediately. No server or internet connection required.

---

## ✨ Key features

| Feature | Detail |
|---|---|
| 🔒 100% local | Your data never leaves the browser |
| 📋 Built-in templates | 8 ready-to-download CSV templates |
| 📊 Descriptive statistics | Mean, median, mode, std. deviation, skewness, kurtosis, IQR, CV |
| 📈 Normality | Approximate Shapiro-Wilk test |
| 🔗 Correlations | Pearson matrix with color-coded visualization |
| 🧪 Inferential tests | Student's t-test, Mann-Whitney, one-way ANOVA |
| 📋 Likert scale | Cronbach's alpha, overall index, per-item distribution |
| 📉 Regression | Simple linear regression with scatter plot |
| 🌐 Export | HTML (Spanish/English) and TXT |
| 📱 Responsive | Works on small screens |

---

## 🗂️ File structure

```
index.html   ← The entire app (HTML + CSS + JS in a single file)
README.md    ← This document
README.es.md ← Spanish version
LICENSE      ← MIT License
```

---

## 📖 Step-by-step guide

The app is organized into **4 steps**, accessible from the top navigation bar.

### Step 1 — Template

Before uploading data, download the template that matches your analysis type.

- **🔬 Research mode** — For academic studies, theses, and scientific research. Includes inferential tests, Likert scales, and regression.
- **📊 General data mode** — For institutional, business, or management reports. Focused on descriptives and trends.

**Research mode** offers 4 template types: Likert scale/survey, group comparison, continuous variables, categorical variables.

**General data mode** offers 4 additional templates: management indicators, time series/trends, frequency counts, cross-tabulation.

The downloaded CSV already includes correct column structure, example data you can replace, and explanatory comments (lines starting with `#`, automatically ignored on upload).

### Step 2 — Data

Upload your dataset in two ways:

- **Upload file:** drag a `.csv` or `.txt` file, or click to browse. Separator (comma, semicolon, or tab) is auto-detected.
- **Paste data:** paste directly from Excel, Google Sheets, or another source. The first row must contain column names.

After loading, you'll see a row/column count, a 5-row preview, and automatic detection of numeric (`NUM`) vs. text (`TXT`) columns.

> ⚠️ **Important:** your file must not have merged cells, formulas, or subtotal rows — raw data with headers in the first row only.

### Step 3 — Configuration

Select which variables to include, set the grouping variable (for t-tests/ANOVA), Likert scale type, significance level (α, default 0.05), and preferred inferential test (or leave on "automatic"). Fill in the study title (required) and optional metadata (institution, hypothesis, sample size, sampling technique, notes).

### Step 4 — Analysis (Results)

The report is organized into collapsible sections:

- **E1 — Descriptive statistics:** mean, median, mode, std. deviation, variance, min/max, range, CV%, quartiles, IQR, skewness, kurtosis, with automatic interpretation.
- **E2 — Distribution & normality:** approximate Shapiro-Wilk test, parametric/non-parametric recommendation, histogram.
- **E3 — Correlation matrix:** full Pearson matrix with color coding, notable pairs (|r| ≥ 0.5).
- **E4 — Inferential tests:** Student's t-test (with Cohen's d), one-way ANOVA, clear H₀ decision.
- **E5 — Likert scale analysis:** Cronbach's alpha, reliability classification, overall index, stacked bar charts per item.
- **E6 — Simple linear regression:** β₀, β₁, Pearson's r, R², standard error, scatter plot with regression line.
- **E7 — Synthesis & conclusions:** integrated summary, methodological recommendations, caution notes on numeric approximations.

---

## 💾 Exporting the report

| Button | Action |
|---|---|
| 📄 HTML (ES) | Full report in Spanish, as a self-contained webpage |
| 📄 HTML (EN) | Full report translated to English |
| 📝 TXT | Plain text version |
| 🖨 | Opens the browser print dialog |
| + New | Resets the tool for a new analysis |

Exported HTML files are **self-contained**: open them in any browser, email them, or attach them to a document with no external dependencies.

---

## 📐 CSV file rules

- ✅ First row = column headers
- ✅ One observation/participant/record per row
- ✅ Separator: comma `,`, semicolon `;`, or tab (auto-detected)
- ✅ Decimal point: `.` (e.g. `3.75`)
- ✅ Text in categorical columns (e.g. `"Bogotá"`, `"Control"`)
- ❌ No merged cells
- ❌ No total/subtotal rows
- ❌ No Excel formulas
- ❌ No extra leading/trailing spaces in cells

---

## ⚙️ Available statistical tests

| Test | Condition |
|---|---|
| Shapiro-Wilk (approx.) | Always, per numeric variable |
| Pearson's r | With ≥ 2 numeric variables |
| Welch's t-test | Grouping variable with exactly 2 groups |
| One-way ANOVA | Grouping variable with ≥ 3 groups |
| Cronbach's alpha | Likert scale configured with ≥ 2 items |
| Simple linear regression | With ≥ 2 numeric variables (uses the first two selected) |

---

## 🔒 Privacy & security

- **No data is ever sent to a server.** All processing happens locally in your browser.
- No backend, external API, or database is used.
- The only external dependencies are Google Fonts and Chart.js (loaded from CDN). For fully offline use, download and embed them in the HTML file.

---

## 🌐 Browser compatibility

| Browser | Status |
|---|---|
| Google Chrome 90+ | ✅ Recommended |
| Mozilla Firefox 88+ | ✅ Compatible |
| Microsoft Edge 90+ | ✅ Compatible |
| Safari 14+ | ✅ Compatible |
| Opera 76+ | ✅ Compatible |

---

## ⚠️ Limitations

- Shapiro-Wilk and the t/F distributions are calculated using **numerical approximations**. For formal academic publication, confirm p-values with dedicated software (R, SPSS, jamovi, STATA).
- Regression is **simple** (one predictor). Use dedicated software for multiple regression.
- Recommended sample size for inferential tests is **n ≥ 30**. Smaller samples trigger a warning in the conclusions.
- The tool does not persist data between sessions. Reloading the page requires re-uploading your data.

---

## 🛠️ Built with

- **HTML5 / CSS3 / JavaScript** — no frameworks
- **[Chart.js 4.4.1](https://www.chartjs.org/)** — interactive charts
- **[Google Fonts](https://fonts.google.com/)** — Inter + JetBrains Mono
- No Node.js, npm, or build step required

---

## 🤝 Contributing

Issues and pull requests are welcome. If you'd like to add a new statistical test, template, or translation, feel free to open an issue first to discuss the approach.

## 👤 Author

Built by **[REKOL08](https://github.com/REKOL08)**
Academic project — Bibliotecas Areandina / BIDIG
Fundación Universitaria del Área Andina

## 📄 License

Released under the [MIT License](LICENSE) — free to use, adapt, and redistribute for academic and institutional purposes. Attribution to the original source is appreciated.

---

*AnalisisCuant v1.0 · 100% local processing · ES/EN*
