# d3-es

> 日本語のREADMEはこちらです: [README.ja.md](README.ja.md)

An ES module wrapper for the D3.js library, allowing for direct use in modern browsers without a build step.

## Features

-   Provides the complete D3.js library (v7.7.0) as a single ES module.
-   Enables direct `import` from a URL in browsers that support ES modules.
-   Transparent build process that wraps the official D3 UMD distribution.

## Usage

Import the `d3` object directly from the module URL.

```js
import { d3 } from "https://code4fukui.github.io/d3-es/d3.min.js";

// Example: Select the body and append a paragraph
d3.select("body").append("p").text("Hello from D3!");
```

## How to Build

This repository generates the ES module by taking the official D3 UMD build and appending an export statement. To replicate the `d3.min.js` file, run the following commands:

```sh
# 1. Install the official d3 package from npm
npm i

# 2. Copy the pre-built, minified UMD file
cp node_modules/d3/dist/d3.min.js .

# 3. Append lines to capture the d3 global and export it as an ES module
echo "const d3 = globalThis.d3;" >> d3.min.js
echo "export { d3 };" >> d3.min.js
```

## License

MIT License — see [LICENSE](LICENSE).