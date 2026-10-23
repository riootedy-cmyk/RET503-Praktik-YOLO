# Praktik YOLO RET503 — Analisis Perbandingan Eksperimen

## 1. Informasi Praktikum

- **Mata Kuliah:** RET503
- **Nama:** Rio Tedy Adhyaksa Situmorang
- **NIM:** 4222411002
- **Topik:** Eksperimen dan Evaluasi Model YOLO untuk Deteksi Objek
- **Bahasa Pemrograman:** Python
- **Framework:** Ultralytics YOLO

## 2. Deskripsi Proyek

Repository ini berisi dokumentasi hasil praktik pengujian dan perbandingan model YOLO untuk mendeteksi objek pada dataset yang terdiri dari tiga kelas, yaitu:

- `person`
- `car`
- `bottle`

Praktik ini bertujuan untuk membandingkan performa model berdasarkan konfigurasi pelatihan yang berbeda, serta menganalisis pengaruh penggunaan pretrained weights dan ukuran gambar terhadap hasil deteksi objek.

## 3. Dataset

Dataset yang digunakan adalah `dataset_v1` dengan rincian:

- Jumlah gambar: 220
- Jumlah kelas: 3
- Kelas objek: person, car, dan bottle

Dataset digunakan dalam eksperimen pelatihan dan evaluasi model. Pembagian data mengikuti konfigurasi dataset yang digunakan pada program praktik.

## 4. Skenario Eksperimen

Tiga skenario eksperimen dilakukan untuk membandingkan performa model.

| Eksperimen | Konfigurasi | Tujuan |
|---|---|---|
| E1 — Pretrained | Menggunakan pretrained weights, `imgsz=416` | Mengukur performa model dengan bobot awal pretrained |
| E2 — Scratch | Tanpa pretrained weights, `imgsz=416` | Membandingkan hasil pelatihan tanpa bobot pretrained |
| E3 — Tuning | Menggunakan pretrained weights, `imgsz=640` | Mengevaluasi pengaruh ukuran gambar yang lebih besar |

## 5. Hasil Eksperimen

Hasil berdasarkan file `hasil_praktik_4222411002.csv`:

| Metrik | E1 Pretrained | E2 Scratch | E3 Tuning |
|---|---:|---:|---:|
| mAP50 | 0.3493 | 0.0028 | 0.4366 |
| mAP50–95 | 0.1767 | 0.0007 | 0.2642 |
| Precision | 0.3363 | 0.6749 | 0.5509 |
| Recall | 0.3785 | 0.0151 | 0.4236 |
| Inferensi (ms) | 30.79 | 26.03 | 48.60 |
| Waktu latih (menit) | 20.84 | 17.32 | 36.34 |
| Ukuran gambar | 416 | 416 | 640 |

## 6. Analisis Hasil

Berdasarkan hasil eksperimen, E3 Tuning memperoleh nilai mAP50 sebesar 0.4366 dan mAP50–95 sebesar 0.2642. Nilai tersebut merupakan yang tertinggi di antara ketiga eksperimen.

E1 Pretrained memperoleh mAP50 sebesar 0.3493 dan mAP50–95 sebesar 0.1767. Sementara itu, E2 Scratch memperoleh nilai mAP50 sebesar 0.0028 dan mAP50–95 sebesar 0.0007. Hasil ini menunjukkan bahwa pada konfigurasi dan dataset yang digunakan, pelatihan tanpa pretrained weights belum menghasilkan performa deteksi yang baik.

E3 Tuning juga membutuhkan waktu pelatihan dan waktu inferensi yang lebih tinggi dibandingkan E1. Dengan demikian, peningkatan metrik deteksi pada eksperimen ini disertai peningkatan kebutuhan komputasi.

## 7. Struktur Repository

```text
RET503-Praktik-YOLO/
├── E1_pretrained/
│   └── results.png
├── E3_tuning/
│   └── results.png
├── hasil_praktik_4222411002.csv
├── hasil_praktik_4222411002.txt
└── README.md
```

Keterangan:
- `hasil_praktik_4222411002.csv`: tabel hasil perbandingan eksperimen.
- `hasil_praktik_4222411002.txt`: ringkasan hasil praktik.
- `E1_pretrained/results.png`: grafik hasil eksperimen E1.
- `E3_tuning/results.png`: grafik hasil eksperimen E3.

## 8. Kesimpulan

Berdasarkan tiga eksperimen yang dilakukan, E3 Tuning menghasilkan nilai mAP50 dan mAP50–95 tertinggi pada pengujian ini. Penggunaan pretrained weights dan ukuran gambar 640 memberikan hasil lebih baik dibandingkan konfigurasi E1 dan E2 pada dataset yang digunakan.

Namun, E3 membutuhkan waktu pelatihan lebih lama dan memiliki waktu inferensi lebih tinggi. Pemilihan konfigurasi model perlu mempertimbangkan keseimbangan antara akurasi deteksi dan kebutuhan komputasi.

## 9. Catatan

Hasil yang disajikan merupakan hasil eksperimen pada dataset dan konfigurasi praktik ini. Performa model pada dataset lain dapat berbeda.

