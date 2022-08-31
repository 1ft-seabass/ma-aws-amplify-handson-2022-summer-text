# 環境の削除

今回使った Cloud9 と Amplify アプリを削除します。

## Amplify アプリの削除

Cloud9 のコンソールで、以下のコマンドを実行します。

```
amplify delete
```

今回の Amplify アプリに関係する環境を丸ごと削除する強力なコマンドです。

```
Are you sure you want to continue? This CANNOT be undone. (This will delete all the environments of the project from the cloud and wipe out all the local files created by Amplify CLI)
```

と出るので Yes を入力して Enter キーを押して削除します。

削除できたら AWS コンソール上でも Amplify アプリが削除されたか確認しておきましょう。

## Cloud9 の削除

今回のハンズオンで使った Cloud9 を削除します。

![image](https://i.gyazo.com/3094017a352f16f501f13f965bcd809a.png)

Cloud9 の一覧から今回の Cloud9 を右上のチェックをクリックして選択します。

![image](https://i.gyazo.com/763344a661856dd564a2baf9cd9b6dc8.png)

Delete ボタンをクリックします。

![image](https://i.gyazo.com/c1d11588dafdb006ca6c8cc8a78aa2ba.png)

本当に削除するか聞かれるので入力欄に Delete を入力して Delete をクリックします。

削除できたら一覧から削除されていることも確認しましょう。

おつかれさまでした。このあとは、時間があれば、質疑応答やフォローを行っていく予定です。

## 参考：何もかも消す場合はこちら

このあと、ハッカソンで使っていくので Amplify アカウントや、それにともなうディープな削除は行いませんが、削除したくなった場合は、以下を参考に対応してみてください。

- [環境削除｜AWS Amplify Studio + Figmaハンズオン](https://zenn.dev/shigeru_oda/books/521fa5a5a9c558c6275d/viewer/delete)