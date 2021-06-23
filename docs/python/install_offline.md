# ネットに繋げないPCでライブラリをインストールする

[Pythonのトップへ](./index.md)

## 何に使うの？

事情があってネットに繋げないPCや、プロキシサーバ下でどうしてもうまくインストールできない場合など。

## 全体の流れ

1. [使用するライブラリの依存関係を調べる](./check_dependencies.md))
1. 使用するライブラリおよびそのライブラリが依存するライブラリをローカルにダウンロードする
1. ダウンロードしたライブラリを--no-indexを指定したコマンドでインストールする

ここではライブラリの依存関係は分かっており、全て「[Python Package Index](https://pypi.org/)」からインストール可能なものであるとする。

## ローカルにライブラリをダウンロードする

### はじめに

ここではopencv-contrib-python（opencv-pythonにArUcoなどのcontribを含めたもの）をインストールする方法を説明する。

ローカルにダウンロードしたものをインストールする方法では、pip installのように自動で依存関係にあるライブラリをインストールしてくれない。

ここで、opencv-pythonはnumpyに依存しているため、numpyもセットにしないといけない。

### ネットにつなげられるPCでの作業

[Python Package Index](https://pypi.org/)にアクセスし、まず[opencv-contrib-python](https://pypi.org/project/opencv-contrib-python/)を検索する。

見つけたら「Download Files」をクリックし、ダウンロード可能なファイル群を確認する。

使用するのがPython3.9であること、Windows(64bit)であることから、ここでは「opencv_contrib_python-4.5.2.54-cp39-cp39-win_amd64.whl」をダウンロードする。ダウンロードしたファイルは、適当な場所に作った「opencv_contrib_src」フォルダに入れておく。

同じく、numpyもダウンロードし、同じ「opencv_contrib_src」フォルダに入れておく。ここでは「numpy-1.20.3-cp39-cp39-win_amd64.whl」をダウンロードした。

この「opencv_contrib_src」フォルダをUSBファイルなどに入れて、ネットにつなげられないPCに持っていく。

### ネットにつなげられないPCでの作業

アプリのルートフォルダ内に「downloaded」フォルダ（名前は可変）を作成し、その中に先ほどの「opencv_contrib_src」フォルダを入れる。

仮想環境内に入り、

```dos

python -m pip install --no-index --find-links=downloaded\opencv_contrib_src opencv-contrib-python

```

とすると、opencv-contrib-pythonをインストールすることができる。

ちなみに、依存関係にあるライブラリであるnumpyがない状態で同じコマンドを実行すると

```

ERROR: Could not find a version that satisfies the requirement numpy>=1.19.3 (from opencv-contrib-python) (from versions: none)
ERROR: No matching distribution found for numpy>=1.19.3

```

というメッセージが出て、インストールされない。

### うまくいかない場合

この方法は、パッケージのバージョンの関係などの整合性をpipが確認してくれないため、pip installする場合と比べるとうまくいかないことが多い。

エラーメッセージで「〇〇がないよ！」というのを確認すると、どのパッケージのインストールで困っているかを判断できる。

「Wheel」と書かれたものと「Source」と書かれたものがある場合、「Wheel」の方がうまくいきやすい。

## 参考ページ

- [pip install を手動でローカルにダウンロードしたファイルで行う方法](https://gammasoft.jp/blog/pip-install-from-local-archives-by-manually/)


