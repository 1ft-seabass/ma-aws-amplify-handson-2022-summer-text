# 環境の削除

今回使った Cloud9 と Amplify アプリを削除します。

## Cloud9 の料金

Cloud9 の料金はこちらです。

https://aws.amazon.com/jp/cloud9/pricing/

>料金の例 (AWS Cloud9 EC2 環境の場合の月次見積もり)
> デフォルトの設定 (30 分間の自動休止状態を設定して 1 か月に 20 日間、1 日 4 時間 IDE を実行) を使用する場合、90 時間の使用に対する月額料金は次のようになります。

を見る限り、1 か月の料金は 2.05 USD ですので、使っていないときはブラウザのタブを閉じ忘れなければ、大丈夫かと思います。

## Amplify の料金

Amplify の料金はこちらです。

https://aws.amazon.com/jp/amplify/pricing/

これを見る限り、今回のハンズオンやハッカソン中にのみ作った Amplify であればそれほど料金もかからないと思います。

「開発者 5 人で構成されるスタートアップチームが、1 日あたり 300 のアクティブユーザーを持つアプリケーションを取り扱っている。チームはコードを 1 日あたり 2 回コミットする。」という事例で、おおよそ、1000円/月くらいですが、それ以下の使用量かと思われます。

ですので、今回のハンズオンでつくったものは、色々試し終えたら削除するくらいで大丈夫です。

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