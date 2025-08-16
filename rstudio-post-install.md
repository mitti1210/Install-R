# RStudioインストール後の準備

## 1. 文字コードを UTF-8 に設定する
1. RStudio を起動します。
2. メニューの **Tools › Global Options** を開き、左の **Code** › **Saving** を選びます。
3. "Default text encoding" が "UTF-8" になっていることを確認します。
  <img width="420" height="444" alt="image" src="https://github.com/user-attachments/assets/50724381-6fcf-4892-a8fd-9b48d63be013" />
   (System defaultであればそのままでも問題ありません)
   
4. もし別の文字コードになっている場合は "Change..." から "UTF-8" を選択し、"Apply" を押します。


## 2. ペインのレイアウトを変更する
1. **Tools › Global Options** の **Pane Layout** を開きます。
2. "Console" を右上にドラッグします。
   <!-- 画像: Pane Layout で Console を右上に移動している様子 -->
3. 右下のペインに "Environment" を追加します。
   <!-- 画像: Pane Layout で右下に Environment を追加している様子 -->

## 3. プロジェクトを作成する
1. 右上の "Project: (None)" をクリックし、**New Project...** を選びます。
2. **New Directory** › **New Project** を選択します。
3. フォルダ名に `JSNPT_RSeminar` と入力し、保存場所は **ドキュメント** もしくは **デスクトップ** など任意の場所を選びます。
   <!-- 画像: New Project で JSNPT_RSeminar を作成するダイアログ -->
4. そのまま **Create Project** を押します。`renv` の設定は変更不要です。
   <!-- 画像: 作成されたプロジェクトの画面 -->

## 4. 必要なパッケージをインストールする
1. Console に次の 2 行を貼り付け、Enter を押します。

```r
install.packages("pacman")
pacman::p_load(skimr, comorbidity, broom, tidyverse, here, openxlsx, tableone)
```

ここでは `pacman::p_load` を使っていますが、`pak` パッケージを入れて `pak::pak()` でインストールしても構いません。

これで授業で使う R の準備は完了です。
