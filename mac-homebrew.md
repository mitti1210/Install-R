# macOS: Homebrew でインストール

## 1. CPU アーキテクチャの確認
ターミナルで次を実行し、`arm64` または `x86_64` が表示されることを確認します。
```bash
uname -m
```

## 2. Homebrew の確認
Homebrew がインストール済みか確認します。
```bash
brew --version
```
インストールされていない場合は [公式サイト](https://brew.sh/) の手順で導入してください。

## 3. インストール手順
1. rig を Homebrew でインストール
   ```bash
   brew tap r-lib/rig
   brew install rig
   ```
2. rig で R をインストール
   1. rig のバージョンを確認
      ```bash
      rig --version
      ```
   2. 利用可能な R を確認
      ```bash
      rig available
      ```
   3. 最新版をインストール
      ```bash
      rig add release
      ```
      バージョンを指定する場合:
      ```bash
      rig add 4.4.3
      ```
   4. インストール済みバージョンを確認
      ```bash
      rig list
      ```
   5. 使用するバージョンを指定
      ```bash
      rig default 4.4.3
      ```
3. RStudio をインストール
   ```bash
   brew install --cask rstudio
   ```
4. RStudio を起動しパッケージをインストール
   ```r
   install.packages("pacman")
   pacman::p_load(skimr, comorbidity, broom, tidyverse, here, openxlsx, tableone)
   ```
