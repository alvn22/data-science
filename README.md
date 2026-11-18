# Klasifikasi Kerusakan Jalan Berlubang & Prioritas Perbaikan Infrastruktur

## Deskripsi

Proyek Data Science ini dirancang untuk mendeteksi serta mengklasifikasikan tingkat keparahan kerusakan jalan (khususnya jalan berlubang/potholes) berbasis citra digital, sekaligus membangun sistem pemeringkatan prioritas perbaikan infrastruktur jalan. Pendekatan ini bertujuan membantu instansi terkait dalam mengalokasikan sumber daya perbaikan secara terukur, efektif, dan berbasis data.

## Dataset

Dataset yang digunakan berupa kumpulan citra jalan rusak dan berlubang yang diperoleh dari platform Roboflow.

- **Sumber Data**: [Pothole Computer Vision Model](https://universe.roboflow.com/brad-dwyer/pothole-voxrl)

## Metode

Pengembangan model mengikuti skema komparasi tiga tingkat kompleksitas (*Supervised Learning* & *Computer Vision*) yang diintegrasikan dengan sistem skoring prioritas:

1. **Model 1 – Baseline Model: Logistic Regression**
   Klasifikasi dasar menggunakan input ekstraksi fitur statistik warna (*Color Histogram* RGB/Grayscale) sebagai tolok ukur performa awal (*lower-bound benchmark*).
2. **Model 2 – Advanced ML Model: Random Forest / Support Vector Machine (SVM)**
   Klasifikasi tingkat lanjut menggunakan ekstraksi fitur tekstur dan tepian **Histogram of Oriented Gradients (HOG)** untuk menangkap pola non-linear permukaan aspal.
3. **Model 3 – Deep Learning Model: Transfer Learning (ResNet-50 / MobileNetV2)**
   Pemrosesan citra *end-to-end* berbasis *Convolutional Neural Network (CNN)* dengan bobot *pre-trained* untuk mengklasifikasikan tingkat keparahan lubang secara otomatis.

**Tahap Lanjutan (Post-Processing):**
- **Priority Scoring Index** – perhitungan bobot prioritas perbaikan infrastruktur berdasarkan kelas keparahan hasil prediksi model dan rasio luas area kerusakan (*bounding box* anotasi).

**Metrik Evaluasi:**
- *Accuracy*, *Macro Precision*, *Macro Recall*, dan *Macro F1-Score* untuk membandingkan performa klasifikasi ketiga model secara adil.
- *Confusion Matrix* dan *Inference Time* (waktu komputasi prediksi).

## Tujuan

- Mengklasifikasikan tingkat kerusakan lubang jalan ke dalam kategori tingkat keparahan (*Low*, *Medium*, *Critical*).
- Menghasilkan rekomendasi urutan prioritas perbaikan jalan berbasis urgensi dan tingkat risiko keselamatan pengendara.
- Mendukung pencapaian **SDG 9 – Industry, Innovation, and Infrastructure** (infrastruktur yang andal dan aman) serta **SDG 11 – Sustainable Cities and Communities**.

> Catatan: Deteksi berbasis citra memberikan estimasi visual terhadap dimensi dan keparahan lubang; penilaian struktural menyeluruh tetap memerlukan inspeksi teknis lapangan lanjutan.

## Struktur Repository

```text
data-dcience/
├── docs/
│   ├── 09_LAMPIRAN_B.md
│   └── Laporan_Proyek_ML_LMOP.md
├── notebook/
│   ├── 01_learning_problem_eda.ipynb
│   └── 02_data_preparation.ipynb
├── report/figures/
│   ├── eda_01_class_distribution.png
│   └── eda_02_area_ratio_distribution.png
│   └── eda_03_sample_images.png
└── README.md