# Markdown記法 - ソースコードなどをシンタックスハイライト付きで表示する

[ドキュメント作成のトップへ](./../index.md)

シンタックスハイライトとは、ソースコードを記述した時、言語ごとのキーワードや文法に合わせて
自動で色分けを行う機能である。

プログラミングの上では重要な機能であるが、Markdownにはソースコードのシンタックスハイライトを行う機能がある。



Markdownファイル内で、

````pandoc

```(言語名):(ファイル名)

(ソースコード、コマンドなど)

```

````

と、バッククォーテーション3つで囲むと、その中はソースコードを扱いとなる。

更に、最初のバッククォーテーションの後に言語名をつけると、その言語ごとのシンタックスハイライトを行ってくれる。

[ここ](https://github.com/github/linguist/blob/master/lib/linguist/languages.yml)にあるymlファイルの、「言語そのものの文字列」または「aliasesに書かれている文字列」が使用できる。

以下に代表的なものを示す。
Qiitaなどとは、使用できる名前が少しずつ異なっているので注意。

| 言語など | 記述名 |
|:-:|:-:|
| Windowsのコマンドプロンプト | sh / bash |
| Linuxのシェル、bashなど | sh / bash |
| WindowsのPowerShell | PowerShell / posh |
| Python | Python |
| VBA | VBA |
| Markdown| Markdown / pandoc |
| JSON | JSON |
| YAML | YAML / yml |

## 言語ごとの例

### Python

#### Markdownの記述

````pandoc

```Python:main.py

def __main__():
    print("Hello, World!")

```

````

#### 表示

```Python:main.py

def __main__():
    print("Hello, World!")

```

### コンソール

#### Markdown

````pandoc

```sh

python -m pip install matplotlib

```

````

#### 表示

```sh

python -m pip install matplotlib

```

## 差分の表示

更に、ソースコードの先頭に - や + をつけると差分を表現することができる。


## 参考ページ

- [[GitHub] Markdownの「シンタックスハイライト」に対応している言語一覧](https://blog.katsubemakito.net/articles/github-markdown-syntaxhighlighting)
- [GitHubでサポートしている言語](https://github.com/github/linguist/blob/master/lib/linguist/languages.yml)