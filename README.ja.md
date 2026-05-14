# chart-bar

依存関係のない、レスポンシブな棒グラフのWebコンポーネント。

## デモ
[Webデモ](https://code4fukui.github.io/chart-bar/)

## 特徴
- **Webコンポーネント:** HTML内で直接 `<chart-bar>` タグとして使用可能。
- **レスポンシブ:** コンテナに合わせて自動的にリサイズ。
- **柔軟なデータ対応:** JavaScriptオブジェクト、配列、インラインCSV、または外部CSVファイルからデータを読み込み可能。
- **ゼロ依存:** 外部のセットアップが不要な単一のESモジュール。

## 使い方

### 1. Webコンポーネントとして（CSVから）

モジュールをインポートし、HTML内で直接 `<chart-bar>` タグを使用します。標準のCSSでサイズをスタイリングできます。

#### `src` 属性を使用して外部CSVファイルから読み込む:
```html
<script type="module" src="https://code4fukui.github.io/chart-bar/chart-bar.js"></script>

<chart-bar 
  src="https://code4fukui.github.io/discovery_datagojp/data/data_go_jp_format.csv" 
  style="width: 100%; height: 30vh;">
</chart-bar>
```

#### インラインのCSVコンテンツから読み込む:
```html
<script type="module" src="https://code4fukui.github.io/chart-bar/chart-bar.js"></script>

<chart-bar style="height: 400px; width: 600px;">
name,count
農林水産業,96777
行財政,47496
司法・安全・環境,44875
</chart-bar>
```

### 2. JavaScriptクラスとして（オブジェクトまたは配列から）

プログラムでチャートを作成し、追加することもできます。

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
```
