# Klasifikasi Kerusakan Jalan Berlubang & Prioritas Perbaikan Infrastruktur

## Deskripsi

Proyek Data Science ini dirancang untuk mendeteksi serta mengklasifikasikan tingkat keparahan kerusakan jalan (khususnya jalan berlubang/potholes) berbasis citra digital, sekaligus membangun sistem pemeringkatan prioritas perbaikan infrastruktur jalan. Pendekatan ini bertujuan membantu instansi terkait dalam mengalokasikan sumber daya perbaikan secara terukur, efektif, dan berbasis data.

## Dataset

Dataset yang digunakan berupa kumpulan citra jalan rusak dan berlubang yang diperoleh dari platform Roboflow.

- **Sumber Data**: [Pothole Computer Vision Model](https://universe.roboflow.com/brad-dwyer/pothole-voxrl)

## Metode

Model yang dikembangkan menggunakan pendekatan *Supervised Learning* dan *Computer Vision*, dikombinasikan dengan sistem skoring prioritas:

- **Convolutional Neural Network (CNN) / ResNet** – model baseline untuk klasifikasi citra tingkat keparahan lubang.
- **YOLO (You Only Look Once)** – deteksi dan lokalisasi lubang jalan pada citra secara real-time.
- **Priority Scoring Index (Multi-Criteria Decision Making)** – pembobotan prioritas perbaikan berdasarkan tingkat keparahan visual, estimasi volume kerusakan, dan kelas/fungsi jalan.

Evaluasi model klasifikasi dan deteksi menggunakan metrik:
- *Accuracy*, *Precision*, *Recall*, dan *F1-Score*
- *Mean Average Precision (mAP)* untuk lokalisasi objek kerusakan

## Tujuan

- Mengklasifikasikan tingkat kerusakan lubang jalan ke dalam kategori tingkat keparahan (*Low*, *Medium*, *Critical*).
- Menghasilkan rekomendasi urutan prioritas perbaikan jalan berbasis urgensi dan tingkat risiko keselamatan pengendara.
- Mendukung pencapaian **SDG 9 – Industry, Innovation, and Infrastructure** (infrastruktur yang andal dan aman) serta **SDG 11 – Sustainable Cities and Communities**.

> Catatan: Deteksi berbasis citra memberikan estimasi visual terhadap dimensi dan keparahan lubang; penilaian struktural menyeluruh tetap memerlukan inspeksi teknis lapangan lanjutan.

## Struktur Repository

```text
data-dcience/
├── Docs/
│   ├── 09_LAMPIRAN_B.md
│   ├── 09_minggu9.md
│   └── Laporan_Proyek_ML_LMOP.md
└── README.md