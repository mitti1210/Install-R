# installR

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

### Windows 10, 11の場合

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

```
https://github.com/r-lib/rig/releases
```

① バージョンの確認
```
uname -m
```



### arm64と出た場合(MacbookのM1, M2, M3, M4など)

② Homebrewのインストール
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

③ Homebrewのパスを通す
```
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> ~/.zprofile
```

```
eval "$(/opt/homebrew/bin/brew shellenv)"
```



④ rigのインストール
```
brew install rig
```

⑤ Rのインストール
```
rig add release
```

⑥ RStudioのインストール
```
brew install --cask rstudio
```

⑦ pacmanのインストール
```
install.packages("pacman")
```

⑧ パッケージのインストール
```
pacman::p_load(skimr, comorbidity, broom, tidyverse, here, openxlsx, tableone)
```


### x86_64と出た場合(MacbookのIntel CPUなど)

② Homebrewのインストール
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

③ Homebrewのパスを通す
```
(echo; echo 'eval "$(/usr/local/bin/brew shellenv)"') >> ~/.zprofile
```

```
eval "$(/usr/local/bin/brew shellenv)"
```

④ rigのインストール
```
brew install rig
```

⑤ Rのインストール
```
rig add release
```

⑥ RStudioのインストール
```
brew install --cask rstudio
```

⑦ pacmanのインストール
```
install.packages("pacman")
```

⑧ パッケージのインストール
```
pacman::p_load(skimr, comorbidity, broom, tidyverse, here, openxlsx, tableone)
```
