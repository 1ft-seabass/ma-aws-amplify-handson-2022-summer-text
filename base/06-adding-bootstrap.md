# Bootstrap の導入

CSS フレームワーク Bootstrap を導入してみましょう。

## Bootstrap

Bootstrap は Web サイトのメジャーなパーツを手軽に作ることができ、今回のハッカソンのような場で自分のチームの仕組みを作るときに、CSS や HTML を悩まずにある程度のクオリティでつくることができます。

公式サイト https://getbootstrap.jp/ にはドキュメントも豊富で、ほぼここだけの情報でもいろいろな仕組みを作ることができます。もちろん、Qiita や Google 検索で調べても文献がいろいろあるので助けになることでしょう。

## 参考文献

Node-RED と Vue 3 が連携したプロジェクトに初期表示のコンポーネントと Bootstrap を導入するメモ – 1ft-seabass.jp.MEMO
https://www.1ft-seabass.jp/memo/2021/09/02/node-red-and-vue3-and-bootstrap-collaboration-basic/

私の記事ですがこちらの記事を元に進めていきます。

## Bootstrap 関連のモジュールインストール

aws-amplify-vite-and-vue3-my-template フォルダをベースに進めます。

```
npm i bootstrap @popperjs/core
```

このコマンドを実行します。

## src/main.js を編集

src/main.js を以下のように編集して保存します。

```js
import { createApp } from 'vue'
// import './style.css'
import App from './App.vue'

// Bootstra
import 'bootstrap'
import 'bootstrap/dist/css/bootstrap.css'

// Amplify Add
import { Amplify } from 'aws-amplify';
import awsExports from './aws-exports';
Amplify.configure(awsExports);

createApp(App).mount('#app')

```

具体的には、

```js
// Bootstrap
import 'bootstrap'
import 'bootstrap/dist/css/bootstrap.css'
```

が加わり、以前からの CSS 設定の `import './style.css'` をコメントアウトしました。

### src/App.vue 上書き

src/App.vue を以下のプログラムで上書きして保存します。

```html
<script setup>

</script>

<template>
  <div class="container">
    <div class="row">
      <div class="col m-5 text-center">
        <img src="./assets/vue.svg" width="250" class="logo vue" alt="Vue logo" />
      </div>
    </div>
    <div class="row">
      <div class="col m-3 text-center">
        説明文説明文説明文説明文説明文説明文説明文説明文説明文説明文説明文説明文説明文説明文説明文説明文説明文説明文説明文説明文
      </div>
    </div>
    <div class="row">
      <div class="col m-1">
        <h3>入力フォームサンプル</h3>
      </div>
    </div>
    <div class="row">
      <div class="col m-1">
        <label for="exampleFormControlTextarea1" class="form-label">テキストエリアサンプル</label>
        <textarea class="form-control" id="exampleFormControlTextarea1" rows="3"></textarea>
      </div>
    </div>
    <div class="row">
      <div class="col m-1">
        <button type="button" class="btn btn-primary">ボタン</button>
      </div>
    </div>
    <div class="row">
      <div class="col m-1">
        <select class="form-select" aria-label="Default select example">
          <option selected>メニュー選択</option>
          <option value="1">春</option>
          <option value="2">夏</option>
          <option value="3">秋</option>
          <option value="4">冬</option>
        </select>
      </div>
    </div>
    <div class="row">
      <div class="col m-1">
        <h3>リストサンプル</h3>
      </div>
    </div>
    <div class="row">
      <div class="col m-1">
        <ul class="list-group">
          <li class="list-group-item">リストアイテム1</li>
          <li class="list-group-item">リストアイテム2</li>
          <li class="list-group-item">リストアイテム3</li>
          <li class="list-group-item">リストアイテム4</li>
          <li class="list-group-item">リストアイテム5</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>
```

## 手元で実行してみる

確認してみましょう。

```
npm run dev
```

で手元の開発サーバーを起動して、Preview の操作で見てみましょう。

![image](https://i.gyazo.com/68e7df4a4d32c9f9ec8999ca907b4a20.png)

Bootstrap によって、比較的簡単な記述で、フォームパーツやロゴや文字などが、整った見た目で配置されます。

その他のレイアウトについては、こちらを参考にしてみてください。

はじめに · Bootstrap v5.0
https://getbootstrap.jp/docs/5.0/getting-started/introduction/