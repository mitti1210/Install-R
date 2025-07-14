# Windows

Windowsはアカウント名が英語か日本語化でインストールの手間がまったく異なります。
またOnedriveを使っているかどうかでもインストールする前の準備が変わります。

## wingetの利用
Windows11と10の一部はwingetというコマンドが行えます。
wingetを使うとわざわざホームページにいきダウンロードせずにインストールができます。

## Windowsの環境の確認

### Windowsのバージョン

スタートメニューから`PowerShell`と入力し右側の「管理者権限」で開く

以下をコピペし貼り付けてEnter

``` powershell
winver
```

### アカウント名の確認
以下をコピペし貼り付けてEnter

```
$Env:USERNAME
```

ここが英語で始まる英数字であればOK(-._もおそらく可能)
日本語であれば新しいアカウントを作成した方が良い
英数字であればこの文字を後で使います。メモ帳やWordを開き貼り付けておいてください。

### Onedriveの確認
ドキュメントを見てOnedriveと書いてないか確認
書いてあれば以下の作業が必要

``` powershell
mkdir C:\Users\$Env:USERNAME\R\library
```

次にスタートメニューに「env」と入力し環境変数の編集を選びます。次に上真ん中の以下の新規をクリックします。

変数名
```
R_LIBS_USER
```

変数値
```
C:\Users\あなたのユーザー名\R\library
```

`あなたのユーザー名`は先ほどメモ帳にコピーしておいた自分のアカウント名に置き換えてください （例えばC:\Users\taroyamada\R\library）。

もし入力がわからない場合は`ディレクトリの参照`から`PC→Cドライブ→ユーザー(もしくはUser)→自分のアカウント名→R→library`と進みOKを押します。

もしフォルダが存在していなければ、PCから進めていないか、ここまでの手順でミスが起きている可能性があります。

上のウィンドウを確認し、`R_LIBS_USER`が追加されていることを確認できれば閉じてください。

### wingetの確認

管理者権限でpowershellを開きます。 以下のコマンドをコピーして貼り付け、Enterキーを押します。

``` powershell
winget -v
```

-   ここでバージョン（v1.11.400など）が表示されればwingetはインストールされています。

-   もしエラーだったり表示されていなければ別のこちらに進みます

これでインストールする準備は完了です。


### rのインストール

```　powershell
winget install -e RProject.R
```

完了すればWindowsメニューでRと入力すればRが表示されるはずです。

### Rtoolsのインストール

WindowsでRを快適に使うためのRtoolsというものがあり、これもインストールします。 以下のコマンドをコピーして貼り付け、Enterキーを押します。

``` powershell
winget install -e RProject.Rtools
```

### RStudioのインストール

Rのインストールは完了しましたが、実際にRを使う時はRStudioという総合開発環境(IDE)を使います。 最近はAI機能など充実しているPositronというIDEもありますが、ここではRStudioをインストールします。

以下のコマンドをコピーして貼り付け、Enterキーを押します。

``` powershell
winget install -e Posit.RStudio
```

```
install.packages("pacman")
pacman::p_load(tidyverse)
```

