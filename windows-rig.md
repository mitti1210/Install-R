# Windows: rig で複数バージョンを管理

## 1. 前提条件の確認
1. 管理者アカウントでログインします。
2. スタートメニューの検索から **PowerShell** を右クリックし「管理者として実行」。
3. Windows のバージョン確認:
   ```powershell
   winver
   ```
4. アカウント名の確認:
   ```powershell
   $Env:USERNAME
   ```
   日本語が含まれる場合は英数字のみのアカウントを新規作成し管理者権限を付与してください。[ローカルユーザーまたは管理者アカウントを作成する方法](https://support.microsoft.com/ja-jp/windows/create-a-local-user-or-administrator-account-in-windows-20f7d0d1-70f5-4102-9039-0a5a603b005e) を参照。
5. `winget` の確認:
   ```powershell
   winget -v
   ```
   バージョン番号が表示されれば利用できます。

## 2. インストール手順
1. rig のインストール
   ```powershell
   winget install Posit.rig
   ```
2. PowerShell を一旦閉じ、再度開きます。
3. 最新版の R をインストール
   ```powershell
   rig add release
   ```
   任意のバージョンを指定する場合:
   ```powershell
   rig add 4.4.3
   ```
4. Rtools のインストール (環境によっては時間がかかります)
   ```powershell
   rig system rtools add
   ```
5. インストール済みバージョンの確認
   ```powershell
   rig list
   ```
6. 使用するバージョンの指定
   ```powershell
   rig default 4.4.3
   ```
7. RStudio のインストール
   ```powershell
   winget install -e Posit.RStudio
   ```
8. RStudio を起動しパッケージをインストール
   ```r
   install.packages("pacman")
   pacman::p_load(skimr, comorbidity, broom, tidyverse, here, openxlsx, tableone)
   ```
