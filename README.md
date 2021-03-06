# Introduction
In this project, I have made a toy GUI that calculates the TF-IDF vector of a sentence given. This project is to get better insights into the TF-IDF method of sentence embedding in Natural Language Processing.

The Idea is to provide the application with a preprocessed text file that it will open and then train the TF-IDF model internally. The application uses sklearns's implementation of TF-IDF vectorizer to train and then askes for a sentence (again preprocessed) to be provided, on which it runs the trained TF-IDF model. It then outputs the TF-IDF vector with the corresponding weights.

**NOTE:** The input file and the sentence need to be preprocessed in advanced.

---

# Requirements
```
python           3.6.6
scikit-learn     0.20.0
scipy            1.1.0
pyqt             5.9.6
```

---

# Theory
The TF-IDF vectorizer method works by denoting each word in a sentence by a number. This number incorporates important parameters such as **frequency** and **uniqueness**.

**TF - term frequency**

<img src="https://latex.codecogs.com/gif.latex?f_{t,d}&space;=&space;\text{&hash;&space;of&space;times&space;the&space;word&space;}&space;t&space;\text{appears&space;in&space;the&space;document&space;}&space;d" title="f_{t,d} = \text{# of times the word } t \text{appears in the document } d" />

<img src="https://latex.codecogs.com/gif.latex?f_{t^o,&space;d}&space;=&space;\text{total&space;number&space;of&space;tokens&space;in&space;document}&space;d" title="f_{t^o, d} = \text{total number of tokens in document} d" />

<img src="https://latex.codecogs.com/gif.latex?\boxed{tf_t&space;=&space;\frac{f_{t,d}}{\Sigma{}{}}}" title="\boxed{tf_t = \frac{f_{t,d}}{\Sigma{}{}}}" />


**IDF - inverse document frequency**

<img src="https://latex.codecogs.com/gif.latex?a&space;=&space;\text{&hash;&space;of&space;docs}" title="a = \text{# of docs}" />

<img src="https://latex.codecogs.com/gif.latex?b_t&space;=&space;1&space;&plus;&space;\text{&hash;&space;of&space;docs&space;having&space;word&space;}&space;t" title="b_t = 1 + \text{# of docs having word } t" />

<img src="https://latex.codecogs.com/gif.latex?\boxed{idf_t&space;=&space;log&space;\left(&space;\frac{a}{b_t}\right)}" title="\boxed{idf_t = log \left( \frac{a}{b_t}\right)}" />

We multiply these numbers together to find the final number for each of the word. The vector representing the sentence is now a collection of these numbers. This is how we find the TF-IDF vector.

Once we have TF-IDF vectors we can have similarity matrices like cosine similarity that find the similarity between two vectors.

---

# Usage
This GUI works by first giving in a text file that has been normalized with no punctuations. The Python program underneath the GUI trains the `TF-IDF vectorizer` imported from `sklearn`.
To run the GUI, run `app.py`, which will internally import `tfidf.py`.

Selecting a file to train the tfidf model on.

![upload](https://i.imgur.com/Y3vvqQr.png)


The application then asks for an input sentence (again normalized).

![sample_sent](https://i.imgur.com/d9w1cL0.png)


The program takes in this sentence and transforms it into TF-IDF space and returns by a popping a popup what shows the TF-IDF vector of the sentence provided.

![Popup](https://i.imgur.com/UtDC8zx.png)

---

# Disclosure
I have cited the code that I have reused from a source.
[1](https://pythonspot.com/pyqt5-textbox-example/), [2](https://www.commonlounge.com/discussion/99e86c9c15bb4d23a30b111b23e7b7b1)

---
