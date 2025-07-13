
# 📘  Convolutional Neural Network (CNN)

## 📚 Overview
**Convolutional Neural Network (CNN)** adalah jenis arsitektur jaringan syaraf yang terutama digunakan untuk **pemrosesan citra (image processing)** dan **komputer vision**. CNN dirancang untuk mengenali pola dalam data berupa gambar, seperti objek, tekstur, dan bentuk. CNN sangat efektif dalam pengenalan wajah, deteksi objek, dan klasifikasi gambar.

CNN adalah model deep learning yang terinspirasi oleh cara manusia memproses gambar. CNN menggabungkan lapisan konvolusi, lapisan pooling, dan lapisan fully connected untuk mengidentifikasi fitur dalam data gambar dan membuat prediksi yang akurat.

## 📚 Key Concepts

### 1. **Convolution Layer**
   - Lapisan konvolusi adalah inti dari CNN yang bertugas untuk mengekstrak fitur dari gambar. Dalam lapisan ini, filter (atau kernel) diterapkan pada gambar untuk mendeteksi pola-pola lokal seperti garis, sudut, atau tekstur. Proses ini dilakukan dengan **menggeser filter** di seluruh gambar dan menghitung hasil perkalian antara filter dan bagian gambar yang sedang diproses.

### 2. **Pooling Layer**
   - Lapisan pooling bertujuan untuk **mengurangi dimensi** dan kompleksitas data, serta meningkatkan ketahanan model terhadap pergeseran dan distorsi kecil dalam gambar. **Max pooling** adalah metode pooling yang paling umum, yang memilih nilai maksimum dari setiap area filter.

### 3. **Fully Connected Layer**
   - Lapisan ini terletak di akhir jaringan CNN dan menghubungkan neuron-neuron di lapisan sebelumnya untuk menghasilkan output final, seperti klasifikasi gambar.

### 4. **Activation Function**
   - Fungsi aktivasi seperti **ReLU** (Rectified Linear Unit) digunakan untuk mengintroduksi non-linearitas dalam jaringan, yang memungkinkan CNN untuk mempelajari hubungan yang lebih kompleks dalam data.

## 📚 Applications of CNN

1. **Image Classification**
   - Mengklasifikasikan gambar ke dalam kategori-kategori tertentu, seperti mengidentifikasi objek dalam gambar (misalnya, kucing, anjing, mobil).

2. **Object Detection**
   - Mendeteksi dan menandai objek dalam gambar atau video, sering digunakan dalam aplikasi **mobil otonom** dan **sistem pengawasan**.

3. **Face Recognition**
   - Digunakan dalam sistem pengenalan wajah untuk memverifikasi identitas seseorang, misalnya dalam perangkat keamanan atau aplikasi social media.

4. **Semantic Segmentation**
   - Memisahkan gambar ke dalam bagian-bagian yang berbeda, yang sangat berguna dalam analisis medis dan otonomi kendaraan.

5. **Image Generation**
   - Menghasilkan gambar baru berdasarkan pola atau data pelatihan, digunakan dalam aplikasi seperti **generative adversarial networks (GANs)**.

## 🧠 How CNN Works

CNN terdiri dari serangkaian lapisan yang bekerja bersama untuk mengekstrak fitur dan membuat prediksi. Berikut adalah proses umum dalam CNN:

1. **Input Image**: Gambar yang akan dianalisis dimasukkan ke dalam model CNN.
2. **Convolution**: Filter diterapkan pada gambar untuk mendeteksi fitur lokal.
3. **Activation (ReLU)**: Fungsi aktivasi diterapkan pada output dari lapisan konvolusi untuk memperkenalkan non-linearitas.
4. **Pooling**: Data direduksi untuk mengurangi dimensi dan kompleksitas.
5. **Fully Connected**: Data yang telah diproses diteruskan ke lapisan fully connected untuk menghasilkan output akhir.
6. **Output**: Prediksi klasifikasi atau deteksi objek.

### 🧪 Formula Convolution:
Proses konvolusi dapat dijelaskan dengan rumus berikut:

$$ I_{out} = (I_{in} * F) + b $$

Dimana:
`$$ I_{out} $$` adalah output citra setelah konvolusi.
`$$ I_{in} $$` adalah input citra.
`$$ F $$` adalah filter/kernel.
`$$ b $$` adalah bias yang ditambahkan ke hasil konvolusi.

## CNN in Practice with Python

Berikut adalah contoh implementasi CNN menggunakan **Keras** di Python untuk **klasifikasi gambar** menggunakan dataset **CIFAR-10**:

### Install TensorFlow:
```bash
pip install tensorflow
```

### Code Example:
```python
import tensorflow as tf
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Conv2D, MaxPooling2D, Flatten, Dense
from tensorflow.keras.datasets import cifar10
from tensorflow.keras.utils import to_categorical

# Load dataset CIFAR-10
(x_train, y_train), (x_test, y_test) = cifar10.load_data()

# Normalize data
x_train, x_test = x_train / 255.0, x_test / 255.0

# One-hot encode labels
y_train = to_categorical(y_train, 10)
y_test = to_categorical(y_test, 10)

# Build CNN Model
model = Sequential()
model.add(Conv2D(32, (3, 3), activation='relu', input_shape=(32, 32, 3)))
model.add(MaxPooling2D((2, 2)))
model.add(Conv2D(64, (3, 3), activation='relu'))
model.add(MaxPooling2D((2, 2)))
model.add(Flatten())
model.add(Dense(64, activation='relu'))
model.add(Dense(10, activation='softmax'))  # Output layer for 10 classes

# Compile model
model.compile(optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])

# Train model
model.fit(x_train, y_train, epochs=5, batch_size=64, validation_data=(x_test, y_test))

# Evaluate model
test_loss, test_acc = model.evaluate(x_test, y_test)
print(f'Test accuracy: {test_acc}')
```

## 📚 Conclusion
Convolutional Neural Networks (CNN) adalah salah satu model deep learning yang paling kuat dan efektif untuk pemrosesan gambar. Dengan kemampuannya dalam mengekstrak fitur secara hierarkis, CNN telah merevolusi bidang **komputer vision**, dan digunakan dalam berbagai aplikasi mulai dari **deteksi objek** hingga **pengenalan wajah**. CNN terus digunakan dalam berbagai industri, termasuk **automotif**, **medis**, **keamanan**, dan **e-commerce**.

## 📚 References
- [Convolutional Neural Networks - Stanford](https://cs231n.github.io/convolutional-networks/)
- [Deep Learning with Python by François Chollet](https://www.manning.com/books/deep-learning-with-python)
- [TensorFlow Documentation](https://www.tensorflow.org/)
