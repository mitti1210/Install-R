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

<img width="680" height="107" alt="image" src="https://github.com/user-attachments/assets/a9870985-42ce-4dcd-8a9a-06dc23ffc570" />

1. **winget が使えるか確認**

   以下をコピーしPowerShellに張り付けてEnterを押してください。

    ```powershell
    winget -v
    ```

   バージョン番号が表示されれば利用できます。
   表示されなければwingetを使うことはできないので

## 2. R のインストール

以下をコピーしPowerShellに張り付けてEnterを押してください。

```powershell
winget install -e RProject.R
```

<img width="1439" height="180" alt="image" src="https://github.com/user-attachments/assets/817e1d24-4289-4d06-8a46-98e88ae5c964" />

この画面が出た場合はYと入力しEnter

<img width="1038" height="222" alt="image" src="https://github.com/user-attachments/assets/974d4114-75fb-48e2-a5e5-d41ad96c01fd" />

後は待つだけで R 本体がインストールされます。

## 3. Rtools のインストール

同様に以下をコピーしPowerShellに張り付けてEnterを押してください。

```powershell
winget install -e RProject.Rtools
```

パッケージのコンパイルに必要なツールです。環境によっては時間がかかります(約10分かかることもある)。

## 4. RStudio のインストール

```powershell
winget install -e Posit.RStudio
```

これで RStudio もインストールされます。

## 5. RStudio の初期設定とパッケージのインストール

RStudio の初期設定や必要なパッケージの導入については [RStudioインストール後の準備について](rstudio-post-install.md) を参照してください。
