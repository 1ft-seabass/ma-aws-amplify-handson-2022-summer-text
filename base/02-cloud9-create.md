# Cloud9 の準備

![image](https://i.gyazo.com/a38ce016608928e5f9b782f52aed91bd.png)

Amplify 環境を扱うために AWS 上でオンラインで動くエディタ Cloud9 を準備します。

## 自分の名前を半角英数字で決めておきます

このあと、つどつど自分の環境を分かりやすく作成します。

自分の名前を使うので半角英数字で決めておきます。

たとえば Tanaka Seigo の場合は tanaka-seigo です。

## AWS にログインしましょう

![image](https://i.gyazo.com/7ac8923b90fed81c1ce09700f6cfda41.png)

レッツログイン！

## まず検索して Cloud9 にアクセス

![image](https://i.gyazo.com/6a4fb8f45fb61ce60777fc019660b3d9.png)

Cloud9 で検索します。

![image](https://i.gyazo.com/132e82be8ccc21f5d81761fe5d222452.png)

アクセスできました。

![image](https://i.gyazo.com/55d538bde6ad1f5d851898f191876c48.png)

リージョンを東京に合わせます。

![image](https://i.gyazo.com/b0dc51847bfb14009b17ab38042bb98e.png)

東京になっていることを確認します。

![image](https://i.gyazo.com/f693e782384c070a6c375ecae2395c2a.png)

Create environment ボタンをクリックします。

## Name Environment

![image](https://i.gyazo.com/df747eb83d5f97b691f0bafb8969a2e5.png)

Name Environment ページに移動します。以下のように設定を行います。

- Name
    - aws-amplify-firststep-handson-<自分の名前>-202208
    - 例 : aws-amplify-firststep-handson-tanaka-seigo-202208
- Description
    - 任意

Next step ボタンをクリックします。

## Configure settings

![image](https://i.gyazo.com/366baa9cbe7ebe6f8f777986fbc87e7c.png)

Configure settings ページに移動します。

以下のように設定を行います。

- Environment type
    - そのまま
- Instance type
    - m5.large
- Platform
    - そのまま（Amazon Linux 2）

Next step をクリックします。

## Review

Review ページに移動します。

![image](https://i.gyazo.com/aa5223ab2ede185b95fc8bf8078944c7.png)

設定を確認して Create environment ボタンをクリックします。

![image](https://i.gyazo.com/fbc4dc89494a05b9b284d9e7614753ec.png)

2～3分待つと Cloud9 の画面が表示されます。

![image](https://i.gyazo.com/ba5944d8d63248744e3e1354e90a818f.png)

できあがりました。

## 上部のメニューを確認します

![image](https://i.gyazo.com/004e3b48c017513c63e514a8d07917e2.png)

上部のメニューを確認します。

![image](https://i.gyazo.com/01f956525f21ee5a67d55722f83fcda8.png)

うっかりメニューを閉じてしまった人は、上部のこれくらいのスキマがクリックできるのでメニューを表示します。

## Dashboard

![image](https://i.gyazo.com/259059e1a71dd272d3d779bd7c296be4.png)

Cloud9 アイコンをクリックして、 Go To Your Dashboard をクリックします。

![image](https://i.gyazo.com/eaf28656a79c1d7184e05dcaed836758.png)

別ウィンドウで Dashboard が開きます。

## 詳細設定へ

![image](https://i.gyazo.com/3c9a1bee9c84f407e6fc96d02ba4785b.png)

今回作成した Cloud9 の名前のチェックボックスをクリックして選択します。

![image](https://i.gyazo.com/f8daffeb9fc6878a8c5893e026fbaab2.png)

選択した状態で上部の View details をクリックします。

![image](https://i.gyazo.com/271898cd7b2a93224dc608bd4f2489fa.png)

Environment details ページに移動します。

## EC2 の設定調整

![image](https://i.gyazo.com/10d0c5bccfbec7517d0444aeb955250a.png)

Environment details ページで EC2 Instance の項目の Go To Instance ボタンをクリックします。

![image](https://i.gyazo.com/8bcc29b7a62f8d8bd8fa90941628fa46.png)

今回 Cloud9 で使っている EC2 Instance で絞り込まれています。

![image](https://i.gyazo.com/97b657fe66d5bd6004bac6e7b3dcf4c2.png)

aws-cloud9-... の項目のチェックボックスをクリックして選択します。

![image](https://i.gyazo.com/4878699bfd37830c1b72541aa544df72.png)

下部にインスタンスの詳細が出てきます。

![image](https://i.gyazo.com/12dd32e54a934aa4afcc9a71d21f71b1.png)

ストレージの欄をクリックします。

![image](https://i.gyazo.com/ae6b6815cee495bb7b7bc029b2663641.png)

ボリューム ID をクリックします。

![image](https://i.gyazo.com/36094d1d167f79e0f9775241ea1dde67.png)

今回のボリューム ID で絞り込まれています。

![image](https://i.gyazo.com/96cb96f952b46554bd7231c638573caa.png)

チェックボックスをクリックして選択します。

![image](https://i.gyazo.com/2dc4607e13a9466cf854d040998cad2b.png)

上部のアクションボタンをクリックして、ボリュームの変更をクリックします。

![image](https://i.gyazo.com/f276af7bc972bf9dd85ac98e2618a598.png)

ボリュームの詳細ページが表示されます。もともとのサイズが 10 GiB になっていることを確認します。

![image](https://i.gyazo.com/5116004779446699ce62bd73c7106f7c.png)

30 に変更して、変更ボタンをクリックします。（コツとしては 10 のときに 1 を選択して 3 と打ち込んで 30 とするのがおすすめです。）

![image](https://i.gyazo.com/8f9800f5d733c071ce10220a3ca07c24.png)

アラートが出ますが、ここは変更するので、変更ボタンをクリックします。

## インスタンスの再起動

![image](https://i.gyazo.com/dd7f801b2c5b85ebbfefe82bb0652472.png)

右のメニューからインスタンスをクリックして、インスタンスに戻ります。

![image](https://i.gyazo.com/49cdedfaf49c4845fe1e0e0fa36d35fb.png)

今回のインスタンスがステータスチェックが緑で完了していることを確認しておきましょう。

![image](https://i.gyazo.com/c7dea9c1da90f855dcc00ae0c493c1ba.png)

今回 Cloud9 で使っている EC2 Instance を選択します。

![image](https://i.gyazo.com/31c5ef58255f30b668cd54f9a29029ab.png)

選択した上で、インスタンスの状態からインスタンスを再起動ボタンをクリックします。

![image](https://i.gyazo.com/621c0b4cc573998b62313c13ba38c021.png)

確認画面が出るので、今回 Cloud9 で使っている EC2 Instance かどうかを確認して再起動ボタンをクリックします。

![image](https://i.gyazo.com/3353dbd03466c6d17c441fca69395f2e.png)

正常に再起動しましたとメッセージが出て、再起動できたことを確認します。

## Cloud9 に戻ります

![image](https://i.gyazo.com/213625075fe0271c4b17236760cdd0e7.png)

今回使う Cloud9 に戻ります。再起動されたので、一度ブラウザを再読み込みしましょう。

## ターミナルで容量確認

![image](https://i.gyazo.com/34300908f77498404d5b7ca75ab35f0c.png)

下部のターミナルでコマンドを入力します。

```bash
df -H
```

このコマンドを入力して Enter キーを押します。

すると、以下のように結果が出ます。

```text
Filesystem      Size  Used Avail Use% Mounted on
devtmpfs        4.1G     0  4.1G   0% /dev
tmpfs           4.1G     0  4.1G   0% /dev/shm
tmpfs           4.1G  472k  4.1G   1% /run
tmpfs           4.1G     0  4.1G   0% /sys/fs/cgroup
/dev/nvme0n1p1   33G  8.9G   24G  28% /
tmpfs           806M     0  806M   0% /run/user/1000
```

/dev/nvme0n1p1 の Size が 33G のボリュームになっていることを確認します。

## Credentials を OFF

Credentials が ON のままだと作業時に影響があるようなので OFFにします。→ [参考](https://zenn.dev/shigeru_oda/books/521fa5a5a9c558c6275d/viewer/setup-cloud9#go-to-instance)

![image](https://i.gyazo.com/139b29ed118f2b6dac321ddba6b7a0e2.png)

Cloud9 アイコンをクリックして、 Preferences をクリックします。

![image](https://i.gyazo.com/ee6193d11f7561c56d896197587b9a19.png)

AWS Settings をクリックします。

![image](https://i.gyazo.com/f2acfe9145b2573868bd5bf16d3f730d.png)

AWS managed temporary credentials の項目を確認します。 ON になっているはずです。

![image](https://i.gyazo.com/1b92b63fc2143ecf12b3d0f483e8a01c.png)

これをスイッチをクリックして OFF にします。操作をしたと同時に設定が反映されます。

これで Cloud9 の準備は完了です。