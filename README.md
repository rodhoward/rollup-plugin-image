# rollup-plugin-image

Import JPG, PNG, GIF and SVG files.

Main change is to not create an Image object but just a base64 encoded string.

## Installation

```bash
npm install --save-dev rollup-plugin-image-src
```

## Usage

```js
// rollup.config.js
import image from "rollup-plugin-image-src";

export default {
  entry: "src/index.js",
  dest: "dist/my-lib.js",
  plugins: [image()]
};
```

You can now use images in your bundle like so:

```js
import logo from "./rollup.png";

// using js
document.body.appendChild(new Image(logo));

// or
// using e.g. vue assign the logo directly to an image src.
<img :src="logo" style="width: 20rem;" />
```

Images are encoded using base64, which means they will be 33% larger than the size on disk. You should therefore only use this for small images where the convenience of having them available on startup (e.g. rendering immediately to a canvas without co-ordinating asynchronous loading of several images) outweighs the cost.

## License

MIT
