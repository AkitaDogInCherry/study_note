# Linux - はじめに - WindowsからSSH接続で操作する

[Linuxのトップへ](./../index.md)

## ここでやること

Raspberry Piをネットワークに繋げておけば、WindowsからCUIで操作できるようにする。

流れとしては、

- Windows側から特定できるようRaspberry Pi側のIPアドレスを固定する
- Windows側からSSH接続するためのWindows側の準備を行う
- 接続する

という流れになる。

## Raspberry PiのIPアドレスの固定

IPアドレスを固定するための設定は、/etc/dhcpcd.conf内に記載する。

DHCPとは、IPアドレスを自動で割り振ってネットワーク設定を簡略化してくれる機能である。

```sh

~ $ sudo cat /etc/dhcpcd.conf

```

で中身をシェル上に表示することができる。（nanoで直接閲覧しながら編集してもよい）

```sh

#It is possible to fall back to a static IP if DHCP fails: # define static profile
#profile static_eth0
#static ip_address=192.168.1.23/24
#static routers=192.168.1.1
#static domain_name_servers=192.168.1.1
#fallback to static profile on eth0
#interface eth0
#fallback static_eth0

```

このような記載があり、すべてコメントアウトされている。
これを受けて、以下のように末尾に記載する。

```sh

interface wlan0
static ip_address=192.168.0.51/24
static routers=192.168.0.1
static domain_name_servers=192.168.0.1

```

これは、ルータのIPアドレスが192.168.0.1で、自身のIPアドレスを192.168.0.51にしたい場合の例である。

- staticが固定することを意味する。
- interfaceは無線LANの場合で、有線LANの場合はeth0とする。

同じルータを使用するWindows PCからルータのIPアドレスを確認するには、

```console

ipconfig

```

と入力し、「デフォルトゲートウェイ」の横のIPアドレスを見ればよい。

基本的には「192.168.XXX.1」の形になっているはず。






## 参考ページ

- [Raspberry Pi のWi-Fi設定（初期設定）](https://raspida.com/wifi4raspbian)




