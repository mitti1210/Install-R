# Windows: winget を使わない手動インストール

## 1. アカウントの確認
1. 管理者アカウントでログインします。
2. スタートメニューの検索から **PowerShell** を右クリックし「管理者として実行」。
3. アカウント名の確認:
   ```powershell
   $Env:USERNAME
   ```
   日本語が含まれる場合は英数字のみのアカウントを新規作成し管理者権限を付与してください。[ローカルユーザーまたは管理者アカウントを作成する方法](https://support.microsoft.com/ja-jp/windows/create-a-local-user-or-administrator-account-in-windows-20f7d0d1-70f5-4102-9039-0a5a603b005e) を参照。

## 2. ライブラリ用フォルダの作成
PowerShell で次を実行し、出力されたパスを控えておきます。
```powershell
mkdir C:\Users\$Env:USERNAME\Documents\R\libs
```

## 3. 環境変数の追加
1. スタートメニューで「env」と入力し **環境変数の編集** を選択します。
2. ユーザー環境変数で「新規(N)」をクリックし、以下を入力します。
   - 変数名: `R_LIBS_USER`
   - 変数値: `C:\Users\◯◯\Documents\R\libs` （◯◯はアカウント名）


## 4. R / Rtools / RStudio のインストール
1. [RStudio のダウンロードページ](https://posit.co/download/rstudio-desktop/) を開き、`Download R for Windows` から R をインストールします。
2. 同じサイトから Rtools と RStudio もダウンロードしてインストールします。

## 5. パッケージのインストール
RStudio を起動し次を実行します。
```r
install.packages("pacman")
pacman::p_load(skimr, comorbidity, broom, tidyverse, here, openxlsx, tableone)
```
