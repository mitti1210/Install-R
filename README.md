# install R

このサイトは日本神経理学療法学会サテライトカンファレンスの事前動画におけるRのインストール手順になっています。

RのインストールはWndows, Macでも違いがあるだけでなく、バージョンの違いでもインストール方法が異なります。

## Windows

### 環境の確認

① バージョン確認

```         
winver
```

② アカウント名の確認

```         
$Env:USERNAME
```

③ wingetが使えるかの確認

```         
winget -v
```

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

⑩ 環境変数

```         

```

⑪ pacmanのインストール

```         
install.packages("pacman")
```

⑫ パッケージのインストール

```         
pacman::p_load(skimr, comorbidity, broom, tidyverse, here, openxlsx, tableone)
```

### 

## Macの場合

① バージョンの確認
```
uname -m
```

以下のどちらかが出ます

1. arm64:(MacbookのM1, M2, M3, M4など新しいMac)
2. x86_64:(MacbookのIntel CPUなど古いMac)



④ RとRstudioのインストール



⑦ pacmanのインストール
```
install.packages("pacman")
```

⑧ パッケージのインストール
```
pacman::p_load(skimr, comorbidity, broom, tidyverse, here, openxlsx, tableone)
```


