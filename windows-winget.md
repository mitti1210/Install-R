# Windows: winget での簡単インストール

> [!NOTE]
> RStudio は Windows 10 以降のみサポートされています。Windows 7/8 を利用している場合は、OS を Windows 10 以上にアップグレードすることをおすすめします。旧OSでのインストールは過去バージョンを自己責任で導入してください。 詳細はこちら: [Windows7/8に関する注意点](windows-r-japanese-path-issues.md)。

PowerShell の開き方やコマンドの貼り付け方から丁寧に説明します。

## 0. PowerShell を管理者として開く

1. 画面左下の **スタートボタン** をクリックします。
2. 検索欄に `powershell` と入力します。
3. 表示された **Windows PowerShell** を右クリックし、「**管理者として実行**」を選びます。

<img width="240" height="200" alt="image" src="https://github.com/user-attachments/assets/423cacf4-09ac-4696-9c76-9ef2522bc7a8" />

4. 「このアプリがデバイスに変更を加えることを許可しますか?」と出たら **はい** をクリックします。
5. 黒い画面が開き、ここに文字を入力します。これを **PowerShell（コマンドライン）** と呼びます。
   - ここに出てくる命令文をマウスで選択し、右クリックで貼り付け、**Enter キー**を押すだけで実行できます。
   - 画面に `>` が表示されているときに入力できます。表示されていない間は前のコマンドが処理中なので、`>` が再び出るまで待ちます。
   - パスワードの入力を求められた場合、画面には文字が表示されませんが、そのまま入力して **Enter キー** を押してください。

## 1. 前提条件の確認

<img width="695" height="401" alt="image" src="https://github.com/user-attachments/assets/9b5e495e-0c4f-4129-9c5e-d16ee3dd4fa3" />


1. **Windows のバージョン確認**

    ```powershell
    winver
    ```

    画面に Windows のバージョンが表示されます。Windows 10 以上であれば OK です。

2. **アカウント名の確認**

    ```powershell
    $Env:USERNAME
    ```

    日本語が含まれる場合は英数字のみのアカウントを新規作成し、管理者権限を付与してください。
    [ローカルユーザーまたは管理者アカウントを作成する方法](https://support.microsoft.com/ja-jp/windows/create-a-local-user-or-administrator-account-in-windows-20f7d0d1-70f5-4102-9039-0a5a603b005e) を参照します。

3. **winget が使えるか確認**

    ```powershell
    winget -v
    ```

    バージョン番号が表示されれば利用できます。

## 2. R のインストール

```powershell
winget install -e RProject.R
```

`-e` は完全一致検索のオプションです。R 本体がインストールされます。

## 3. Rtools のインストール

```powershell
winget install -e RProject.Rtools
```

パッケージのコンパイルに必要なツールです。環境によっては時間がかかります。

## 4. RStudio のインストール

```powershell
winget install -e Posit.RStudio
```

これで RStudio もインストールされます。

## 5. RStudio の初期設定とパッケージのインストール

RStudio の初期設定や必要なパッケージの導入については [RStudioインストール後の準備について](rstudio-post-install.md) を参照してください。
