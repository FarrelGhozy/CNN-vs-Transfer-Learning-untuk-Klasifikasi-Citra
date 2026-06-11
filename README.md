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
│   ├── cifar10/                # Dataset CIFAR-10 (pickle files)
│   ├── cats_vs_dogs/           # Dataset Cats vs Dogs (file .jpg)
│   ├── cifar10.dvc             # DVC pointer — CIFAR-10
│   └── cats_vs_dogs.dvc        # DVC pointer — Cats vs Dogs
├── notebook/
│   └── cnn_vs_transfer_learning.ipynb  # Notebook utama
├── report/
│   └── laporan.pdf            # Laporan PDF (max 10 halaman)
├── AGENTS.md                  # Instruksi untuk AI assistant
├── PLANNING.md                # Rencana pengerjaan
├── README.md
└── requirements.txt           # Dependensi Python
```

## Dataset

Dataset **tidak disimpan langsung di Git** karena ukurannya besar — melainkan dilacak menggunakan **DVC (Data Version Control)** dan di-hosting di DagsHub.

| Dataset | Penggunaan | Kelas | Sumber |
|---|---|---|---|
| CIFAR-10 (2 kelas) | CNN from scratch | 2 | HuggingFace `uoft-cs/cifar10` |
| Dogs vs Cats | Transfer Learning | 2 | Kaggle |

## Cara Menjalankan

1. **Clone repositori:**
   ```bash
   git clone https://github.com/FarrelGhozy/CNN-vs-Transfer-Learning-untuk-Klasifikasi-Citra.git
   cd CNN-vs-Transfer-Learning-untuk-Klasifikasi-Citra
   ```

2. **Pull dataset dari DVC:**
   ```bash
   pip install dvc
   dvc pull
   ```
   Dataset akan diunduh dari DagsHub ke folder `dataset/`.

3. **Install dependensi Python:**
   ```bash
   pip install -r requirements.txt
   ```
   > ⚠️ Sebaiknya gunakan virtual environment (`python -m venv venv && source venv/bin/activate`).

4. **Jalankan notebook:**
   ```bash
   jupyter notebook notebook/cnn_vs_transfer_learning.ipynb
   ```
   Atau buka file `.ipynb` langsung di VS Code.

> **Catatan:** Jika notebook dijalankan tanpa `dvc pull`, kode akan otomatis mendeteksi dan memuat dataset dari folder `dataset/` bila sudah tersedia.

## Hasil

Notebook berisi:
- Implementasi CNN from scratch + Transfer Learning
- Grafik akurasi & loss training/validation
- Confusion matrix
- Contoh prediksi benar & salah
- Analisis perbandingan dan studi kasus

Laporan PDF tersedia di `report/laporan.pdf`.
