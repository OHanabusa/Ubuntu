# Ubuntu-ssh以下は，UbuntuにOpenSSHサーバーをインストールし，接続するまでの手順です．

### 1. OpenSSHサーバーのインストール
まず，OpenSSHサーバーをインストールします．端末を開き，以下のコマンドを実行してください．

```bash
sudo apt update
sudo apt install openssh-server
```

### 2. OpenSSHサーバーのステータス確認
インストールが完了したら，OpenSSHサーバーが正しく動作しているか確認します．

```bash
sudo systemctl status ssh
```

`active (running)` と表示されていれば問題ありません．

`active(dead)`と表示されている場合，以下のコマンドを実行する．

```bash
sudo systemctl enable ssh
sudo systemctl start ssh
```

### 3. SSH接続の確認
別のマシンからSSH接続を試みます．以下のコマンドを実行し，UbuntuマシンのIPアドレスを指定します．

```bash
ssh <ユーザー名>@<IPアドレス>
```

例えば，ユーザー名が`ubuntu`で，IPアドレスが`192.168.1.10`の場合は次のように実行します．

```bash
ssh ubuntu@100.80.127.2
```

接続が成功すれば，UbuntuマシンにSSHでログインできるようになります．

これで，UbuntuへのOpenSSHサーバーのインストールと接続の手順は完了です．
