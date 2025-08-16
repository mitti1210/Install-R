# Windows: rig で複数バージョンを管理

> [!NOTE]
> RStudio は Windows 10 以降のみサポートされています。Windows 7/8 を利用している場合は、OS を Windows 10 以上にアップグレードすることをおすすめします。旧OSでのインストールは過去バージョンを自己責任で導入してください。 詳細はこちら: [Windows7/8に関する注意点](windows-r-japanese-path-issues.md)。

PowerShell の開き方やコマンドの貼り付け方から丁寧に説明します。

## 0. PowerShell を管理者として開く

1. 画面左下の **スタートボタン** をクリックします。
2. 検索欄に `powershell` と入力します。
3. 表示された **Windows PowerShell** を右クリックし、「**管理者として実行**」を選びます。
4. 「このアプリがデバイスに変更を加えることを許可しますか?」と出たら **はい** をクリックします。
5. 青い画面が開き、ここに文字を入力します。これを **PowerShell（コマンドライン）** と呼びます。
   - ここに出てくる命令文をマウスで選択し、右クリックで貼り付け、**Enter キー**を押すだけで実行できます。
   - 画面に `>` が表示されているときに入力できます。表示されていない間は前のコマンドが処理中なので、`>` が再び出るまで待ちます。
   - パスワードの入力を求められた場合、画面には文字が表示されませんが、そのまま入力して **Enter キー** を押してください。

## 1. 前提条件の確認

1. **Windows のバージョン確認**

   以下をコピーしてPowerShellに張り付けてEnterを押してください。

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

   以下をコピーしてPowerShellに張り付けてEnterを押してください。

    ```powershell
    winget -v
    ```

   <img width="680" height="107" alt="image" src="https://github.com/user-attachments/assets/597d1741-0bbf-4fa8-b0f3-323ae495c444" />


    バージョン番号が表示されれば利用できます。何も出ない場合、エラーが出る場合はwingetが使えないので、

## 2. rig のインストール

   同様に以下をコピーしてPowerShellに張り付けてEnterを押してください。

```powershell
winget install -e Posit.rig
```

   <img width="1439" height="180" alt="image" src="https://github.com/user-attachments/assets/549d7bba-c2eb-4641-b610-4597f0e81f3d" />

   この画面が出てきたらYを入力しEnter

   <img width="1108" height="226" alt="image" src="https://github.com/user-attachments/assets/e2243e0b-421e-4731-bdcb-3ef8d29af32d" />

   インストールが完了したら **PowerShell を一度閉じ**、再度管理者として開きます。

   一度閉じないと以降のコードを入力しても反応しない場合があります。

## 3. rig が入ったか確認

```powershell
rig --version
```

   <img width="495" height="57" alt="image" src="https://github.com/user-attachments/assets/b9a510c8-8d51-4111-b298-cde9c63e55a4" />

   バージョン番号が表示されれば成功です。

## 4. 最新の R をインストール

```powershell
rig add release
```

   `release` は「一番新しい安定版」を意味します。通常はこれだけで十分です。インストールが終わるまで待ちます。

   <img width="980" height="337" alt="image" src="https://github.com/user-attachments/assets/296a65cc-e650-41c6-97b7-0df5475a8777" />

   上記のような画面になり、一番下に`＞`が出るようになればインストール完了です。

   基本的には`release`で大丈夫ですが、*もし意図的に特定のバージョンを入れたい場合だけ* 次のようにバージョンを指定します。

```powershell
rig add 4.4.3
```

   もしrigでインストールできるバージョンを知りたい場合は以下を入力します(基本的には不要です)

 ```bash
    rig available
 ```


## 5. Rtools のインストール

開発に必要なツールを入れます。インターネット環境によっては10分ほど時間がかかります。

```powershell
rig system rtools add
```

## 6. インストール済み R を確認

```powershell
rig list
```

1つだけ入っているならそのバージョンだけが表示されます。
2つ以上入れた場合はここで一覧を確認できます。
`rig` で入れた R だけが表示されるため、別の方法で入れた R は必要なら `rig add` で入れ直してください。

## 7. 使う R のバージョンを切り替える（複数バージョンをインストールしている場合のみ）

```powershell
rig default 4.4.3
```

バージョンを複数入れているときだけ必要な操作です。
1つしか入っていないなら何もしなくて大丈夫です。

## 8. RStudio のインストール

```powershell
winget install -e Posit.RStudio
```

`-e` は完全一致検索のオプションです。

## 9. RStudio の初期設定とパッケージのインストール

RStudio の初期設定や必要なパッケージの導入については [RStudioインストール後の準備について](rstudio-post-install.md) を参照してください。
