# Klasifikasi Gambar - Intel Image Classification

Model CNN untuk mengklasifikasikan gambar alam menggunakan TensorFlow/Keras.

## Dataset

**Intel Image Classification** (Kaggle) dengan 4 kelas:
- Forest
- Glacier
- Mountain
- Sea

| Split      | Jumlah |
| ---------- | ------ |
| Training   | 7.567  |
| Validasi   | 1.894  |
| Test       | 2.062  |
| **Total**  | **11.523** |

## Hasil Model

| Metrik   | Nilai  |
| -------- | ------ |
| Train Accuracy | 87.43% |
| Test Accuracy  | 86.18% |

## Struktur Submission

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
├── Submission_Akhir_Klasifikasi_Gambar.ipynb
├── requirements.txt
└── README.md
```

## Cara Menjalankan

1. Install dependensi:
```bash
pip install -r requirements.txt
```

2. Buka dan jalankan notebook:
```
Submission_Akhir_Klasifikasi_Gambar.ipynb
```
