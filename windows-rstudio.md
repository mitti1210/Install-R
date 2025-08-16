# Windows: RStudio サイトからの簡単インストール

RStudio のサイトから R・Rtools・RStudio を順番に入れる、もっとも一般的な方法です。迷ったらまずはこの手順で大丈夫です。PowerShell の開き方やコマンドの貼り付け方から丁寧に説明します。

## 0. PowerShell を管理者として開く

1. 画面左下の **スタートボタン** をクリックします。\\
2. 検索欄に `powershell` と入力します。\\
3. 表示された **Windows PowerShell** を右クリックし、「**管理者として実行**」を選びます。\\
4. 「このアプリがデバイスに変更を加えることを許可しますか?」と出たら **はい** をクリックします。\\
5. 青い画面が開き、ここに文字を入力します。これを **PowerShell（コマンドライン）** と呼びます。\\
   - ここに出てくる命令文をマウスで選択し、右クリックで貼り付け、**Enter キー**を押すと実行できます。

## 1. アカウントの確認

1. PowerShell で次のコマンドを実行し、表示された名前を確認します。

```powershell
$Env:USERNAME
```

日本語が含まれる場合は英数字のみのアカウントを新規作成し、管理者権限を付与してください。\\
[ローカルユーザーまたは管理者アカウントを作成する方法](https://support.microsoft.com/ja-jp/windows/create-a-local-user-or-administrator-account-in-windows-20f7d0d1-70f5-4102-9039-0a5a603b005e) を参照します。

## 2. ライブラリ用フォルダの作成

R のパッケージを保存するフォルダを作ります。PowerShell で次を実行し、表示されたパスを控えておきます。

```powershell
mkdir C:\Users\$Env:USERNAME\Documents\R\libs
```

## 3. 環境変数の追加

1. スタートボタンをクリックし、検索欄に `env` と入力します。\\
2. **環境変数の編集** を選びます。\\
3. 「ユーザー環境変数」の欄で **新規(N)** をクリックし、以下を入力します。
   - 変数名: `R_LIBS_USER`
   - 変数値: `C:\Users\<ユーザー名>\Documents\R\libs`
4. OK を押してすべて閉じます。

## 4. R / Rtools / RStudio のインストール

1. ブラウザで [RStudio のダウンロードページ](https://posit.co/download/rstudio-desktop/) を開きます。\\
2. ページ内の `Download R for Windows` をクリックし、ダウンロードした `R-*-win.exe` を起動して R をインストールします。\\
3. 同じページから `Rtools` をダウンロードしてインストールします。\\
4. さらに `RStudio` もダウンロードしてインストールします。\\
   - それぞれ基本的に「Next」を押し続け、最後に「Finish」で閉じれば大丈夫です。

## 5. パッケージのインストール

1. スタートメニューから RStudio を開きます。\\
2. 画面下部の「Console」と書かれた白い場所に次の2行を順番に貼り付け、Enter を押します。

```r
install.packages("pacman")
pacman::p_load(skimr, comorbidity, broom, tidyverse, here, openxlsx, tableone)
```

これで授業で使う R の準備は完了です。
