# リストファイルを使ってライブラリをインストールする

[Pythonのトップへ](./../index.md)

## 何に使うの？

```

python -m pip install (ライブラリ)

```

を複数のライブラリに対して一括でやりたい。

または、あるプロジェクトで使用したライブラリをリストに書き出し、別プロジェクトにまとめてインストールしたい。

## 基本

アプリフォルダ直下にファイル名「requirements.txt」のテキストファイルを作成する。

（ファイル名は通例で使用されるもの）

テキストファイル内に必要なものを書き出す。

```text:requirements.txt

numpy
opencv-python

```

-rオプションを使用し、ファイルを指定してインストールする。

```dos

python -m pip install -r requirements.txt

```

## アプリAの使用ライブラリをアプリBにコピー

アプリAの仮想環境内で

```

python -m pip freeze > requirements.txt

```

で、使用しているライブラリをバージョン情報含めrequirements.txtに出力する。

そのrequirements.txtをアプリB直下にコピーし、

```dos

python -m pip install -r requirements.txt

```

により、アプリBにコピーできる。

