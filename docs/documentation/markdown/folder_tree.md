# Markdown記法 - フォルダツリーの入力

[ドキュメント作成のトップへ](./../index.md)

フォルダツリー（ディレクトリツリー）はプログラムなどのフォルダ構成を明示する上で必要である。

手入力する方法と、treeコマンドを使って出力したものを取得する方法がある。

## 手入力

フォルダツリーに使用する記号は以下のように変換できる。

- たてみぎ→「┠」
- たて→「│」
- ひだりした→「└」

これを使うと任意のフォルダツリーが書ける。

Markdown上はコード扱い（```で囲む）すると等幅になって良い。

## treeコマンドによる入力

### Windowsの場合

フォルダツリーを表示したいフォルダでコマンドプロンプトを開き、

```.console

tree

```

と入力すると、

```

C:\XXX\study_note>

├─docs
│  ├─automation
│  ├─documentation
│  │  ├─git
│  │  ├─github
│  │  ├─markdown
│  │  └─pages
│  ├─excel_vba
│  ├─iot
│  ├─javascript
│  ├─linux
│  │  └─introduction
│  ├─python
│  │  ├─introduction
│  │  └─management
│  └─server
└─workspace

```

のようにフォルダ構造が出力される。ここにはファイルが含まれていないが、

```.console

tree /f

```

とすると

```

C:\XXX\study_note\docs\python>

│  index.md
│
├─introduction
│      env.md
│      venv.md
│
└─management
        check_dependencies.md
        install_offline.md
        install_requirements.md

```

のようにファイルも表示される。

クリップボードにコピーするには

```

tree /f | clip

```

などと、末尾に 「| clip」をつける。

### Macの場合

```

tree /f | pbcopy

```

と、clipの代わりにpbcopyというコマンドを使うとクリップボードにコピーできる。

### Linux(Ubuntu)の場合

最初は使えない。

```

sudo apt-get install xsel

```

してから

```

tree /f xsel --clipboard --input

```

とする。

.zshrcなどに

```

alias pbcopy = 'xsel --clipboard --input'

```

などと書いておくと、Macと同様の記述が出来るようになる。









