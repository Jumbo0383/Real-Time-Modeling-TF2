# Real-Time-Modeling-TF2

リアルタイムモデリングを Tensorflow 2.3とRaspberry Pi 4で行う．

## Raspberry Pi 4セッティング
RAM: 4GB <br>
OS == Ubuntu20.10 (64-bit) <br>

Python ==3.8.6 <br>

### Pythonインストール
必要なパッケージ一式のダウンロード <br>
$ sudo apt update
$ sudo apt install build-essential libbz2-dev libdb-dev \
  libreadline-dev libffi-dev libgdbm-dev liblzma-dev \
  libncursesw5-dev libsqlite3-dev libssl-dev \
  zlib1g-dev uuid-dev tk-dev
  
以下のサイトからPythonのダウンロード
> https://pythonlinks.python.jp/ja/index.html <br>

ダウンロードしたファイルを以下のコマンドで解凍 <br>
> $ tar xJf Python-3.x.y.tar.xz

Pythonのビルドとインストール <br>
> $ cd Python-3.8.6
> $ ./configure
> $ make
> $ sudo make install

### Tensorflowインストール
古いパッケージの更新 <br>
> $ apt-get update; apt-get dist-upgrade

必要なパッケージ一式のダウンロード <br>
> $ apt-get install python3-protobuf python3-termcolor python3-yaml python3-pydot python3-pyasn1 python3-pyasn1-modules python3-rsa python3-markdown python3-cachetools python3-future python3-dill python3-tqdm python3-pil python3-pip python3-wheel python3-setuptools python3-matplotlib python3-h5py python3-scipy python3-grpcio python3-requests-oauthlib python3-werkzeug

管理者権限で etc/apt/sources.list のコメントアウトを外し，この変更を反映 <br>
> $ sudo vi /etc/apt/sources.list <br>
> $ sudo apt-get update && sudo apt-get upgrade <br>

必要なパッケージ一式のダウンロード <br>
> $ sudo pip3 install h5py==2.9.0 <br>
> $ pip3 install -U --user six wheel mock <br>
> $ wget "https://raw.githubusercontent.com/PINTO0309/Tensorflow-bin/master/tensorflow-1.15.0-cp37-cp37m-linux_armv7l_download.sh" <br>

permission deniedになると思うので、(ls -lで権限を確認)
> chmod 755 ./tensorflow-1.15.0-cp37-cp37m-linux_armv7l_download.sh <br>
で変更する権限を与える。 <br>
> $ ./tensorflow-1.15.0-cp37-cp37m-linux_armv7l_download.sh <br>
> $ sudo pip3 install tensorflow-1.15.0-cp37-cp37m-linux_armv7l.whl
