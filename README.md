# 🌱 Smart Plant Monitoring & AI Detection System

Sistem pemantauan kesehatan tanaman dan klasifikasi penyakit daun interaktif berbasis **Streamlit**, **OpenCV (Ruang Warna HSV & Operasi Morfologi)**, serta **PyTorch Deep Learning (MobileNetV2)** dengan umpan balik suara otomatis (*Text-to-Speech* Bahasa Indonesia).

---

## 👤 Pengembang Proyek

* **Nama:** Ahmad Maulana (Alan)
* **NIM:** E41241323
* **Program Studi:** D4 Teknik Informatika
* **Jurusan:** Teknologi Informasi
* **Institusi:** Politeknik Negeri Jember

---

## 🚀 Fitur Utama

1. **Dual Segmentation (HSV Color Space):**
   * Segmentasi warna hijau daun sehat ($\text{Hue } 25\text{--}95$).
   * Segmentasi warna kuning/cokelat untuk daun kering atau layu ($\text{Hue } 15\text{--}30$).
2. **Operasi Morfologi (Opening & Closing):**
   * Membersihkan *noise* piksel latar belakang serta menutup celah lubang pada objek daun secara dinamis via *slider* ukuran kernel.
3. **AI Disease Classification (PyTorch MobileNetV2):**
   * Mengklasifikasikan jenis daun dan infeksi penyakit tanaman secara presisi menggunakan model *pre-trained*.
4. **Automated Voice Feedback (macOS TTS):**
   * Penyuaran status kesehatan daun otomatis dalam Bahasa Indonesia menggunakan suara *Damayanti*.
5. **Streamlit Interactive GUI & Un-mirror Camera:**
   * Antarmuka web modern dengan fitur perbaikan tampilan kamera browser agar tidak terbalik (*un-mirror*).
6. **Data Logging System:**
   * Penyimpanan riwayat pengamatan otomatis ke format CSV (`hasil_monitoring.csv`) dan ekspor citra *mask* segmentasi (`.png`).

---

## 📂 Struktur Repositori

```text
Smart-Plant-Monitoring-AI_Alan_E41241323/
├── app_praktikum_streamlit.py   # Aplikasi utama berbasis Streamlit Web GUI
├── detect_webcam_praktikum.py   # Aplikasi pemantauan live camera berbasis OpenCV Native
├── detect_webcam.py             # Skrip deteksi dasar cepat (OpenCV + AI)
├── train.py                     # Skrip pelatih model AI MobileNetV2
├── model_daun.pth               # File bobot model PyTorch yang sudah dilatih
├── PlantVillage/                # Dataset citra daun (train/val)
└── outputsApp/                  # Direktori luaran penyimpanan
    ├── hasil_monitoring.csv     # Rekapitulasi data riwayat pemantauan
    └── masks/                   # Berkas simpanan mask segmentasi citra
