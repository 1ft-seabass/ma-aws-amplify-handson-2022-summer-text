## Auth 機能の追加

Amplify 認証機能を加えてみましょう。

Tutorial - Add authentication - Vue - AWS Amplify Docs
https://docs.amplify.aws/start/getting-started/auth/q/integration/vue/

こちらの文献を参考にして進めます。

## Auth 機能の追加

```
amplify add auth
```

コマンドを実行します。

###  Do you want to use the default authentication and security configuration? (Use arrow keys)

Default configuration を選択して Enter キーを押します。

Warning: you will not be able to edit these selections. 

### How do you want users to be able to sign in?

Username を選択して Enter キーを押します。 

### Do you want to configure advanced settings?

No, I am done. を選択して Enter キーを押します。 

## amplify push

手元で設定ができたのでクラウドの Amplify に反映します。

```
amplify push
```

を実行します。 

![image](https://i.gyazo.com/e0b938ba8e263ef80a8a8c110f0bf091.png)

Auth が登場し Create になっていることを確認して、`Are you sure you want to continue?` と聞かれたら Y を入力して Enter キーを押します。 

![image](https://i.gyazo.com/a985591141bce79ced5312fc0288ce4c.png)

しばらく設定が進行します。

```
✔ All resources are updated in the cloud
```

となったら作成完了です。

## ユーザーを設定しておく

ユーザーは Amplify コンソールの画面で設定します。

```
amplify console
```

このコマンドを実行すると、今回の Amplify のコンソール画面のページの URL を教えてくれます。

### ✔ Which site do you want to open?

AWS console を選択して Enter キーを押すと URL が表示されます。

![image](https://i.gyazo.com/12b1f5440d6fb87bdbfdc5de04dd5454.png)

URL をクリックして Open を押します。

![image](https://i.gyazo.com/5f00116e2773d3d3d390b9d575fa6a9a.png)

Amplify コンソールが表示されます。

![image](https://i.gyazo.com/3224605cbd7ea71240797ad91b3b032b.png)

認証をクリックします。

![image](https://i.gyazo.com/6d8610d0170dbab6e18ca87a626245b8.png)

Cognito で表示をクリックします。

![image](https://i.gyazo.com/c39f5305e2535fbe8a0c2725e7da34f7.png)

うまくリージョンが移動できない場合は、今回のリージョン　東京　を選択します。

![image](https://i.gyazo.com/d6b3f0184449fbf4ca866c0f3c87d662.png)

それでも出てこない場合は、

![image](https://i.gyazo.com/650a3c0fbcd86b26ebc2fda04f165620.png)

右上のリージョンから東京を選びます。この場合、一覧に戻ってしまい、今回のものが探しにくいので、再度 Amplify コンソールに戻って、

![image](https://i.gyazo.com/6d8610d0170dbab6e18ca87a626245b8.png)

認証から Cognito で表示をクリックします。

![image](https://i.gyazo.com/a76018d2baf30b451231788686b6fa02.png)

Cognito ページに移動できました。

![image](https://i.gyazo.com/e5d3529626685e8b996beb5d5b095a07.png)

左メニューから、ユーザとグループをクリックします。

![image](https://i.gyazo.com/cc6cdd51a25340d11f0a49798e67b706.png)

ユーザータブであることを確認して、ユーザーの作成ボタンをクリックします。

![image](https://i.gyazo.com/16110135c78ff76487756c9f413a9c0a.png)

- ユーザー名
    - 任意の英数字の名前
- 仮パスワード
    - 任意のパスワード
- 電話番号
    - 入力しない
- 電話番号を検証済みにしますか
    - チェックを外す
- Eメール
    - ログインで使用する E メール

設定できたら、ユーザーの作成ボタンをクリックします。

![image](https://i.gyazo.com/54ad30fab1e9b988984962a59ee8d9eb.png)

ユーザーが作られたことを確認します。ユーザー名、仮パスワード、Eメールを忘れないようにメモしておきましょう。

## 表示側にログイン UI をつける

ログイン UI は Amplify の仕組みととても密着しているものです。ですので Amplify Ui というモジュールで構成されています。

Amplify UI - Build UI fast with Amplify on Vue
https://ui.docs.amplify.aws/?platform=vue

今回はクローン最初の npm i のインストールで、このあたりの `"@aws-amplify/ui-vue` も一緒に入ってるのですぐ使えます。

### src/App.vue の変更

src/App.vue を以下のプログラムで上書きして保存します。

```html
<script setup>

import '@aws-amplify/ui-vue/styles.css';
import { Authenticator, useAuthenticator } from '@aws-amplify/ui-vue';

const auth = useAuthenticator();

</script>

<template>
  <div class="container">
    <div class="row">
      <div class="col m-3 text-center">
        <h1>ログインシステム</h1>
      </div>
    </div>
    <div class="row">
      <div class="col m-3 text-center">
        <template v-if="auth.route === 'authenticated'">
          こんにちは！ {{ auth.user?.username }} さん <button type="button" class="btn btn-primary" @click="auth.signOut">サインアウト</button>
        </template>
      </div>
    </div>
    <div class="row">
      <div class="col m-3">
        <authenticator hideSignUp></authenticator>
        <template v-if="auth.route === 'authenticated'">
          ログインの時に見えるエリア
        </template>
      </div>
    </div>
  </div>
</template>
```

## 手元で実行してみる

確認してみましょう。

```
npm run dev
```

で手元の開発サーバーを起動して、Preview の操作で見てみましょう。

![image](https://i.gyazo.com/8e2e8545f9beabf1841cc7022e87958d.png)

このようにログイン画面が表示されます。先ほど作ったユーザーのユーザー名と仮パスワードを入力します。（今回 E メールは必要ありません）

![image](https://i.gyazo.com/57bed19e585a4232a7c69315c053dfa8.png)

Change Password と出て、正式なパスワードを入力して Change Password ボタンをクリックします。

![image](https://i.gyazo.com/042dec31530fee732a97f46d8d526a9d.png)

正式なパスワード設定と同時に、ログインできます。

すると、ログインの時に見えるアリアであったり、ユーザへのあいさつの部分が動作しています。このように、ログインしたユーザーにだけコンテンツを表示する仕組みもすぐに作ることができます。

## 新しくユーザーを作りたくなったら？

さきほどの AWS Cognito でユーザーの作成を行います。
