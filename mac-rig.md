# macOS: rig でバージョン管理

## 1. CPU アーキテクチャの確認
ターミナルで次を実行し、`arm64` または `x86_64` が表示されることを確認します。
```bash
uname -m
```

## 2. インストール手順
1. [rig のリリースページ](https://github.com/r-lib/rig/releases) からインストーラをダウンロードしインストールします。
2. ターミナルを再起動し rig のバージョンを確認
   ```bash
   rig --version
   ```
3. 利用可能な R を確認
   ```bash
   rig available
   ```
4. 最新版をインストール
   ```bash
   rig add
   ```
   バージョンを指定する場合:
   ```bash
   rig add 4.4.3
   ```
5. インストール済みバージョンを確認
   ```bash
   rig list
   ```
6. 使用するバージョンを指定
   ```bash
   rig default 4.4.3
   ```
7. [RStudio のダウンロードページ](https://posit.co/download/rstudio-desktop/) から **RStudio** または **Positron** をインストールします。
8. RStudio を起動しパッケージをインストール
   ```r
   install.packages("pacman")
   pacman::p_load(skimr, comorbidity, broom, tidyverse, here, openxlsx, tableone)
   ```
