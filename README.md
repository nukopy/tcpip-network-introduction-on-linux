# 「Linux で動かしながら学ぶ TCP/IP ネットワーク入門」 写経用リポジトリ

## Links

- 書籍
  - [Linux で動かしながら学ぶ TCP/IP ネットワーク入門](https://www.amazon.co.jp/dp/B085BG8CH5)
- サポートページ
  - [github.com/momijiame/linux-tcpip-book](https://github.com/momijiame/linux-tcpip-book)
- 著者ブログ
  - (2020/03) [「Linux で動かしながら学ぶ TCP/IP ネットワーク入門」という本を書きました](https://blog.amedama.jp/entry/linux-tcpip-book)
    - 「特定の分野におけるプロフェッショナルとは、その分野でひととおりの失敗を経験した人のことをいう」 ← この言葉良き

## 実行環境

- OS
  - Host: macOS Big Sur 11.6
  - Guest: Ubuntu 20.04.3 LTS
- Software for VM
  - VirtualBox v6.1.32
  - Vagrant 2.2.19
    - プラグイン
      - vagrant-vbguest 0.3.0
        - ホスト OS とゲスト OS の GuestAdditions のバージョンを自動で合わせてくれる Vagrant のプラグイン。VM の Linux カーネルを更新した際に、 VirtualBox の GuestAdditions が古くなることで生じる問題を防いでくれる。Vagrant 起動時およびリロード時に GuestAdditions の更新があれば自動的にゲスト OS が更新される。
        - リポジトリ：[dotless-de/vagrant-vbguest](https://github.com/dotless-de/vagrant-vbguest)

Vagrant プラグインのインストール

```sh
vagrant plugin install vagrant-vbguest
```

## 環境構築

VM（Ubuntu）上で写経した。

```sh
cd tcpip-network-introduction-on-linux/

# box ファイルのダウンロード
vagrant box add ubuntu/focal64
vagrant box list
vagrant init ubuntu/focal64 # Vagrantfile が生成される

# VM の初期化 & 起動
vagrant up
vagrant status # running が表示されれば OK

# VM の中に SSH 接続で入る
vagrant ssh
# exit で VM から抜ける

# VM の停止
vagrant halt # VM の停止
```
