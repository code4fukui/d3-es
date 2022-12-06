# d3-es

## Usage

```js
import { d3 } from "https://code4fukui.github.io/d3-es/d3.min.js";
```

## How to Build

```sh
npm i
cp node_modules/d3/dist/d3.min.js .
echo "const d3 = globalThis.d3;" >> d3.min.js
echo "export { d3 };" >> d3.min.js
```
