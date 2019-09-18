# webpack-author-libraries

webpack でライブラリ用のビルドをする。以下を参考。

[Authoring Libraries](https://webpack.js.org/guides/author-libraries/)

## どうすればライブラリ用のビルドができるのか？

`webpack.config.js`を以下の感じにすればOK。

```js
const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'webpack-numbers.js',
    // バンドルを読み込めば window.webpackNumbers でアクセスできるようになる
    library: 'webpackNumbers',
    // ライブラリの公開方法、今回は widnow からアクセスしたいため、'window'を指定
    libraryTarget: 'window'
  }
};
```
