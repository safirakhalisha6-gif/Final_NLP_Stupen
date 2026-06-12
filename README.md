# 📊 LogSight — Text Mining Logbook Magang VINIX7 Batch 4

> Implementasi Text Mining berbasis NLP untuk analisis pola kegiatan peserta  
> program Studi Independen PT Vinix Seven Aurum (VINIX7) Batch 4  
> **Tugas Konversi Mata Kuliah Natural Language Processing**

---

## 👤 Identitas

| | |
|---|---|
| **Nama** | Safira Khalisha |
| **NIM** | *(isi NIM)* |
| **Program Studi** | Teknik Informatika |
| **Universitas** | Universitas Malikussaleh |
| **Mata Kuliah** | Natural Language Processing |
| **Dosen Pengampu** | Dr. Eng. Defry Hamdhana, S.Kom., M.Kom |

---

## 📌 Deskripsi Proyek

Peserta program MSIB VINIX7 Batch 4 diwajibkan mengisi **logbook mingguan** berisi narasi kegiatan harian. Data teks ini selama ini hanya berfungsi sebagai dokumen administratif dan belum pernah dianalisis secara otomatis.

Proyek ini membangun pipeline **text mining berbasis NLP** untuk mengekstrak pola kegiatan dari 166 entri logbook tiga anggota tim divisi Python Machine Learning selama 10 minggu, menggunakan tiga teknik unsupervised secara kombinatif:

| Task | Metode | Pertanyaan yang Dijawab |
|---|---|---|
| 1 | K-Means Clustering | Jenis kegiatan apa yang paling dominan? |
| 2 | LDA Topic Modeling | Topik apa yang muncul tiap minggu? |
| 3 | Cosine Similarity | Seberapa mirip pola kerja antar anggota? |

---

## 📂 Struktur Repository

```
nlp-logbook-vinix7/
│
├── data/
│   └── logbook_bersih.csv          # Dataset utama (166 entri, 3 anggota)
│
├── output/
│   ├── hasil_preprocessing.csv
│   ├── hasil_clustering.csv
│   ├── hasil_topik_lda.csv
│   ├── ringkasan_cluster_per_anggota.csv
│   ├── ringkasan_topik_per_minggu.csv
│   ├── hasil_cosine_similarity.csv
│   ├── elbow_method.png
│   ├── distribusi_cluster.png
│   ├── pca_cluster.png
│   ├── wordcloud_topik.png
│   ├── heatmap_topik.png
│   ├── cosine_similarity_perminggu.png
│   └── heatmap_cosine_overall.png
│
├── nlp_logbook_vinix7.ipynb        # Notebook Google Colab (kode lengkap)
├── requirements.txt
└── README.md
```

---

## 🗂️ Dataset

- **Sumber:** Logbook mingguan 3 peserta divisi Python Machine Learning VINIX7 Batch 4
- **Periode:** Minggu 1–10 (Februari–Mei 2026)
- **Format:** CSV dengan kolom `nama`, `minggu`, `hari_tanggal`, `deskripsi`

| Anggota | Jumlah Entri |
|---|---|
| Wardatul A'ani | 50 |
| Safira Khalisha | 66 |
| Tri Mayluddin Villanda | 50 |
| **Total** | **166** |

---

## ⚙️ Cara Menjalankan

### 1. Buka di Google Colab
Klik badge di bawah atau buka file `nlp_logbook_vinix7.ipynb` langsung di Colab:

[![Open In Colab]([/colab.research.google.com/github/*(username)*/nlp-logbook-vinix7/blob/main/nlp_logbook_vinix7.ipynb](https://colab.research.google.com/drive/1CG61WNFhu5qAOEiX_8iOWj0EOQV3g3lK?usp=sharing))

### 2. Jalankan sel secara berurutan
```
SEL 1  → Install library & import
SEL 2  → Load dataset CSV
SEL 3  → Preprocessing (PySastrawi)
SEL 4  → TF-IDF Vectorization
SEL 5  → K-Means Clustering + visualisasi
SEL 6  → LDA Topic Modeling + visualisasi
SEL 7  → Cosine Similarity antar anggota
SEL 8  → Ringkasan & kesimpulan otomatis
SEL 9  → Simpan semua output
```

### 3. Upload dataset
Saat SEL 2 berjalan, upload file `logbook_bersih.csv` dari folder `data/`.


## 🛠️ Library yang Digunakan

```
python-docx
PySastrawi
scikit-learn
gensim
matplotlib
seaborn
wordcloud
pandas
numpy
```

Install sekaligus:
```bash
pip install python-docx PySastrawi scikit-learn gensim matplotlib seaborn wordcloud
```


## 📈 Ringkasan Hasil

### Task 1 — K-Means Clustering (K=5)

| Cluster | Jumlah Entri | Interpretasi |
|---|---|---|
| 0 | 43 (25,9%) | Pengerjaan tugas teknis & implementasi kode |
| 1 | 11 (6,6%) | Evaluasi, finalisasi, dan pengumpulan tugas |
| 2 | 30 (18,1%) | Sesi briefing & mentorship bersama mitra |
| 3 | 73 (44,0%) | Diskusi tim, pembagian tugas & kolaborasi |
| 4 | 9 (5,4%) | Pembelajaran mandiri & riset eksplorasi |

### Task 2 — LDA Topic Modeling (5 Topik)

Ditemukan progresivitas topik yang jelas dari minggu awal hingga akhir:
- **Minggu 1–4:** Dominan topik pengolahan data & pipeline
- **Minggu 5–8:** Beralih ke analisis model & mentorship teknis  
- **Minggu 9–10:** Meningkat pada topik finalisasi & evaluasi

### Task 3 — Cosine Similarity

| Pasangan | Rata-rata Similarity |
|---|---|
| Safira vs Tri | 0,2817 *(tertinggi)* |
| Tri vs Wardatul | 0,2789 |
| Safira vs Wardatul | 0,1868 *(terendah)* |


## 📄 Laporan

Laporan lengkap tersedia di file `Laporan_NLP_Safira_Khalisha.pdf` (atau `.docx`) dalam repository ini.

