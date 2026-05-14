# d3-es

D3.jsライブラリのESモジュールラッパーであり、ビルドステップなしでモダンブラウザから直接利用できるようにします。

## 特徴

- 完全なD3.jsライブラリ（v7.7.0）を単一のESモジュールとして提供します。
- ESモジュールをサポートするブラウザにおいて、URLからの直接 `import` を可能にします。
- 公式のD3 UMD配布版をラップする、透過的なビルドプロセスを採用しています。

## 使い方

モジュールURLから `d3` オブジェクトを直接インポートします。

```js
import { d3 } from "https://code4fukui.github.io/d3-es/d3.min.js";

// 例: body要素を選択して段落を追加
d3.select("body").append("p").text("Hello from D3!");
```

## ビルド方法

このリポジトリは、公式のD3 UMDビルドを取得し、エクスポート文を追記することでESモジュールを生成します。`d3.min.js` ファイルを再現するには、以下のコマンドを実行してください。

```sh
# 1. npmから公式のd3パッケージをインストール
npm i

# 2. 事前にビルドされた圧縮版UMDファイルをコピー
cp node_modules/d3/dist/d3.min.js .

# 3. d3グローバルを取得し、ESモジュールとしてエクスポートするコードを追記
echo "const d3 = globalThis.d3;" >> d3.min.js
echo "export { d3 };" >> d3.min.js
```

## ライセンス

MIT License — 詳細は [LICENSE](LICENSE) を参照してください。
