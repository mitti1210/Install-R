# macOS: Homebrew で R と RStudio をインストールする方法


文字を打つ場所や「Enter」を押すタイミングまで丁寧に説明します。

## 0. ターミナルを開く

1. 画面左上の **Finder**（顔のアイコン）をクリックします。
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

<img width="526" height="125" alt="image" src="https://github.com/user-attachments/assets/0e9aaa27-a9d1-4553-9f75-5488af376998" />


`arm64` なら Apple シリコン、`x86_64` なら Intel です。後の手順で迷ったときの目印になります。

## 2. Homebrew の確認

**Homebrew** は Mac でソフトをまとめて管理できる道具です。
入っているか確かめるため、次を実行します。

```bash
brew --version
```

バージョン番号が表示されれば OK です。
何も表示されない場合は、ブラウザで [Homebrew の公式サイト](https://brew.sh/) を開き、
そのページにあるコードをターミナルに貼り付けて Enter を押してインストールしてください。

## 3. Homebrew で rig をインストールする

**rig** は R のバージョンを簡単に切り替えるための道具です。
最初に Homebrew に rig の場所を教えてから、インストールします。

```bash
brew tap r-lib/rig
brew install rig
```

- `brew tap` は Homebrew に新しいソフトの倉庫を追加する合図です。初回だけで大丈夫です。
- `brew install rig` で rig 本体を入れます。

<img width="561" height="65" alt="image" src="https://github.com/user-attachments/assets/992c65e7-f045-47f3-939b-7b1ffd9fe888" />


## 4. rig で R をインストールする

ここからは Homebrew ではなく rig を使います。

1. **rig が正しく入ったか確認**

    ```bash
    rig --version
    ```

<img width="519" height="46" alt="image" src="https://github.com/user-attachments/assets/f3e8952d-ac02-4b3c-a8ad-29a167f84556" />

    バージョン番号が出れば成功です。

2. **インストールできる R の一覧を見る**

    ```bash
    rig available
    ```

    どのバージョンの R を用意できるかが表示されます。

3. **最新の R をインストール**

    ```bash
    rig add release
    ```

    `release` は「一番新しい安定版」を意味します。通常はこれだけで十分です。
    *もし特定のバージョンを入れたい場合だけ* 次のように数字を指定します。

    ```bash
    rig add 4.4.3
    ```

4. **インストールされている R を確認**

    ```bash
    rig list
    ```

    <img width="444" height="112" alt="image" src="https://github.com/user-attachments/assets/f763d83c-e04b-412b-9362-dd3b13387e36" />

    1つだけ入っているならそのバージョンだけが表示されます。
    2つ以上入れた場合はここで一覧を確認できます。
   *がついているのが現在使っているバージョン(default)です。今は`R4.4.3`になっています。
    `rig` で入れた R だけが表示されるため、別の方法で入れた R は必要なら `rig add` で入れ直してください。

6. **使う R のバージョンを切り替える（複数バージョンをインストールしている場合のみ）**

    ```bash
    rig default 4.5.1
    ```

    上記入力すると先程defaultだった`R4.4.3`から`R4.5.1`に切り替わります(rig listで確認可能)
    バージョンを複数入れているときだけ必要な操作です。
    1つしか入っていないなら何もしなくて大丈夫です。

## 5. XQuartz をインストール（必要な人のみ）

**R Commander や EZR、3D グラフを使いたい方向け**の追加作業です。X11 を利用するこれらの機能には **XQuartz 2.8.5 以降** が必要です。
[CRAN の macOS 用ページ](https://cran.rstudio.com/bin/macosx/) にもリンクがあります。macOS をメジャーバージョンアップしたら XQuartz も再インストールしてください。

```bash
brew install --cask xquartz
```

## 6. RStudio をインストールする

**RStudio** は R を使いやすくするアプリです。Homebrew で入れます。

```bash
brew install --cask rstudio
```

## 7. RStudio で必要なパッケージを入れる

1. 「アプリケーション」フォルダから RStudio を開きます。
2. 画面下部の「Console」と書かれた白い場所に次の2行を順番に貼り付け、Enter を押します。

```r
install.packages("pacman")
pacman::p_load(skimr, comorbidity, broom, tidyverse, here, openxlsx, tableone)
```

ここでは `pacman::p_load` を使っていますが、`pak` パッケージを入れて `pak::pak()` でインストールしても構いません。

これで授業で使う R の準備は完了です。

