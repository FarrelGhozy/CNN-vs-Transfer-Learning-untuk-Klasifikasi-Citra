# PLANNING.md — CNN vs Transfer Learning

## Phase 0: Setup (estimasi 30 menit)

- [ ] Buat struktur folder: `dataset/`, `notebook/`, `report/`
- [ ] Buat `requirements.txt` (tensorflow/keras atau pytorch, matplotlib, numpy, sklearn, seaborn)
- [ ] Siapkan link dataset CIFAR-10 (2 kelas) dan Cats vs Dogs (Kaggle) → simpan di `dataset/link_dataset.txt`
- [ ] Buat `README.md` (judul, identitas, deskripsi tugas, cara menjalankan, link dataset, referensi)

## Phase 1: Preprocessing & Augmentasi (estimasi 1 jam)

- [ ] Load CIFAR-10, filter 2 kelas (pilih, misal: kucing vs anjing, atau pesawat vs mobil)
- [ ] Load Cats vs Dogs, pilih subset 100+ gambar per kelas
- [ ] Split data: 70% train, 15% val, 15% test
- [ ] Terapkan preprocessing: resize (misal 150x150 atau 224x224 tergantung model), normalize pixel [0,1]
- [ ] Terapkan augmentasi (rotation, flip, zoom, shift) pada data training
- [ ] Dokumentasikan preprocessing & augmentasi di notebook

## Phase 2: CNN from Scratch — Arsitektur & Training (estimasi 2 jam)

- [ ] Rancang arsitektur CNN:
  - Input layer sesuai ukuran gambar
  - 2-3 Conv2D + ReLU + MaxPooling blocks (justifikasi jumlah filter & kernel size)
  - Flatten atau GlobalAveragePooling
  - Dense layer + Dropout untuk regularisasi
  - Output layer (2 kelas, softmax)
- [ ] Compile: pilih optimizer (Adam), learning rate, loss (categorical_crossentropy / sparse), metrics
- [ ] Train dengan EarlyStopping, simpan history
- [ ] Evaluasi: akurasi & loss plot, confusion matrix, classification report
- [ ] Catat waktu training & jumlah parameter

## Phase 3: Transfer Learning — Model Pretrained (estimasi 2 jam)

- [ ] Pilih arsitektur pretrained (rekomendasi: MobileNetV2 untuk ringan, ResNet50 untuk akurat)
- [ ] Load model tanpa top layer, set input size sesuai dataset
- [ ] Strategi A: Feature extraction — freeze semua base layer, tambah classifier baru
  - Train classifier, evaluasi
- [ ] (Opsional) Strategi B: Fine-tuning — unfreeze 10-30% layer teratas base model
  - Train dengan learning rate kecil (1e-5), evaluasi
- [ ] Catat waktu training & jumlah parameter

## Phase 4: Evaluasi & Perbandingan (estimasi 1.5 jam)

- [ ] Plot perbandingan akurasi training/validation (CNN vs Transfer Learning)
- [ ] Plot perbandingan loss training/validation
- [ ] Confusion matrix untuk kedua model
- [ ] Tampilkan contoh prediksi benar & salah (masing-masing 3-5 gambar)
- [ ] Buat tabel perbandingan 11 aspek (akurasi, loss, waktu, parameter, overfitting, dll)
- [ ] Analisis overfitting: bandingkan gap train-val accuracy

## Phase 5: Analisis & Studi Kasus (estimasi 1.5 jam)

- [ ] Analisis dataset: ukuran, variasi, imbalance, noise (berdasarkan hasil observasi)
- [ ] Analisis performa: model terbaik, stabilitas, hubungan data-performa
- [ ] Analisis pemilihan pendekatan: kapan CNN vs Transfer Learning (7 faktor)
- [ ] Jawab 4 skenario studi kasus (medis 300 img, 1M produk, 2 hari prototipe, GPU besar)
- [ ] Refleksi pribadi: 5 pertanyaan refleksi (tantangan, bagian tersulit, perbedaan, pilihan nyata, pembelajaran)

## Phase 6: Laporan & Finalisasi (estimasi 1.5 jam)

- [ ] Export notebook ke HTML/PDF atau tulis laporan langsung
- [ ] Gunakan template IEEE (sesuaikan dengan format conference)
- [ ] Pastikan 10 halaman max dengan 10 section sesuai rubrik
- [ ] Upload notebook, laporan, README ke GitHub
- [ ] Kumpulkan link GitHub via Moodle

## Checklist final sebelum submit

- [ ] Notebook bisa di-run dari awal sampai akhir tanpa error
- [ ] Semua grafik & tabel muncul di output notebook
- [ ] Tidak ada dataset besar di repo (hanya link)
- [ ] Struktur folder sesuai ketentuan
- [ ] Argumentasi analisis berdasarkan data eksperimen, bukan asumsi umum
- [ ] Refleksi pribadi diisi dengan jujur dan spesifik
