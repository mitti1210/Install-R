# macOS: RStudio サイトからの簡単インストール

## 1. CPU アーキテクチャの確認
ターミナルで次を実行し、`arm64` または `x86_64` が表示されることを確認します。
```bash
uname -m
```

## 2. インストール手順
1. [RStudio のダウンロードページ](https://posit.co/download/rstudio-desktop/) を開き、使用しているアーキテクチャに対応した **R for macOS** をダウンロードしてインストールします。
2. 同じページから **RStudio** をダウンロードしインストールします。
3. RStudio を起動しパッケージをインストール
   ```r
   install.packages("pacman")
   pacman::p_load(skimr, comorbidity, broom, tidyverse, here, openxlsx, tableone)
   ```
