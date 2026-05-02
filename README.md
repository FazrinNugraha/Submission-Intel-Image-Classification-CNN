# Klasifikasi Gambar dengan Convolutional Neural Network (CNN)

Proyek ini merupakan implementasi model deep learning menggunakan arsitektur CNN untuk mengklasifikasikan gambar alam dari dataset **Intel Image Classification**. Model mampu mengenali 4 kategori berbeda: Forest, Glacier, Mountain, dan Sea.

---

## Dataset

**Sumber**: [Intel Image Classification – Kaggle](https://www.kaggle.com/datasets/puneet6060/intel-image-classification)

Dataset berisi gambar alam berukuran 150x150 piksel yang dibagi menjadi 4 kelas:

| Kelas    | Deskripsi       |
|----------|-----------------|
| Forest   | Gambar hutan    |
| Glacier  | Gambar gletser  |
| Mountain | Gambar pegunungan |
| Sea      | Gambar lautan   |

**Pembagian Data:**

| Split      | Jumlah Gambar |
|------------|---------------|
| Training   | 7.567         |
| Validasi   | 1.894         |
| Test       | 2.062         |
| **Total**  | **11.523**    |

---

## Arsitektur Model

Model dibangun menggunakan **Sequential API** dari Keras/TensorFlow dengan arsitektur sebagai berikut:

- **Conv2D + MaxPooling** — Ekstraksi fitur visual bertingkat
- **Batch Normalization** — Stabilisasi proses training
- **Dropout** — Mencegah overfitting
- **Dense + Softmax** — Klasifikasi ke 4 kelas

**Teknik yang digunakan:**
- Data Augmentation (rotasi, flip, zoom)
- Callback: `EarlyStopping`, `ModelCheckpoint`, `ReduceLROnPlateau`
- Optimizer: Adam

---

## Hasil Model

| Metrik         | Training | Test   |
|----------------|----------|--------|
| Accuracy       | 87.43%   | 86.18% |

Model memenuhi kriteria minimum akurasi ≥ 85% pada data training maupun test.

---

## Format Export Model

Model diekspor dalam 3 format untuk keperluan deployment:

| Format       | Lokasi                          | Kegunaan                        |
|--------------|---------------------------------|---------------------------------|
| SavedModel   | `saved_model/`                  | TensorFlow Serving / deployment |
| TF-Lite      | `tflite/model.tflite`           | Mobile & edge device            |
| TensorFlow.js| `tfjs_model/`                   | Deployment berbasis web         |

---

## Struktur Proyek

```
submission/
├── tfjs_model/
│   ├── model.json
│   └── group1-shard1of1.bin
├── tflite/
│   ├── model.tflite
│   └── label.txt
├── saved_model/
│   ├── saved_model.pb
│   └── variables/
├── notebook.ipynb
├── requirements.txt
└── README.md
```

---

## Cara Menjalankan

### Prasyarat

- Python 3.8+
- GPU (opsional, mempercepat training)

### Instalasi

```bash
pip install -r requirements.txt
```

### Menjalankan Notebook

1. Buka `notebook.ipynb` menggunakan Jupyter Notebook atau Google Colab
2. Jalankan setiap cell secara berurutan dari atas ke bawah
3. Pastikan dataset tersedia sebelum menjalankan cell training

> **Catatan**: Untuk download dataset dari Kaggle, diperlukan Kaggle API token. Simpan token di Colab Secrets dengan nama `KAGGLE_TOKEN`.

---

## Kriteria yang Dipenuhi

| Kriteria                                      | Status |
|-----------------------------------------------|--------|
| Dataset ≥ 1.000 gambar                        | ✅     |
| Dataset bukan RPS / X-Ray                     | ✅     |
| Split: Train / Validasi / Test                | ✅     |
| Sequential + Conv2D + Pooling Layer           | ✅     |
| Akurasi Train & Test ≥ 85%                    | ✅     |
| Plot Akurasi & Loss                           | ✅     |
| Export: SavedModel + TF-Lite + TFJS           | ✅     |
| Callback (EarlyStopping, Checkpoint, ReduceLR)| ✅     |
| Dataset ≥ 10.000 gambar                       | ✅     |
| Jumlah kelas ≥ 3                              | ✅     |
| Inference TF-Lite + bukti screenshot          | ✅     |

---

## Author

**Fazrin Nugraha**
