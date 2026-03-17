# AnomalyDetect Pro 🔍

**Intelligent Real-Time Data Anomaly Detection Engine**

A fully client-side, interactive anomaly detection web application built with pure JavaScript, Chart.js, and a modern dark glassmorphism UI. No backend required — all processing happens in the browser.

---

## 🚀 Features

### ✅ Data Input
- **Sample Datasets**: 4 built-in datasets (IoT Sensor, Financial Prices, Network Traffic, ECG Signal) — auto-loads on startup
- **CSV/JSON Upload**: Drag & drop or click to upload files; auto-detects columns
- **Manual Entry**: Paste comma-separated numeric values directly

### ✅ Anomaly Detection Algorithms
| Algorithm | Method |
|---|---|
| **Z-Score** | Standard deviation-based outlier detection |
| **IQR** | Interquartile range fencing |
| **Moving Average** | Rolling window with dynamic threshold bands |
| **Isolation Forest** | Tree-based isolation score simulation |
| **DBSCAN** | 1D density-based clustering outlier detection |

### ✅ Interactive Visualization
- Line, Scatter, and Bar chart types
- Anomalies highlighted with red triangles + rich tooltips
- Confidence bands (upper/lower bounds)
- Moving average overlay line
- Zoom (mouse wheel) and pan (drag) with reset button
- Fullscreen mode

### ✅ Results Dashboard
- Total data points, anomaly count & percentage
- Mean / Std Dev, Min / Max statistics
- Sortable anomaly table (index, value, score, severity, deviation)
- Severity doughnut chart (High / Medium / Low breakdown)
- Processing time, algorithm, and threshold metadata

### ✅ Settings & Configuration
- **Sensitivity / Threshold** slider (0.5 – 5.0)
- **Window Size** for Moving Average (2 – 50)
- **Contamination Rate** for Isolation Forest & DBSCAN (1% – 25%)
- **Chart Type** selector (Line / Scatter / Bar)
- Toggles: Show Confidence Band, Show Moving Average, Auto Re-run

### ✅ Export
- **Export CSV** — downloads anomaly list with index, value, score, severity
- **Export PNG** — downloads current chart as a high-resolution image

---

## 📁 Project Structure

```
index.html             Main application page
css/
  style.css            Dark glassmorphism stylesheet
js/
  data.js              Sample data generators + all 5 detection algorithms
  algorithms.js        Algorithm shim (reserved for extensions)
  charts.js            Chart.js rendering module (main + severity charts)
  app.js               Application controller (UI, state, interactions)
```

---

## 🎯 Entry Points

| Path | Description |
|---|---|
| `/` or `/index.html` | Main application (auto-loads sensor data + runs detection) |

---

## ⌨️ Keyboard Shortcut

| Shortcut | Action |
|---|---|
| `Ctrl/Cmd + Enter` | Run detection |

---

## 🛠️ Tech Stack

- **HTML5** — Semantic structure
- **CSS3** — Custom glassmorphism dark theme, CSS variables, animations
- **Vanilla JavaScript (ES6+)** — All logic, no frameworks
- **[Chart.js 4.x](https://www.chartjs.org/)** — Main chart + doughnut chart
- **[chartjs-plugin-zoom](https://www.chartjs.org/chartjs-plugin-zoom/)** — Zoom & pan
- **[Font Awesome 6](https://fontawesome.com/)** — Icons
- **[Google Fonts](https://fonts.google.com/)** — Inter + JetBrains Mono

---

## 🔮 Recommended Next Steps

- Add multi-variate anomaly detection (2D/3D datasets)
- Add time-range filter / date picker for labeled timestamps
- Implement real DBSCAN and Isolation Forest with WASM-compiled ML library
- Add threshold annotation drawing on chart
- Add history of detection runs with comparison view
- Support streaming/real-time data via WebSocket
- Add dark/light theme toggle

---

## 📊 Data Models

All processing is in-memory (no persistence):

```js
// Raw data state
{ values: number[], labels: string[], name: string, unit: string }

// Detection result
{
  anomalies: [{ index, value, score, severity, deviation }],
  scores:    number[],
  metadata:  { mean, std, upperBound, lowerBound, threshold, algorithm, ... }
}
```

---

*Built with ❤️ as a static frontend application — no backend required.*
