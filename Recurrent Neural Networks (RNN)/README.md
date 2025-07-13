# 📘 Recurrent Neural Network (RNN)

## 📚 Overview
**Recurrent Neural Network (RNN)** adalah jenis arsitektur jaringan syaraf yang digunakan untuk memproses data berurutan (sequential data), seperti teks, audio, atau data waktu (time series). RNN sangat berguna untuk tugas-tugas yang memerlukan pemahaman konteks dalam urutan data, seperti **analisis sentimen**, **penerjemahan bahasa**, **pengenalan suara**, dan **prediksi deret waktu**.

RNN memiliki kemampuan untuk **"menghafal" informasi dari urutan sebelumnya** yang digunakan untuk mempengaruhi prediksi di waktu berikutnya.

## 🛠️ Key Concepts

### 1. **Urutan Data (Sequential Data)**
RNN dirancang untuk mengatasi data yang bersifat urutan. Dalam teks, urutan kata-kata sangat penting, sehingga kata pertama mungkin mempengaruhi kata berikutnya. Model RNN menjaga informasi dalam **state** tersembunyi (hidden state) yang diperbarui setelah membaca setiap elemen input.

### 2. **Hidden State**
Pada RNN, informasi dari input sebelumnya disimpan dalam **hidden state**. Ini memungkinkan model untuk **mengingat** informasi dari waktu sebelumnya dan menggunakannya untuk keputusan pada waktu yang lebih baru dalam urutan.

### 3. **LSTM dan GRU**
RNN tradisional mengalami masalah **vanishing gradient**, yang membatasi kemampuannya dalam menangani urutan panjang. Oleh karena itu, arsitektur seperti **LSTM (Long Short-Term Memory)** dan **GRU (Gated Recurrent Unit)** dikembangkan untuk menangani masalah ini, memungkinkan model untuk mengingat informasi dalam jangka waktu yang lebih lama.

## 📚 Types of RNN

### 1. **Vanilla RNN**
Ini adalah bentuk dasar dari RNN. Namun, model ini memiliki keterbatasan dalam menangani urutan panjang karena masalah **vanishing gradient**.

### 2. **LSTM (Long Short-Term Memory)**
LSTM adalah versi RNN yang dikembangkan untuk mengatasi masalah **vanishing gradient**. LSTM memiliki struktur **gated** yang mengontrol aliran informasi dalam dan keluar dari memori, memungkinkan model untuk mengingat informasi penting lebih lama.

### 3. **GRU (Gated Recurrent Unit)**
GRU adalah varian dari LSTM yang lebih sederhana dan lebih efisien dalam beberapa kasus. Meskipun GRU dan LSTM memiliki kesamaan, GRU menggunakan dua **gates** (update dan reset) untuk mengontrol informasi yang disimpan dalam memori.

## 📚 Applications of RNN

1. **Pemrosesan Bahasa Alami (NLP)**
   - **Analisis Sentimen**: Mengklasifikasikan sentimen dari teks (positif, negatif, atau netral).
   - **Penerjemahan Bahasa**: Menerjemahkan kalimat dari satu bahasa ke bahasa lain.
   - **Generasi Teks**: Menghasilkan teks baru yang mirip dengan teks input.

2. **Pengenalan Suara**
   - **Speech Recognition**: Mengubah suara menjadi teks.

3. **Prediksi Deret Waktu**
   - **Forecasting**: Memprediksi harga saham, cuaca, atau data lainnya berdasarkan pola sebelumnya.

4. **Video Processing**
   - **Action Recognition**: Mengenali aksi dalam video berdasarkan urutan gambar.

## 🧠 How RNN Works

1. **Input Sequence**: Setiap elemen dari urutan (misalnya, kata dalam kalimat) diberikan sebagai input ke model RNN.
2. **Hidden State Update**: Setiap input memperbarui **hidden state** model yang membawa informasi dari input sebelumnya.
3. **Output**: Berdasarkan informasi dari **hidden state** dan input saat ini, RNN menghasilkan output (misalnya, klasifikasi sentimen atau prediksi kata berikutnya).

### Formula RNN
RNN dapat digambarkan dengan formula berikut:

- $$ h_t = 	anh(W_h \cdot [h_{t-1}, x_t] + b_h)  $$
- $$ y_t = W_y \cdot h_t + b_y $$

Dimana:
- $$ h_t $$ adalah hidden state pada waktu $$ t $$
- $$ x_t $$ adalah input pada waktu $$ t $$
- $$ y_t $$ adalah output pada waktu $$ t $$
- $$ W_h $$, $$ W_y $$, $$ b_h $$, dan $$ b_y $$ adalah parameter model yang dilatih

## 🧪 RNN in Practice with Python

Berikut adalah contoh implementasi sederhana RNN menggunakan **Keras** di Python untuk **analisis sentimen**:

### Install TensorFlow:
```bash
pip install tensorflow
```

### Code Example:
```python
import tensorflow as tf
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import SimpleRNN, Dense, Embedding
from tensorflow.keras.datasets import imdb
from tensorflow.keras.preprocessing.sequence import pad_sequences

# Load dataset IMDB
max_words = 10000
maxlen = 200

(x_train, y_train), (x_test, y_test) = imdb.load_data(num_words=max_words)
x_train = pad_sequences(x_train, maxlen=maxlen)
x_test = pad_sequences(x_test, maxlen=maxlen)

# Build RNN Model
model = Sequential()
model.add(Embedding(input_dim=max_words, output_dim=128, input_length=maxlen))
model.add(SimpleRNN(units=128, activation='relu'))
model.add(Dense(1, activation='sigmoid'))

# Compile model
model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])

# Train model
model.fit(x_train, y_train, epochs=5, batch_size=64, validation_data=(x_test, y_test))

# Evaluate model
test_loss, test_acc = model.evaluate(x_test, y_test)
print(f'Test accuracy: {test_acc}')
```

## 📚 Conclusion
RNN adalah arsitektur yang kuat dan efektif untuk memproses data berurutan seperti teks dan suara. Meskipun memiliki kelemahan dalam mengatasi urutan panjang, varian seperti **LSTM** dan **GRU** telah diperkenalkan untuk mengatasi masalah tersebut. RNN banyak digunakan dalam **pemrosesan bahasa alami (NLP)**, **pengenalan suara**, dan **prediksi deret waktu**, dan terus digunakan dalam berbagai aplikasi AI dan deep learning.

## 📚 References
- [The Unreasonable Effectiveness of Recurrent Neural Networks - Andrej Karpathy](http://karpathy.github.io/2015/05/21/rnn-effectiveness/)
- [Understanding LSTM Networks - Christopher Olah](https://colah.github.io/posts/2015-08-Understanding-LSTMs/)
- [TensorFlow Documentation](https://www.tensorflow.org/)
