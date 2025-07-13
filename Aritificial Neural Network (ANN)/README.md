
# Artificial Neural Network (ANN)

## Overview
**Artificial Neural Network (ANN)** adalah jenis model **deep learning** yang digunakan untuk berbagai aplikasi dalam **machine learning**, seperti **klasifikasi**, **regresi**, dan **pengenalan pola**. ANN terdiri dari **neuron-neuron** yang terhubung dalam lapisan-lapisan, yang bekerja dengan cara meniru cara kerja otak manusia dalam memproses informasi.

ANN terdiri dari **input layer**, **hidden layers**, dan **output layer** yang digunakan untuk **mempelajari hubungan kompleks dalam data**. Model ini sangat fleksibel dan dapat diterapkan untuk berbagai jenis data, seperti teks, gambar, dan data numerik.

## Key Concepts

### 1. **Input Layer**
   - Layer pertama dalam ANN, yang menerima data dari dunia luar. Data ini bisa berupa gambar, teks, atau data numerik, yang kemudian diproses oleh **hidden layers**.

### 2. **Hidden Layers**
   - Lapisan yang berada di antara input dan output layer. **Neurons di hidden layer** akan memproses data menggunakan **fungsi aktivasi** untuk memperkenalkan non-linearitas, yang memungkinkan jaringan untuk mempelajari pola yang lebih kompleks.

### 3. **Output Layer**
   - Layer terakhir dalam jaringan yang menghasilkan hasil prediksi. Untuk tugas **klasifikasi**, output layer sering kali menggunakan fungsi aktivasi seperti **softmax** (untuk klasifikasi multi-kelas) atau **sigmoid** (untuk klasifikasi biner).

### 4. **Activation Function**
   - Fungsi aktivasi digunakan untuk memperkenalkan **non-linearitas** ke dalam jaringan. Fungsi-fungsi seperti **ReLU (Rectified Linear Unit)**, **sigmoid**, dan **tanh** adalah yang paling umum digunakan dalam ANN.

### 5. **Backpropagation**
   - Proses pembelajaran di mana **kesalahan output** dihitung dan disebarkan kembali ke seluruh jaringan untuk memperbarui bobot dan bias guna meminimalkan kesalahan. Ini dilakukan menggunakan algoritma **Gradient Descent**.

## Applications of ANN

1. **Image Classification**
   - ANN digunakan untuk **mengklasifikasikan gambar** berdasarkan kategori tertentu, seperti klasifikasi objek dalam gambar.

2. **Speech Recognition**
   - Digunakan untuk mengubah suara menjadi teks, seperti dalam aplikasi **speech-to-text**.

3. **Predictive Analytics**
   - ANN digunakan untuk **memprediksi nilai** masa depan berdasarkan data historis, seperti dalam prediksi **harga saham**.

4. **Medical Diagnosis**
   - ANN digunakan dalam **diagnosis medis** untuk menganalisis gambar medis atau data pasien untuk mendeteksi penyakit.

5. **Natural Language Processing (NLP)**
   - Dalam NLP, ANN digunakan untuk tugas-tugas seperti **analisis sentimen**, **penerjemahan bahasa**, dan **pengenalan entitas**.

## How ANN Works

ANN bekerja dengan cara memproses data melalui beberapa lapisan neuron. Setiap neuron dalam lapisan memiliki **berat (weights)** dan **bias** yang diubah selama pelatihan untuk menghasilkan prediksi yang akurat.

1. **Input Data**: Data diberikan ke jaringan melalui input layer.
2. **Proses di Hidden Layer**: Data diproses melalui beberapa lapisan tersembunyi menggunakan fungsi aktivasi.
3. **Output**: Hasil prediksi dihasilkan oleh output layer berdasarkan informasi yang telah diproses.
4. **Backpropagation**: Jika prediksi salah, backpropagation digunakan untuk memperbarui bobot dan bias jaringan untuk meminimalkan kesalahan.

### Formula untuk ANN:
- Output dari setiap neuron dihitung dengan rumus:
  $$ y = f(Wx + b) $$

Dimana:
- \( W \) adalah bobot
- \( x \) adalah input
- \( b \) adalah bias
- \( f \) adalah fungsi aktivasi

## ANN in Practice with Python

Berikut adalah contoh penerapan **ANN** untuk **klasifikasi teks** menggunakan dataset **IMDB**:

### Install TensorFlow:
```bash
pip install tensorflow
```

### Code Example:
```python
import numpy as np
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense, Embedding, Flatten
from tensorflow.keras.datasets import imdb
from tensorflow.keras.preprocessing.sequence import pad_sequences

# Muat dataset IMDB
max_words = 10000  # Batasi jumlah kata yang digunakan
maxlen = 200       # Panjang maksimum setiap ulasan (200 kata)

(x_train, y_train), (x_test, y_test) = imdb.load_data(num_words=max_words)

# Padding data agar panjang input seragam
x_train = pad_sequences(x_train, maxlen=maxlen)
x_test = pad_sequences(x_test, maxlen=maxlen)

# Bangun Model ANN
model = Sequential()
model.add(Embedding(input_dim=max_words, output_dim=128, input_length=maxlen))  # Input layer + Embedding
model.add(Flatten())  # Flattening layer untuk meratakan input
model.add(Dense(128, activation='relu'))  # Hidden layer dengan 128 neuron
model.add(Dense(1, activation='sigmoid'))  # Output layer untuk klasifikasi biner (positif/negatif)

# Kompilasi Model
model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])

# Latih Model
model.fit(x_train, y_train, epochs=5, batch_size=64, validation_data=(x_test, y_test), verbose=1)

# Evaluasi Model
test_loss, test_acc = model.evaluate(x_test, y_test)
print(f'Test accuracy: {test_acc * 100:.2f}%')

# Prediksi Sentimen untuk Review Baru
sample_review = "I love this movie! It was fantastic and really enjoyable."
sample_review = sample_review.lower().split()  # Tokenisasi review menjadi daftar kata
sample_review = [imdb.get_word_index().get(word, 0) for word in sample_review]  # Ganti kata dengan indeksnya
sample_review = pad_sequences([sample_review], maxlen=maxlen)  # Padding review

prediction = model.predict(sample_review)
print(f"Prediksi Sentimen: {'Positif' if prediction[0] > 0.5 else 'Negatif'}")
```

## Conclusion
**Artificial Neural Network (ANN)** adalah model **deep learning** yang sangat fleksibel dan dapat diterapkan untuk berbagai tugas seperti **klasifikasi**, **regresi**, **pengenalan pola**, dan banyak lagi. Dengan lapisan **fully connected layers**, ANN bisa menangani data yang sangat kompleks dan mempelajari hubungan yang tidak linear antar fitur. Namun, untuk masalah yang lebih kompleks seperti **pengenalan gambar** atau **pemrosesan urutan**, arsitektur lain seperti **CNN** dan **RNN** lebih cocok.

## References
- [Deep Learning with Python by François Chollet](https://www.manning.com/books/deep-learning-with-python)
- [TensorFlow Documentation](https://www.tensorflow.org/)
