﻿---

### 📄 `README.md`

# 📊 Sentiment Analysis Tokopedia Review (Indonesian RoBERTa + PySpark)

Proyek ini bertujuan untuk menganalisis ribuan ulasan produk dari Tokopedia menggunakan model pra-latih [w11wo/indonesian-roberta-base-sentiment-classifier](https://huggingface.co/w11wo/indonesian-roberta-base-sentiment-classifier). Model ini memudahkan klasifikasi otomatis ke dalam kategori sentimen seperti **positif**, **netral**, dan **negatif**. 

---

## 👨‍💻 Author
- **Nama:** M. Iqbal Arrasyid
- **NIM:** 1304221038
- **Kampus:** Telkom University

---

## 📚 Deskripsi Proyek

Analisis ini mencakup:
- Pembersihan dan normalisasi teks dari review Tokopedia.
- Klasifikasi sentimen otomatis menggunakan model IndoBERT (`w11wo/indonesian-roberta-base-sentiment-classifier`).
- Visualisasi sentimen berupa WordCloud dan diagram pie.

---

## 📦 Struktur Proyek

```

sentiment-analysis-tokopedia/
├── Setimen_Analisis_Tokopedia_Review_v1_Spark.ipynb    # Notebook utama analisis
├── 1304221038_Laporan-Final-Project.pdf                # Laporan final project
├── requirements.txt                                    # Dependensi Python
├── product_reviews_dirty.csv                           # Dataset ulasan Tokopedia
├── README.md                                           # Dokumentasi proyek

````

---

## 🔧 Langkah Menjalankan Proyek di Google Colab

### 1. Buka Google Colab

Akses Google Colab melalui tautan berikut:  
[https://colab.research.google.com](https://colab.research.google.com)

### 2. Upload Notebook

Upload file `Sentimen_Analisis_Tokopedia_Review_v1_Spark.ipynb` ke Google Colab.

### 3. Upload Dataset

Dataset bernama `product_reviews_dirty.csv` harus diunggah ke direktori `/content` di Google Colab.

Jalankan kode berikut di salah satu sel notebook untuk mengunggah file CSV:

```python
from google.colab import files
files.upload()  # Pilih file product_reviews_dirty.csv dari komputer Anda
```

Setelah proses upload selesai, file dapat diakses di path `/content/product_reviews_dirty.csv`.

### 4. Jalankan Seluruh Sel

Setelah notebook dan dataset terunggah, jalankan seluruh sel dengan memilih menu **Runtime > Run all** atau tekan **Ctrl + F9**.

---


---

## 🚀 Menjalankan Proyek Secara Lokal (Colab Lokal / Jupyter)

### 1. Clone repo & masuk direktori

```bash
git clone https://github.com/IbalArrasyid/indoBert-sentiment-analysis.git
````

### 2. (Opsional) Buat Virtual Environment

```bash
python -m venv venv
source venv/bin/activate      # Linux/Mac
venv\Scripts\activate         # Windows
```

### 3. Install Dependensi

```bash
pip install -r requirements.txt
```

### 4. Jalankan Jupyter Notebook

```bash
jupyter notebook Setimen_Analisis_Tokopedia_Review_v1_Spark.ipynb
# atau
jupyter lab Setimen_Analisis_Tokopedia_Review_v1_Spark.ipynb
```

---

## 🧠 Teknologi yang Digunakan

* **Transformers** - Model Bahasa dari Hugging Face 🤗
* **PySpark** - Proses data skala besar
* **Pandas** - Manipulasi DataFrame
* **Matplotlib & WordCloud** - Visualisasi data
* **RoBERTa** - Model klasifikasi sentimen Bahasa Indonesia

---

## 📈 Output yang Dihasilkan

* Kategori sentimen untuk setiap ulasan
* WordCloud dari kata-kata populer
* Pie chart distribusi sentimen

---

## 📥 Dataset

Pastikan kamu menyediakan file `product_reviews_dirty.csv` di direktori utama proyek. File ini berisi kolom:

```csv
review
"Saya sangat puas dengan produk ini..."
"Barang datang terlambat..."
"Pelayanan oke."
...
```

---

## 🧪 Contoh Kode

Berikut snippet dari pipeline analisis:

```python
from transformers import pipeline
clf = pipeline("text-classification", model="w11wo/indonesian-roberta-base-sentiment-classifier")
clf("Pengiriman sangat cepat dan kualitas barang memuaskan.")
```

---

## ❗ Catatan Penting

* Batas input model adalah 512 token.
* Model hanya mendukung Bahasa Indonesia.
* Jika ada error seperti timeout model, cek koneksi internet atau potong teks input jadi lebih pendek.

---

## 📜 Lisensi

MIT License

---

## 👨‍💻 Kontribusi

Pull request dan issue sangat disambut! Silakan fork dan modifikasi sesuai kebutuhanmu.

---

## 🤝 Terima Kasih

Terima kasih kepada Hugging Face dan komunitas open-source NLP Bahasa Indonesia ❤️
