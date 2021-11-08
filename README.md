# mynlp100py
My NLP100 by python

## 言語処理100本ノック 2020 (Rev 2)

<https://nlp100.github.io/ja/>


### Environment

#### Mecab

<https://hibiki-press.tech/python/mecab/5153>

```bash
sudo apt install -y mecab libmecab-dev libmecab2 swig
mecab --version
sudo apt install mecab-ipadic mecab-ipadic-utf8
sudo update-alternatives --config mecab-dictionary
sudo apt install git make curl xz-utils file
# mecab-ipadic-NEologd辞書のインストール(これは多分いらない)
cd /tmp
sudo git clone --depth 1 https://github.com/neologd/mecab-ipadic-neologd.git
cd mecab-ipadic-neologd
sudo ./bin/install-mecab-ipadic-neologd -n
mecab -d /usr/lib/x86_64-linux-gnu/mecab/dic/mecab-ipadic-neologd
# Pythonバインディングモジュールのインストール(これは多分いらない)
pip install mecab-python3
pip install unidic-lite
```

#### CaboCha

- <https://taku910.github.io/cabocha/>
- <https://qiita.com/january108/items/85c80769ea870c190eaa>
- <https://qiita.com/kazasiki/items/99505a5005aebe2efb7a>

- install CRF

```bash
wget -O CRF++-0.58.tar.gz 'https://drive.google.com/uc?export=download&id=0B4y35FiV1wh7QVR6VXJ5dWExSTQ'
tar xvzf CRF++-0.58.tar.gz
cd CRF++-0.58
./configure
make
sudo make install
cd ../
sudo ldconfig
```

- install CaboCha

```bash
FILE_ID=0B4y35FiV1wh7SDd1Q1dUQkZQaUU
FILE_NAME=cabocha-0.69.tar.bz2
curl -sc /tmp/cookie "https://drive.google.com/uc?export=download&id=${FILE_ID}" > /dev/null
CODE="$(awk '/_warning_/ {print $NF}' /tmp/cookie)"  
curl -Lb /tmp/cookie "https://drive.google.com/uc?export=download&confirm=${CODE}&id=${FILE_ID}" -o ${FILE_NAME}
tar jxvf cabocha-0.69.tar.bz2
cd cabocha-0.69
./configure -with-charset=utf-8
make
sudo make install
cd ../
cabocha
太郎は本を読んでいる
読んでいる-D    
      太郎は---D
          本を-D
      読んでいる
EOS
```
