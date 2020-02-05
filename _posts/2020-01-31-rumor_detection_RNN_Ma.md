---

layout: article
title: First Rumor Detetion Algorithm based on Deep Learning (Recurrent Neural Networks)
mode: immersive
header:
  theme: dark
article_header:
  type: overlay
  theme: dark
  background_color: '#203028'
  background_image:
    gradient: 'linear-gradient(135deg, rgba(34, 139, 87 , .4), rgba(139, 34, 139, .4))'
    src: /docs/assets/images/cover4.jpg
tags: Rumor_Detection

---

《Detecting Rumors from Microblogs with Recurrent Neural Networks》

*Jing Ma, Wei Gao, Prasenjit Mitra, Sejeong Kwon, Bernard J. Jansen, Kam-Fai Wong, Meeyoung Cha*, 2016 IJCAI

<!--more-->

[pdf](https://www.ijcai.org/Proceedings/16/Papers/537.pdf)

{:toc}

谣言检测经典论文。这是第一篇使用神经网络做谣言检测的论文，后续论文均以此论文作为对比方法做比较。



**Requirement**
python=3.7, tensorflow=1.14, keras=2.3.1

```python

from keras.preprocessing import sequence 
from keras.preprocessing.text import Tokenizer
# Using TensorFlow backend
from keras.models import Sequential
from keras.layers.core import Dense, Dropout, Activation, Flatten
from keras.layers.embeddings import Embedding
from keras.layers.recurrent import LSTM
from keras import losses
from keras import optimizers
from keras import metrics
from matplotlib import pyplot as plt

import os
import re

os.environ["TF_CPP_MIN_LOG_LEVEL"] = '3'
IMDB_DIR = "C:/Users/Scott/.keras/datasets/aclImdb/"
VERBOSE = 2


def rm_tags(text):
    re_tag = re.compile(r',<[^>]+>')
    return re_tag.sub('', text)


def load_data(train_path, test_path):
    # load train data
    x_train = []
    for typ in ['pos', 'neg']:
        folder = os.path.join(train_path, typ)
        for file in os.listdir(folder):
            with open(os.path.join(folder, file), encoding='utf-8') as f:
                x_train += [rm_tags(''.join(f.readlines()))]
    y_train = [1] * 12500 + [0] * 12500
    # load test data
    x_test = []
    for typ in ['pos', 'neg']:
        folder = os.path.join(test_path, typ)
        for file in os.listdir(folder):
            with open(os.path.join(folder, file), encoding='utf-8') as f:
                x_test += [rm_tags(''.join(f.readlines()))]
    y_test = [1] * 12500 + [0] * 12500

    token = Tokenizer(num_words=4000)
    token.fit_on_texts(x_train)
    if VERBOSE:
        print('document_count:', token.document_count)

    x_train_seq = token.texts_to_sequences(x_train)
    x_test_seq = token.texts_to_sequences(x_test)

    x_train = sequence.pad_sequences(x_train_seq, maxlen=300)
    x_test = sequence.pad_sequences(x_test_seq, maxlen=300)

    return x_train, y_train, x_test, y_test


def create_model():
    model = Sequential()
    model.add(Embedding(input_dim=4000,
                        output_dim=32,
                        input_length=300))
    model.add(Dropout(0.2))
    model.add(LSTM(32))
    model.add(Dense(units=256, activation='relu'))
    model.add(Dropout(0.2))
    model.add(Dense(units=1, activation='sigmoid'))
    if VERBOSE:
        print(model.summary())
    return model


def make_plot(history):
    if VERBOSE:
        print(history.history.keys())

    plt.title('model accuracy')
    plt.plot(history.history['accuracy'])
    plt.plot(history.history['val_accuracy'])
    plt.ylabel('accuracy')
    plt.xlabel('epoch')
    plt.legend(['acc', 'val_acc'], loc='upper_left')
    plt.show()

    plt.title('model loss')
    plt.plot(history.history['loss'])
    plt.plot(history.history['val_loss'])
    plt.ylabel('loss')
    plt.xlabel('epoch')
    plt.legend(['loss', 'val_loss'], loc='upper_left')
    plt.show()


print('1. load data...')
x_train, y_train, x_test, y_test = load_data(train_path=os.path.join(IMDB_DIR, 'train'),
                                             test_path=os.path.join(IMDB_DIR, 'test'))
print('[OK] data prepared.')

print('2. creat model...')
model = create_model()
model.compile(optimizer='adam',
              loss='binary_crossentropy',
              metrics=['accuracy'])
print('[OK] model parepared.')

print('3. train model...')
train_history = model.fit(x_train, y_train, batch_size=100,
                          epochs=10, verbose=VERBOSE, validation_split=0.2)
print('[OK] trained.')

print('4. test...')
scores = model.evaluate(x_test, y_test, verbose=VERBOSE)
print(scores)
make_plot(train_history)
print('[OK] tested.')


```

