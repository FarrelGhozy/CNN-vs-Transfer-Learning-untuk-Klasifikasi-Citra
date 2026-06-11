# CNN vs Transfer Learning untuk Klasifikasi Citra

**Tugas Individu — Mesin Learning 2**  
**Semester 5**  
**FarrelGhozy**

## Deskripsi

Proyek ini membandingkan dua pendekatan klasifikasi citra dua kelas:
1. **CNN from scratch** — menggunakan dataset CIFAR-10 (2 kelas)
2. **Transfer Learning** — menggunakan dataset Cats vs Dogs dengan pretrained model

## Struktur Repository

```
├── dataset/
│   └── link_dataset.txt       # Link dataset CIFAR-10 & Cats vs Dogs
├── notebook/
│   └── cnn_vs_transfer_learning.ipynb  # Notebook utama
├── report/
│   └── laporan.pdf            # Laporan PDF (max 10 halaman)
├── AGENTS.md                  # Instruksi untuk AI assistant
├── PLANNING.md                # Rencana pengerjaan
├── README.md
└── requirements.txt           # Dependensi Python
```

## Cara Menjalankan

1. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

2. Buka notebook:
   ```bash
   jupyter notebook notebook/cnn_vs_transfer_learning.ipynb
   ```
   Atau via VS Code: buka file `.ipynb` langsung.

3. Run all cells — dataset akan diunduh otomatis oleh kode.

## Dataset

| Dataset | Penggunaan | Kelas | Sumber |
|---|---|---|---|
| CIFAR-10 (2 kelas) | CNN from scratch | 2 | Built-in TensorFlow |
| Dogs vs Cats | Transfer Learning | 2 | Kaggle |

## Hasil

Notebook berisi:
- Implementasi CNN from scratch + Transfer Learning
- Grafik akurasi & loss training/validation
- Confusion matrix
- Contoh prediksi benar & salah
- Analisis perbandingan dan studi kasus

Laporan PDF tersedia di `report/laporan.pdf`.
