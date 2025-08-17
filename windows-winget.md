# Windows: winget での簡単インストール

> [!NOTE]
> RStudio は Windows 10 以降のみサポートされています。Windows7/8のままでのインストールは非推奨です。Windows 7/8 を利用している場合は、OS を Windows 10 以上にアップグレードすることをおすすめします。Windows7/8/からWindows10/11にアップグレードした場合はトラブルが起きる可能性があるので、[Windows: RStudio サイトからのインストール](windows-rstudio.md)でインストールしてください。詳細はこちら: [Windows7/8に関する注意点](windows-r-japanese-path-issues.md)。

PowerShell の開き方やコマンドの貼り付け方から丁寧に説明します。

## 0. PowerShell を管理者として開く

1. 画面左下の **スタートボタン** をクリックします。
2. 検索欄に `powershell` と入力します。
3. 表示された **Windows PowerShell** を右クリックし、「**管理者として実行**」を選びます。

<img width="486" height="400" alt="image" src="https://github.com/user-attachments/assets/423cacf4-09ac-4696-9c76-9ef2522bc7a8" />

4. 「このアプリがデバイスに変更を加えることを許可しますか?」と出たら **はい** をクリックします。
5. 黒い画面が開き、ここに文字を入力します。これを **PowerShell（コマンドライン）** と呼びます。
   - この後に出てくる命令文をマウスで選択し、右クリックで貼り付け、**Enter キー**を押すだけで実行できます。
   - 画面に `>` が表示されているときに入力できます。表示されていない間は前のコマンドが処理中なので、`>` が再び出るまで待ちます。
   - パスワードの入力を求められた場合、画面には文字が表示されませんが、そのまま入力して **Enter キー** を押してください。

## 1. 前提条件の確認

1. PowerShell で次のコマンドを実行し、表示された名前を確認します。

```powershell
$Env:USERNAME
```

英数字であれば問題ありません。もし日本語が含まれる場合は英数字のみのアカウントを新規作成し、管理者権限を付与してください。[ローカルユーザーまたは管理者アカウントを作成する方法](https://support.microsoft.com/ja-jp/windows/windows-%E3%81%A7%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC-%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%82%92%E7%AE%A1%E7%90%86%E3%81%99%E3%82%8B-104dc19f-6430-4b49-6a2b-e4dbd1dcdf32) を参照します。

2. **winget が使えるか確認**

   以下をコピーしPowerShellに張り付けてEnterを押してください。

   ```powershell
   winget -v
   ```

   <img width="680" height="107" alt="image" src="https://github.com/user-attachments/assets/a9870985-42ce-4dcd-8a9a-06dc23ffc570" />

   バージョン番号が表示されれば利用できます。
   表示されない・エラー場出る場合はwingetを使うことはできないので[Windows: RStudio サイトからのインストール](windows-rstudio.md)でインストールしてください。

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

## 6. 上手くインストールできるか確認する

1. RStudio のコンソールで次を実行します。

   ```r
   install.packages("pacman")
   library(pacman)
   p_loaded()
   ```

   `p_loaded()` に `pacman` が表示されれば R とライブラリの設定は正常です。表示されない（`character(0)` が出る、`library(pacman)` で「there is no package called 'pacman'」と表示される）場合はインストールに失敗しています。

### トラブルが起きたときは？

- `install.packages()` が `C:\Users\<ユーザー名>\OneDrive\??????\R\win-library\...` のようなパスで止まる場合は、`R_LIBS_USER` 環境変数を設定してください。

---

環境は一人ひとり異なるため、手順どおりに進めてもトラブルが発生することがあります。エラーが出たときはウェブ検索や生成 AI を活用すると解決できることが多いです。
