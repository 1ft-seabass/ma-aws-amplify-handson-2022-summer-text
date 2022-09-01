# はじめに

このハンズオン資料は以下の記事を元に Cloud9 をエディタとして使って Amplify Studio と Figma のアプリ作成を行うものです。

![image](https://i.gyazo.com/31e637ad95d0cdc10b1f4918bcc9211f.jpg)

[AWS Amplify Studio – 最小限のプログラミングでFigmaからフルスタックのReactアプリを実現 | Amazon Web Services ブログ](https://aws.amazon.com/jp/blogs/news/aws-amplify-studio-figma-to-fullstack-react-app-with-minimal-programming/)

参考記事

- 一般提供になりました
  - [AWS Amplify Studio 一般提供開始のお知らせ | Amazon Web Services ブログ](https://aws.amazon.com/jp/blogs/news/announcing-the-general-availability-of-aws-amplify-studio/)

とはいえ、「最小限のプログラミングでFigmaからフルスタックのReactアプリを実現」のとおり、AWS と Figma と React という結構色々な複合技術を最小限のプログラミングですすめるものなので、なんでも簡単というよりは、構造を理解しながら作れるようにしていく感じです。頑張っていきましょう～。

## おねがい

![image](https://i.gyazo.com/77b427f743657a3018d0e3da1080428e.png)

- もしかすると、Figma + AWS Amplify ハンズオンも参加された方が、こちらも参加される場合、ユーザーの作成や Cloud9 の準備など、とくに前半が重複する場合がありますが、Amplify 初級ということもあり、なるべく抜けがないように全部の流れを体験することを大事にしています。あらかじめご了承ください。
- 同じ AWS クラウド組織内でみなさん全員のアカウントが発行されている関係で Amplify による「同時に」「似たような処理が働いた」ときの挙動が若干読めません。
- 上記による影響でエラーや不具合が起きた場合に、問題解決のためハンズオンの中断や時間切れがあるかもしれません。
- なるべく走破できるように一緒に頑張りますが、やり切れない場合は、後日フォローが行われる可能性があります。講師も全力で頑張ります！

## それでは

はじめていきましょう！