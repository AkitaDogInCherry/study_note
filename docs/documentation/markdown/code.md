# Markdown記法 - ソースコードなどをシンタックスハイライト付きで表示する

[ドキュメント作成のトップへ](./../index.md)

シンタックスハイライトとは、ソースコードを記述した時、言語ごとのキーワードや文法に合わせて
自動で色分けを行う機能である。

プログラミングの上では重要な機能であるが、Markdownにはソースコードのシンタックスハイライトを行う機能がある。

Markdownファイル内で、

````console

```(言語名):(ファイル名)

(ソースコード、コマンドなど)

```

````

と、バッククォーテーション3つで囲むと、その中はソースコードを扱いとなる。

更に、最初のバッククォーテーションの後に言語名をつけると、その言語ごとのシンタックスハイライトを行ってくれる。

※ただし、GitHub Pagesでテーマを使用している場合、デフォルトではシンタックスハイライトがうまく動作しない。テーマを設定した上でのシンタックスハイライトは[こちらのページ](./index.md)を参照のこと。

※より詳しくは、シンタックスハイライトを行う「[Rouge](http://rouge.jneen.net/)」という技術を使用している。

[ここ](https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers)にあるymlファイルの、「言語そのものの文字列」または「aliasesに書かれている文字列」が使用できる。

以下に代表的なものを示す。略称を使用してもよい。
GitHubなどとは、使用できる名前が少しずつ異なっているので注意。

| 言語など | 記述名・略称 |
|:-:|:-:|
| Windowsのコマンドプロンプト | console / sh / bash |
| Linuxのシェル、bashなど | sh / bash |
| WindowsのPowerShell | powerShell / posh |
| Python | python / py |
| VBA | vb |
| Markdown| markdown / md |
| JSON | json |
| YAML | yaml / yml |

## 言語ごとの例

### Python

#### Markdownの記述

````console

```py:main.py

def __main__():
    print("Hello, World!")

```

````

#### 表示

```py:main.py

def __main__():
    print("Hello, World!")

```

### コンソール

#### Markdown

````console

```console

python -m pip install matplotlib

```

````

#### 表示

```console

python -m pip install matplotlib

```

## 差分の表示

更に、ソースコードの先頭に - や + をつけると差分を表現することができる。


## 参考ページ

- [Rouge - List of supported languages and lexers](https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers)