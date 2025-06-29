
# 📘 Deep Learning Overview

Deep Learning adalah sub-bidang dari Machine Learning yang fokus pada penggunaan jaringan saraf tiruan (Artificial Neural Networks) untuk memecahkan masalah yang lebih kompleks, seperti pengenalan gambar, pemrosesan bahasa alami, dan lainnya. Deep learning memanfaatkan jaringan yang terdiri dari banyak lapisan (layers), yang dikenal sebagai jaringan saraf dalam (deep neural networks), untuk melakukan representasi data yang sangat abstrak.

Deep learning memungkinkan komputer untuk belajar langsung dari data dengan sedikit atau tanpa intervensi manusia, dan telah digunakan untuk menghasilkan hasil luar biasa dalam berbagai aplikasi.

## Bahan Ajar
- [Convolutional Neural Networks (CNN)](https://github.com/arofiqimaulana/Artificial-Intelligence/tree/master/Deep%20Learning/Convolutional%20Neural%20Network%20(CNN))

## 🔍 Daftar Algoritma Deep Learning

### 📌 Jaringan Saraf Tiruan (Artificial Neural Networks - ANN)
Model dasar deep learning yang terdiri dari lapisan input, lapisan tersembunyi, dan lapisan output. Digunakan untuk berbagai aplikasi, mulai dari pengenalan pola hingga prediksi data.

### 📌 Convolutional Neural Networks (CNN)
CNN adalah jaringan saraf yang sangat efektif untuk pengolahan gambar. CNN menggunakan lapisan konvolusi untuk mengekstraksi fitur dari gambar dan telah menjadi dasar untuk banyak aplikasi pengenalan gambar dan video.

### 📌 Recurrent Neural Networks (RNN)
RNN digunakan untuk memproses data berurutan, seperti teks atau urutan waktu. Mereka memiliki memori internal yang memungkinkan mereka untuk memprediksi informasi berdasarkan input sebelumnya, membuatnya berguna untuk pemrosesan bahasa alami dan prediksi urutan.

### 📌 Long Short-Term Memory Networks (LSTM)
LSTM adalah jenis RNN yang dirancang untuk mengatasi masalah *vanishing gradient*, yang dapat mempengaruhi pelatihan RNN biasa. LSTM banyak digunakan dalam aplikasi yang melibatkan data urutan panjang, seperti pemrosesan bahasa alami dan prediksi saham.

### 📌 Gated Recurrent Units (GRU)
GRU adalah varian LSTM yang lebih sederhana, tetapi memiliki kinerja yang hampir setara dalam banyak kasus. GRU lebih cepat dalam pelatihan dan lebih efisien dalam beberapa aplikasi, meskipun LSTM sering lebih disukai dalam masalah yang lebih kompleks.

### 📌 Generative Adversarial Networks (GAN)
GAN adalah jaringan saraf yang terdiri dari dua jaringan yang saling berkompetisi: generator yang mencoba membuat data baru yang mirip dengan data asli, dan discriminator yang mencoba membedakan antara data asli dan data yang dihasilkan. GAN digunakan untuk menghasilkan gambar, video, dan data sintetis lainnya.

### 📌 Autoencoders
Autoencoders adalah jenis jaringan saraf yang digunakan untuk mempelajari representasi yang lebih rendah dari data. Mereka digunakan dalam kompresi data dan denoising. Autoencoders belajar untuk mengkodekan data input menjadi representasi yang lebih kompak dan kemudian mendekodekannya kembali.

### 📌 Deep Belief Networks (DBN)
DBN adalah jaringan saraf yang terdiri dari beberapa lapisan Restricted Boltzmann Machines (RBM). DBN digunakan untuk pembelajaran tidak terawasi dan memiliki aplikasi dalam pengenalan pola dan pengklasifikasian data.

### 📌 Radial Basis Function Networks (RBFN)
RBFN adalah jenis jaringan saraf yang menggunakan fungsi basis radial sebagai fungsi aktivasi. RBFN sering digunakan dalam klasifikasi dan regresi dan dapat digunakan untuk mempelajari representasi data yang kompleks.

### 📌 Transformer Networks
Transformer adalah model deep learning yang sangat kuat untuk pemrosesan bahasa alami dan telah mengubah banyak aplikasi NLP modern. Transformer menggunakan mekanisme perhatian (attention mechanism) untuk memungkinkan pemrosesan data dalam urutan yang sangat panjang dan telah digunakan dalam model seperti BERT, GPT, dan T5.


## 🛠️ Tools dan Library Populer untuk Deep Learning

- **TensorFlow** – Library open-source untuk komputasi numerik dan deep learning.
- **Keras** – API untuk TensorFlow yang memudahkan pembuatan model deep learning.
- **PyTorch** – Framework deep learning yang populer di kalangan peneliti dan praktisi.
- **Caffe** – Framework deep learning yang digunakan dalam pengenalan gambar.
- **MXNet** – Framework deep learning yang dikembangkan oleh Amazon.
- **Theano** – Library deep learning yang sangat kuat namun sudah tidak aktif lagi.

## 🛠️ Perbandingan Tools
| **Fitur**               | **Keras**                          | **TensorFlow**                       | **PyTorch**                          |
|-------------------------|------------------------------------|--------------------------------------|--------------------------------------|
| **Tingkat Abstraksi**   | Tinggi (API tingkat tinggi)        | Menyediakan fleksibilitas lebih tinggi | Sedikit lebih rendah dibanding Keras, tapi sangat fleksibel |
| **Kemudahan Penggunaan**| Sangat mudah digunakan             | Lebih sulit, tapi lebih fleksibel    | Lebih mudah dibanding TensorFlow, lebih fleksibel dibanding Keras |
| **Fleksibilitas**       | Terbatas jika dibandingkan dengan PyTorch dan TensorFlow | Sangat fleksibel, terutama untuk aplikasi skala besar | Sangat fleksibel, terutama dalam penelitian |
| **Dukungan Platform**   | Terintegrasi dengan TensorFlow, Theano, CNTK | Mendukung berbagai platform (mobile, cloud, embedded) | Kurang optimal untuk beberapa platform (terutama untuk mobile) |
| **Penggunaan Umum**     | Model dasar, prototyping cepat     | Model kompleks, deployment skala besar | Penelitian, eksperimen, prototyping cepat |
| **Dikembangkan**     | François Chollet, Google     | Google Brain Team | Facebook's AI Research (FAIR) |

## 📚 Referensi Belajar

- [Deep Learning Specialization by Andrew Ng on Coursera](https://www.coursera.org/specializations/deep-learning)
- [TensorFlow Documentation](https://www.tensorflow.org/learn)
- [PyTorch Documentation](https://pytorch.org/docs/stable/index.html)
- [DeepLearning.AI](https://www.deeplearning.ai/)
- [Fast.ai Deep Learning Course](https://www.fast.ai/)
