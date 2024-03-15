投稿済み：[\[AWS CDK\]Chatbotを使ってLambdaのエラーをSlackに通知してみた \| DevelopersIO](https://dev.classmethod.jp/articles/cdk-lambda-error-chatbot/)

# LambdaでSeleniumを動かす構成をAWS CDKで実装する

## はじめに

最近Lambda上でSeleniumを動かしていたのですが、Python3.7から3.12へランタイムを上げたことで動作しなくなってしまいました…

これまではLambdaレイヤーを使ってchromedriverとheadless-chromiumをレイヤー化する方法を利用していました。これがランタイムが変わるとうまくいかなくなります。

<iframe class="hatenablogcard" style="width:100%;height:155px;max-width:680px;" title="AWS Lambda PythonでSeleniumを使える環境を構築する | DevelopersIO" src="https://hatenablog-parts.com/embed?url=https://dev.classmethod.jp/articles/aws-lambda-python-selenium-make-env/" width="300" height="150" frameborder="0" scrolling="no"></iframe>


動作しなくなった原因はSeleniumで利用する`chromedriver`や`headless-chromium`の互換性がないことです。ここがLambda上でSeleniumを使う上で一番面倒なところで、新しいバージョンを使おうとしてもどのバージョンが正しく動作するのかが分かりません。

そこで、調べていたところ[docker-selenium-lambda](https://github.com/umihico/docker-selenium-lambda/tree/main)というLambda上でSeleniumを動かすためのリポジトリがあったので使ってみました。

元々のリポジトリではSAMを使ったデプロイが行われていますが、私のプロジェクトではCDKを利用しているため今回はCDKで実装してみます。

## やってみる

以下の環境で実装しました。

[bash]
❯ npx cdk --version
2.99.1 (build b2a895e)
❯ python  --version 
Python 3.12.1
[/bash]


### 事前準備


### CDKのコード


### Lambdaのコード


### 試してみる

上記のCDKをデプロイします。
[bash]
cdk deploy
[/bash]

## 終わりに

## 参考
