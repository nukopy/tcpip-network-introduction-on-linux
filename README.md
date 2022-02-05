# 「Linux で動かしながら学ぶ TCP/IP ネットワーク入門」 写経用リポジトリ

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

ゲスト OS の情報

```sh
lsb_release -a

No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 20.04.3 LTS
Release:        20.04
Codename:       focal
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
