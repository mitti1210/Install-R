# install R

このサイトは日本神経理学療法学会サテライトカンファレンスの事前動画におけるRのインストール手順になっています。

RのインストールはWndows, Macでも違いがあるだけでなく、バージョンの違いでもインストール方法が異なります。

## Windows

### 環境の確認

PowerShellを開きます

<img width="813" height="820" alt="image" src="https://github.com/user-attachments/assets/526b52cd-8678-47db-885e-c199b4198775" />


① Windowsのバージョン確認

```         
winver
```

Windows11なら②へ。10より前なら②の後⑨へ

② アカウント名の確認

```         
$Env:USERNAME
```

英語で始まる英数字かどうかを確認

③ wingetが使えるかの確認

```         
winget -v
```

v1.11.430 のようなバージョン情報が出ていれば次に進める

------------------------------------------------------------------------

### wingetが使える場合

④ Rのインストール

```         
winget instll -e RProject.R
```

⑤ RToolsのインストール

```         
winget install -e RProject.Rtools
```

⑥ RStudioのインストール

```         
winget install -e Posit.RStudio
```

⑦ pacmanのインストール

```         
install.packages("pacman")
```

⑧ パッケージのインストール

```         
skimr, comorbidity, broom, tidyverse, here, openxlsx, tableone
```

### 以前のWindowsの場合(Windows10より前)

⑨ フォルダの作成

```         
mkdir C:\Users\$Env:USERNAME\R\library
```

⑩ 環境変数の作成

```         

```

⑪ rigのインストール

ブラウザに以下を入力

```
https://github.com/r-lib/rig/releases
```

windows板をインストール

⑫ rigの起動

PowerShellを開く

```
rig add release
```

完了するまで待ち以下を実行

```
rig system rtools
```

⑬ RStudioのインストール

https://posit.co/download/rstudio-desktop/

⑪ pacmanのインストール

```         
install.packages("pacman")
```

⑫ パッケージのインストール

```         
pacman::p_load(skimr, comorbidity, broom, tidyverse, here, openxlsx, tableone)
```

### 

## Macの場合(なるべく簡単にインストールしたい)

① バージョンの確認
```
uname -m
```

以下のどちらかが出ます。インストールする時に必要になります

1. arm64
2. x86_64



④ RとRstudioのインストール
以下をウェブで検索

```
RStudio
```


⑤ pacmanのインストール
```
install.packages("pacman")
```

⑥ パッケージのインストール
```
pacman::p_load(skimr, comorbidity, broom, tidyverse, here, openxlsx, tableone)
```

## Macの場合(バージョン管理を行う場合)

- チームでバージョンを揃えたい場合
- ある特殊な解析でRのバージョンが指定されている場合

① バージョンの確認
```
uname -m
```

以下のどちらかが出ます。インストールする時に必要になります

1. arm64
2. x86_64

② rigのインストール
```
https://github.com/r-lib/rig/releases
```

```
rig --version
```



③ Rのインストール
```
rig available
```


最新版をインストールする場合
```
rig add
```

指定のバージョンをインストールする場合(ここでは)
```
rig add 4.4.3
```

④ インストールされているRのバージョンを確認する
```
rig list
```

⑤ 使用するRのバージョンを指定する
```
rig default 4.4.3 
```

⑥ RStudio/Positronをインストールする
```
RStudio
```


```
positron r
```

⑦  pacmanのインストール
```
install.packages("pacman")
```

⑥ パッケージのインストール
```
pacman::p_load(skimr, comorbidity, broom, tidyverse, here, openxlsx, tableone)
```
