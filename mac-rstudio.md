# macOS: RStudio サイトからの簡単インストール

RStudio のサイトから R と RStudio を順番に入れる、もっとも一般的な方法です。迷ったらまずはこの手順で大丈夫です。ターミナルの開き方やコマンドの貼り付け方から丁寧に説明します。

## 0. ターミナルを開く

1. Dockから **Finder**（顔のアイコン）をクリックします。
2. メニューから **アプリケーション > ユーティリティ** を開き、**ターミナル** をダブルクリックします。
   - 検索欄で `ターミナル` と入力しても開けます。
3. 黒い画面が開き、ここに文字を入力します。これを **ターミナル（コマンドライン）** と呼びます。
   - ここに出てくる命令文をマウスで選択し、`⌘ + C` でコピー、ターミナルで `⌘ + V` で貼り付け、
     **Enter キー**を押すだけで実行できます。
   - 画面に `>` が表示されているときに入力できます。表示されていない間は前のコマンドが処理中なので、`>` が再び出るまで待ちます。
   - パスワードの入力を求められた場合、画面には文字が表示されませんが、そのまま入力して **Enter キー** を押してください。

## 1. CPU アーキテクチャの確認

あなたの Mac が Apple シリコン(arm64) か Intel(x86_64) かを確認します。
ターミナルに次を貼り付け、Enter を押します。

```bash
uname -m
```

<img width="525" height="74" alt="image" src="https://github.com/user-attachments/assets/4ea605f2-b5d1-4f56-ad72-a439455bc091" />


`arm64` なら Apple シリコン、`x86_64` なら Intel です。後でダウンロードするファイルを選ぶ目印になります。

## 2. R と RStudio のダウンロードとインストール

1. ブラウザで [RStudio のダウンロードページ](https://posit.co/download/rstudio-desktop/) を開きます。

<img width="300" height="74" alt="image" src="https://github.com/user-attachments/assets/34acf8db-edb0-4421-ba28-6f8fc3875970" />

2. ページ内の **Download AND INSTALL R** をクリックし、表示されたリンクから自分の CPU に合った `R-*-macos.pkg` をダウンロードします。
<img width="496" height="327" alt="image" src="https://github.com/user-attachments/assets/2bc31002-4ebb-4462-83ae-7c5331b478df" style="border: 1px solid #000;" />

   - ファイル名に `arm64` があれば Apple シリコン用、`x86_64` があれば Intel 用です。

3. ダウンロードした `.pkg` ファイルをダブルクリックし、画面の指示に従って R をインストールします。

<img width="306" height="222" alt="image" src="https://github.com/user-attachments/assets/498f3dfd-b3b8-44a5-84bd-21723c042000" style="border: 1px solid #000;" />

続けるを選択

<img width="306" height="222" alt="image" src="https://github.com/user-attachments/assets/7b39eb77-a4d3-4722-ad4c-63e25b6a7e6c" style="border: 1px solid #000;" />

続けるを選択

<img width="306" height="222" alt="image" src="https://github.com/user-attachments/assets/c18477fb-8802-42c2-8de7-ae538ba52a6e" style="border: 1px solid #000;" />

続けるを選択

<img width="306" height="222" alt="image" src="https://github.com/user-attachments/assets/c341f590-640a-455d-8b14-16cd335de39a" style="border: 1px solid #000;" />

同意する

<img width="306" height="222" alt="image" src="https://github.com/user-attachments/assets/efcf5268-85a1-4b44-b607-97a79fc9b97b" style="border: 1px solid #000;" />

インストールを選択

4. [RStudio のダウンロードページ](https://posit.co/download/rstudio-desktop/) に戻り、 **RStudio** の `Download` ボタンをクリックし、`RStudio.dmg` をダウンロードします。
<img width="313" height="175" alt="image" src="https://github.com/user-attachments/assets/00409251-9fe1-47ab-a014-07433421628c" style="border: 1px solid #000;" />

5. ダウンロードした `.dmg` ファイルをダブルクリックし、表示されるウインドウから **RStudio** を **アプリケーション** フォルダにドラッグします。その後ディスクイメージをイジェクトしてください。
<img width="140" height="56" alt="image" src="https://github.com/user-attachments/assets/9816a752-b003-4536-8140-58ae54bce47f" style="border: 1px solid #000;" />

<img width="125" height="32" alt="image" src="https://github.com/user-attachments/assets/d7af3fc8-cb49-4ad3-a8da-924ded90b3f0" />


## 3. XQuartz をインストール（必要な人のみ）

**R Commander や EZR、3D グラフを使いたい方向け**の追加作業です。X11 を利用するこれらの機能には **XQuartz** が必要です。
[CRAN の macOS 用ページ](https://cran.rstudio.com/bin/macosx/) にリンクがあります。macOS をメジャーバージョンアップしたら XQuartz も再インストールしてください。
通常のアプリと同じようにインストールします。

<img width="496" height="327" alt="image" src="https://github.com/user-attachments/assets/1071ae0c-391e-4241-9954-b3bd31f2c2e2" style="border: 1px solid #000;" />


## 4. RStudio の初期設定とパッケージのインストール

RStudio の初期設定や必要なパッケージの導入については [RStudioインストール後の準備について](rstudio-post-install.md) を参照してください。
