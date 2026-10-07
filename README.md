# CNN Image Classification — MNIST & Fashion-MNIST

Repository ini berisi dua project pembelajaran **Convolutional Neural Network (CNN)** menggunakan dataset **MNIST** dan **Fashion-MNIST**.

Kedua project dibuat untuk memahami alur dasar CNN mulai dari memuat dataset, preprocessing gambar, membangun arsitektur CNN, training, evaluasi, hingga melakukan prediksi.

## Project

### 1. MNIST

Dataset MNIST berisi gambar grayscale berukuran 28×28 piksel dengan 10 kelas angka, yaitu 0–9.

Tahapan yang dilakukan:
- Memuat dataset MNIST menggunakan `tensorflow.keras.datasets`
- Melihat ukuran data dan contoh gambar
- Normalisasi pixel dengan membagi nilai pixel menggunakan `255.0`
- Mengubah bentuk data menjadi `(28, 28, 1)` agar sesuai dengan input CNN
- Membangun model CNN
- Melatih model selama 5 epoch
- Evaluasi pada data training dan testing
- Melakukan prediksi terhadap satu gambar

### 2. Fashion-MNIST

Fashion-MNIST berisi gambar grayscale 28×28 piksel yang terbagi menjadi 10 kelas pakaian dan alas kaki.

Kelas yang digunakan:

| Label | Kelas |
|---|---|
| 0 | T-shirt/top |
| 1 | Trouser |
| 2 | Pullover |
| 3 | Dress |
| 4 | Coat |
| 5 | Sandal |
| 6 | Shirt |
| 7 | Sneaker |
| 8 | Bag |
| 9 | Ankle boot |

Tahapan yang dilakukan:
- Memuat dataset Fashion-MNIST
- Melihat ukuran data dan contoh gambar
- Melihat daftar kelas menggunakan `np.unique()`
- Mengecek nilai maksimum pixel
- Normalisasi pixel dengan `255.0`
- Mengubah bentuk data menjadi `(28, 28, 1)`
- Membangun model CNN
- Melatih model selama 10 epoch
- Evaluasi pada data training dan testing
- Melakukan prediksi terhadap satu gambar

## Arsitektur CNN

Kedua project menggunakan arsitektur CNN yang hampir sama:

```text
Input Image (28×28×1)
        ↓
Conv2D (32 filters, 3×3, ReLU)
        ↓
MaxPooling2D (2×2)
        ↓
Conv2D (64 filters, 3×3, ReLU)
        ↓
MaxPooling2D (3×3)
        ↓
Flatten
        ↓
Dense (128, ReLU)
        ↓
Dense (10, Softmax)
        ↓
Class Prediction
```

### Penjelasan singkat

- **Conv2D**: mencari pola atau fitur pada gambar.
- **MaxPooling2D**: mengecilkan ukuran feature map sambil mempertahankan informasi penting.
- **Flatten**: mengubah feature map menjadi data satu dimensi.
- **Dense**: mengolah fitur untuk melakukan klasifikasi.
- **Softmax**: menghasilkan probabilitas untuk 10 kelas.

## Training

Optimizer yang digunakan:

```python
optimizer='adam'
```

Loss function:

```python
loss='sparse_categorical_crossentropy'
```

Metric:

```python
metrics=['accuracy']
```

Training dilakukan menggunakan:

```python
batch_size=128
validation_split=0.2
```

MNIST menggunakan **5 epoch**, sedangkan Fashion-MNIST menggunakan **10 epoch**.

## Tools

- Python
- TensorFlow / Keras
- NumPy
- Matplotlib
- Jupyter Notebook

## File

```text
CNN.ipynb
CNN2.ipynb
README.md
```

- `CNN.ipynb` → CNN untuk klasifikasi MNIST.
- `CNN2.ipynb` → CNN untuk klasifikasi Fashion-MNIST.

## Tujuan Pembelajaran

Project ini dibuat sebagai latihan untuk memahami konsep dasar **Convolutional Neural Network**, terutama:

1. Cara mempersiapkan data gambar.
2. Cara melakukan normalisasi pixel.
3. Cara mengubah dimensi gambar agar dapat diproses CNN.
4. Cara kerja `Conv2D` dan `MaxPooling2D`.
5. Cara menggunakan `Flatten` dan `Dense`.
6. Cara melakukan training dan evaluasi model.
7. Cara menggunakan model CNN untuk melakukan prediksi gambar.

Project ini merupakan bagian dari proses pembelajaran dasar **Deep Learning dan Computer Vision**.
