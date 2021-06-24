# Markdown記法 - ソースコードなどをシンタックスハイライト付きで表示する

[ドキュメント作成のトップへ](./../index.md)

シンタックスハイライトとは、ソースコードを記述した時、言語ごとのキーワードや文法に合わせて
自動で色分けを行う機能である。

プログラミングの上では重要な機能であるが、Markdownにはソースコードのシンタックスハイライトを行う機能がある。



Markdownファイル内で、

````markdown

```(言語名):(ファイル名)

(ソースコード、コマンドなど)

```

````

と、バッククォーテーション3つで囲むと、その中はソースコードを扱いとなる。

更に、最初のバッククォーテーションの後に言語名をつけると、その言語ごとのシンタックスハイライトを行ってくれる。

よく使われるものは省略名があることもある。以下によく使うものを示す。

| 言語など | 記述名・省略名 |
|:-:|:-:|
| Windowsのコマンドプロンプトなど | console |
| Linuxのシェル、bashなど | shell / bash / sh |
| WindowsのPowerShell | posh |
| Python | python / py |
| VBA | visualbasic / vb |
| C# | csharp / c# / cs |
| JSON | json |
| YAML | yaml / yml |

## 言語ごとの例

### Python

#### Markdownの記述

````markdown

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

### Console

#### Markdown

````markdownの記述

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
