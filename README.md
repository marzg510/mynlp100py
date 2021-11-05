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
