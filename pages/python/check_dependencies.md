# ライブラリの依存関係・ライセンスを調べる

[Pythonのトップへ](./index.md)

## 何に使うの？

主に、次の項のネットに繋げないPCやプロキシサーバでうまくpip installできないPCでの
ライブラリインストールに使用する。

## 全体の流れ

1. 普通にpip installできるPCを使用し、依存関係・ライセンス確認用のプロジェクトを作る
1. 使用するライブラリのリストをrequirements.txtに作成する
1. pipdeptree、pip-licensesのライブラリをそのリストに追加する
1. リストをインストールするコマンドでライブラリ群をインストールする
1. pipdeptreeのコマンドでライブラリの依存関係を確認する
1. pip-licensesのコマンドでライブラリの依存関係を確認する

4までは前項の「リストファイルを使ってライブラリをインストール」を参照のこと。

2に記載のライブラリは、普通に「pipdeptree」「pip-licenses」を追加すればよい。

または、requirements.txtを使用せず、python -m pip installで必要なライブラリをインストールした状態にしてもよい。

## ライブラリの依存関係の確認

アプリのルートフォルダで

```dos

python -m pipdeptree

```

コマンドを実行すると、ライブラリの依存関係が表示される。

例：numpy、opencv-python、pandasをインストール後、実行した場合

```dos

opencv-python==4.5.2.54
  - numpy [required: >=1.19.3, installed: 1.20.3]
pandas==1.2.4
  - numpy [required: >=1.16.5, installed: 1.20.3]
  - python-dateutil [required: >=2.7.3, installed: 2.8.1]
    - six [required: >=1.5, installed: 1.16.0]
  - pytz [required: >=2017.3, installed: 2021.1]

```

## ライブラリのライセンスの確認

アプリのルートフォルダで

```dos

python -m pip-licenses

```

コマンドを実行すると、各ライブラリのライセンスが表示される。

例：numpy、opencv-python、pandasをインストール後、実行した場合

```

 Name                   Version   License
 numpy                  1.20.3    BSD License
 opencv-python          4.5.2.54  MIT License
 pandas                 1.2.4     BSD
 python-dateutil        2.8.1     BSD License, Apache Software License
 pytz                   2021.1    MIT License
 scipy                  1.6.3     BSD License
 six                    1.16.0    MIT License

```

## 参考ページ

- [Pythonパッケージの依存関係とライセンスを確認する](https://dev.classmethod.jp/articles/python-pipdeptree_licenses/)






