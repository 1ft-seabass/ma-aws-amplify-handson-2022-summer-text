# Amplify の初期設定（既存）

このページはすでに Amplify 用の IAM ユーザーがある場合の流れです。初めて IAM ユーザーをつくる場合は [Amplify の初期設定（新規）](03-amplify-account-create.md) を進めてください。

以前、作成してメモしたアクセスキー ID とシークレットアクセスキーを準備しておきましょう。

この作業は Cloud9 のターミナルで作業を進めます。

## Amplify CLI インストール

Amplify CLI をインストールします。

```
npm install -g @aws-amplify/cli
```

こちらのコマンドをコピーアンドペーストで入力して実行して、インストールを待ちます。

![image](https://i.gyazo.com/550100bc65037a688ac59f4e08752241.png)

コピーアンドペースト時にブラウザのアドレスバーでクリップボードの許可がでてくるので許可します。これをすれば今後はペーストできます。

## Amplify 初期設定をはじめる

```
amplify configure
```

こちらのコマンドを実行します。

```
Follow these steps to set up access to your AWS account:

Sign in to your AWS administrator account:
https://console.aws.amazon.com/
Press Enter to continue
```

このようなメッセージが出てくるので Enter キーを押します。

### Specify the AWS Region

![image](https://i.gyazo.com/d7403e2a37429e460c42a32bc41a62f3.png)

リージョンは ap-northeast-1 を選択して、Enter キーを押します。

### Specify the username of the new IAM user:

![image](https://i.gyazo.com/62110af7cd533317a1a629765e6bb302.png)

Amplify のための新しい IAM ユーザーの名前を決まりますが、すでにユーザーがあるので気にせず、Enter キーを押して進めます。

### Complete the user creation using the AWS console

リージョンと IAM ユーザの名前が決まったので、ブラウザ上の AWS コンソールで実際に作成する URL が案内されました。

![image](https://i.gyazo.com/968760e7cc5cae519c53185d46435e41.png)

今回はすでにユーザーのアクセスキー ID とシークレットアクセスキー持っているので、このまま Cloud9 のターミナルで進めます。（ユーザーを作りません）

Enter キーを押して進めます。

### アクセスキー ID をコピーアンドペーストして入力

![image](https://i.gyazo.com/5f266f1e0eb94cfa90ab87b43c2d89cc.png)

Amplify のための新しい IAM ユーザーのアクセスキーを聞かれるので、メモしたものを入力します。コピーアンドペーストできます。

まず、アクセスキーをコピーします。

![image](https://i.gyazo.com/39bac5ee793c19d9e3a1b23bc2dd4b78.png)

ターミナルで右クリックで Paste を選びましょう。

![image](https://i.gyazo.com/64a046c31ef147a2bab0c683f7ec0afa.png)

ペーストするとこのように＊＊＊＊＊となります。

Enter キーを押します。

### シークレットアクセスキーをコピーアンドペーストして入力

![image](https://i.gyazo.com/636916da111dbba008e6606f0dfaca97.png)

Amplify のための新しい IAM ユーザーのシークレットアクセスキーを聞かれるので、メモしたものを入力します。コピーアンドペーストできます。

![image](https://i.gyazo.com/2b907045a97f075eb110962d4880edf0.png)

入力できたら Enter キーを押します。

### プロファイル名の設定

この Cloud9 のローカルのプロファイル名を指定が聞かれます。

デフォルトのままで OK なので、 Enter キーを押します。

![image](https://i.gyazo.com/731f1a2ec7aa061fc1a7b765703721ab.png)

Successfully set up the new user. とでて、この Cloud9 での Amplify 初期設定は完了です！

「Amplify のベース作成」へ進みます。
