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
1. R をインストール
   ```bash
   brew install --cask r
   ```
2. RStudio をインストール
   ```bash
   brew install --cask rstudio
   ```
3. RStudio を起動しパッケージをインストール
   ```r
   install.packages("pacman")
   pacman::p_load(skimr, comorbidity, broom, tidyverse, here, openxlsx, tableone)
   ```
