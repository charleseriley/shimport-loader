# shimport-loader

Webpack loader that replaces import() with shimport() https://www.npmjs.com/package/shimport

### Usage

Include the shimport script to create the global var `__shimport__`.

E.g.,
```html
<script src="https://unpkg.com/shimport"></script>
```

Then use the `shimport-loader` in the webpack config.

```js
// in webpack.config.js
...
module: {
  rules: [
    {
      test: /\.m?js$/,
      exclude: /(node_modules|bower_components)/,
      use: {
        loader: 'shimport-loader'
      }
    }
  ]
}
```

^ will replace the dynamic `import()` expressions with `__shimport__.load()` expressions.
