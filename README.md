# chart-bar

> 日本語のREADMEはこちらです: [README.ja.md](README.ja.md)

A zero-dependency, responsive bar chart Web Component.

## Demo
[Web demo](https://code4fukui.github.io/chart-bar/)

## Features
- **Web Component:** Use directly in your HTML as a `<chart-bar>` tag.
- **Responsive:** Automatically resizes to fit its container.
- **Flexible Data:** Load data from a JavaScript object, an array, an inline CSV, or an external CSV file.
- **Zero-Dependency:** A single ES module with no external setup required.

## Usage

### 1. As a Web Component (from CSV)

Import the module and use the `<chart-bar>` tag directly in your HTML. You can style its dimensions with standard CSS.

#### Load from an external CSV file via `src` attribute:
```html
<script type="module" src="https://code4fukui.github.io/chart-bar/chart-bar.js"></script>

<chart-bar 
  src="https://code4fukui.github.io/discovery_datagojp/data/data_go_jp_format.csv" 
  style="width: 100%; height: 30vh;">
</chart-bar>
```

#### Load from inline CSV content:
```html
<script type="module" src="https://code4fukui.github.io/chart-bar/chart-bar.js"></script>

<chart-bar style="height: 400px; width: 600px;">
name,count
農林水産業,96777
行財政,47496
司法・安全・環境,44875
</chart-bar>
```

### 2. As a JavaScript Class (from Object or Array)

You can also create and append the chart programmatically.

```html
<div id="chart-container" style="width: 500px; height: 300px;"></div>

<script type="module">
  import { ChartBar } from "https://code4fukui.github.io/chart-bar/chart-bar.js";

  const data = {
    "A": 30,
    "B": 20,
    "C": 70,
  };
  const chart = new ChartBar(data);
  document.getElementById("chart-container").appendChild(chart);
</script>