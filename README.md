# R / Rtools / RStudio のインストール

このリポジトリは授業や研究で使う R 環境を整えるためのガイド集です。
すべてのページでターミナル（macOS）や PowerShell（Windows）の開き方、コマンドの貼り付け方から丁寧に説明しています。

- **R**: データ分析や統計計算を行うための言語です。
- **Rtools**: Windows で追加パッケージを作るのに必要なツールです。
- **RStudio**: R を使いやすくするアプリです。
- **rig**: 複数の R バージョンを簡単に切り替えるための道具です。例えば研究室で同じバージョンをそろえたいときや、過去の解析を再現したいときに役立ちます。
- **Homebrew**: macOS でソフトを管理するための道具です。なくても R を入れられますが、最近はサイトから直接ダウンロードする以外にこうした方法もよく使われています。
- **winget**: Windows でソフトをまとめてインストールできる道具です。同じく必須ではありませんが、便利な入れ方として紹介します。

ご自身の環境に合わせて、以下の手順から 1 つを選んでください。

## Windows

### [RStudio サイトからのインストール](windows-rstudio.md)

もっとも一般的な方法です。RStudio のサイトから R・Rtools・RStudio を順番にインストールします。迷ったらまずはこの手順で大丈夫です。
ただ確認事項も多く、次のwingetを使った方がより早く簡単にインストールができます。

### [winget で簡単インストール](windows-winget.md)

上記よりも早く簡単にインストールしたい方向けです。Windows で **winget** が使える環境なら、PowerShell に数行貼り付けるだけで、半自動的に自分のパソコン環境に合った R・Rtools・RStudio をインストールできます。

### [rig で複数バージョンを管理](windows-rig.md)

複数の R バージョンを切り替えたい方向けです。まず winget で rig をインストールし、rig を使い R と Rtoolsをインストールします。複数の R バージョンを切り替えられます。RStudioは winget でインストールします。

## macOS

### [RStudio サイトからのインストール](mac-rstudio.md)

もっとも一般的な方法です。RStudio のサイトから R と RStudio を順番にインストールします。迷ったらまずはこの手順で大丈夫です。

### [rig で複数バージョンを管理](mac-rig.md)

複数の R バージョンを切り替えたい方向けです。先にrig をインストールし、rigを使い R をインストールします。複数の R バージョンを切り替えられます。

### [Homebrew でインストール](mac-homebrew.md)

既にHomebrew を利用している方向けです。Homebrew で rig をインストールし、rig で R をインストールします。RStudioもHomebrewでインストールします。

どの手順でも最後に RStudio を起動し、必要なパッケージをインストールするところまで案内しています。

## 参考サイト

- [R・RStudioインストール手順書](https://dataviz-r-epi.netlify.app/resources/R%E3%83%BBRStudio%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E6%89%8B%E9%A0%86%E6%9B%B8.pdf#page=18.08) — 日本疫学会プレセミナー2023「Rで実践！美しい Figure & Table を作成しよう」
- [RとRStudioのインストール方法の解説（macOS編/Windows編）](https://yukiyanai.github.io/jp/resources/)
- [RStudioでデフォルトライブラリのパスに日本語が含まれているときの対処法](https://ameblo.jp/tufui57/entry-12529844554.html)
- [RStudioのダイアログボックスで文字化けが発生した際の対応](https://qiita.com/Maki-Daisuke/items/0378626c9bf9971f3822)
- [RStudioインストールのメモ](https://note.com/toshi_matsuura/n/n487eecff9632)
- [R と RStudio のインストール手順（楽天ブログ）](https://plaza.rakuten.co.jp/techmfg/diary/201907110000/)
- [R/RStudio インストール時のよくある問題](https://www.fbc.keio.ac.jp/~shimpo/r_rstudio_problems.html)
- [Windows に R・RStudio・Rtools をインストールする方法](https://www.kkaneko.jp/tools/win/install.html)
- [rig と pak で R 環境を構築する（2023 年版）](https://zenn.dev/eitsupi/articles/rig-pak-p3m-2023)
- [rig: Install and Manage Multiple Versions of R](https://github.com/r-lib/rig)
- [Windows で R・RStudio をセットアップするメモ](https://qiita.com/Mitz-TADA/items/499feff855bccc9cb022)

---

## ライセンスと免責事項

- **文章（解説・ガイド）**
  このリポジトリの文章・図表などのドキュメントは
  [Creative Commons Attribution 4.0 International (CC BY 4.0)](./LICENSE-DOCS)
  のもとで公開されています。

- **コード（R / Bash スクリプト）**
  このリポジトリ内のコードは [MIT License](./LICENSE-CODE) で公開されています。

---

## 免責事項

- このリポジトリは文章とコードで異なるライセンスが適用されています。詳しくは [LICENSE](LICENSE) をご覧ください。
- 環境は一人ひとり異なるため、手順通りに進めてもトラブルが発生することがあります。
- ここで紹介するソフトウェアはすべてフリーソフトです。利用は自己責任で行ってください。
- トラブルが起きた場合は生成 AI や検索エンジンを活用すると解決できることが多いです。
- OS やソフトのバージョンは更新され続けています。最新の情報は各公式サイトで確認してください。
