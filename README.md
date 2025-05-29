# 🧠 **Analisis Perbandingan Clustering DASS (Depression Anxiety Stress) Menggunakan K-Means dan GMM Sebelum dan Sesudah Penyeimbangan Data dengan ADASYN**

---

## 📋 **Deskripsi Singkat Proyek**

Proyek ini bertujuan menerapkan teknik **clustering** untuk mendeteksi potensi gangguan kesehatan mental pada mahasiswa menggunakan hasil survei **DASS** (Depression, Anxiety, Stress Scales).  
Metode yang digunakan adalah **K-Means** dan **Gaussian Mixture Model (GMM)** untuk mengelompokkan mahasiswa berdasarkan risiko gangguan mental, serta membandingkan kinerja kedua metode tersebut sebelum dan sesudah penyeimbangan data menggunakan **ADASYN**.  
**ADASYN** membantu mengatasi ketidakseimbangan data di mana jumlah responden berisiko tinggi biasanya lebih sedikit dibandingkan kelompok risiko rendah atau sedang.

---

## 📖 **Latar Belakang Masalah**

Kesehatan mental merupakan aspek penting dalam kualitas hidup, terutama bagi mahasiswa yang sedang mengalami fase transisi menuju kedewasaan dan karier profesional. Tekanan akademik, adaptasi sosial, dan ekspektasi lingkungan sekitar menjadi pemicu utama gangguan mental.  
Menurut data WHO, sekitar **12,5%** populasi dunia mengalami gangguan mental, termasuk mahasiswa sebagai kelompok yang rentan.  
Di Indonesia, **Riskesdas 2018** melaporkan gangguan mental emosional pada usia 15+ mencapai **9,8%**. Beberapa kampus seperti **UNNES** telah menyediakan layanan konseling “Kawan Dengar” sebagai upaya penanganan.  
Metode clustering dalam penelitian ini digunakan untuk deteksi dini dan pemahaman kondisi psikologis mahasiswa.

---

## 📊 **Deskripsi Dataset**

Dataset survei DASS yang digunakan terdiri dari **39.775 baris** dan **172 kolom**, berformat CSV, mencakup:
- **42 kolom skor DASS (Q1A–Q42A)** yang merepresentasikan tingkat depresi, kecemasan, dan stres.
- Kolom **demografis dan psikologis** lain seperti usia, jenis kelamin, dan skor kepribadian.

---

## ⚙️ **Algoritma yang Digunakan**

### K-Means Clustering  
Metode clustering berbasis centroid, mengelompokkan data berdasarkan jarak ke pusat cluster. Efektif untuk cluster dengan bentuk seragam dan jelas.

### Gaussian Mixture Model (GMM)  
Model probabilistik yang mengasumsikan data berasal dari campuran distribusi Gaussian. Lebih fleksibel dan mampu menangani cluster yang overlap.

### ADASYN (Adaptive Synthetic Sampling)  
Teknik penyeimbangan data dengan menghasilkan data sintetis pada kelas minoritas untuk mengurangi bias akibat ketidakseimbangan dataset.

---

## 🚀 **Panduan Menjalankan Kode**

### Prasyarat  
Pastikan pustaka Python berikut telah terpasang:  
`numpy`, `pandas`, `matplotlib`, `seaborn`, `scikit-learn`, `imbalanced-learn`  

Instalasi dengan:  
```bash
pip install numpy pandas matplotlib seaborn scikit-learn imbalanced-learn
```
# 🚀 Langkah-langkah Menjalankan Kode

Ikuti panduan berikut untuk menjalankan eksperimen clustering menggunakan dua notebook utama: satu tanpa penyeimbangan data dan satu dengan penyeimbangan data menggunakan ADASYN.

---

## 1️⃣ Menjalankan Eksperimen Tanpa Penyeimbangan Data

📂 **Notebook:** `clustering_tanpa_penyeimbangan.ipynb`

### Cara menjalankan:
- Buka notebook tersebut di Jupyter Notebook, JupyterLab, atau Google Colab.
- Jalankan setiap sel secara berurutan dengan menekan **Shift + Enter**.

### Apa yang akan dilakukan pada notebook ini?
- **Eksplorasi Data (EDA)**  
  Memahami struktur data, mengecek nilai yang hilang, dan mengevaluasi distribusi kelas responden.
  
- **Pembersihan Data**  
  Menghapus data yang tidak valid menggunakan **Vocabulary Check List (VCL)**.

- **Normalisasi Data**  
  Menggunakan **StandardScaler** untuk menstandarisasi fitur agar model tidak bias karena perbedaan skala.

- **Clustering dengan K-Means dan GMM**  
  Mengelompokkan data ke dalam cluster berdasarkan fitur yang sudah diproses.

- **Visualisasi Hasil**  
  Menggunakan **PCA** untuk mereduksi dimensi dan menampilkan hasil clustering dalam bentuk scatter plot.

---

## 2️⃣ Menjalankan Eksperimen dengan Penyeimbangan Data (ADASYN)

📂 **Notebook:** `clusteringg_dengan_adasyn.ipynb`

### Cara menjalankan:
- Buka notebook ini setelah menyelesaikan eksperimen tanpa penyeimbangan.
- Jalankan semua sel secara berurutan dengan **Shift + Enter**.

### Apa yang akan dilakukan pada notebook ini?
- **Penyeimbangan Data dengan ADASYN**  
  Menghasilkan data sintetis untuk kelas minoritas agar distribusi data lebih seimbang.

- **Clustering dengan K-Means dan GMM**  
  Melakukan clustering ulang pada data yang sudah diseimbangkan.

- **Evaluasi dan Visualisasi**  
  Menggunakan metrik **Silhouette Score** dan **BIC** (untuk GMM) untuk evaluasi kualitas cluster.  
  Visualisasi cluster dengan PCA untuk memudahkan interpretasi.

- **Perbandingan Hasil**  
  Membandingkan hasil clustering sebelum dan sesudah penyeimbangan untuk melihat dampak teknik ADASYN terhadap performa model.

---

### Tips:  
- Pastikan semua pustaka yang dibutuhkan sudah terpasang.  
- Jalankan kode secara berurutan agar tidak terjadi error.  
- Simpan dan dokumentasikan hasil clustering untuk analisis lebih lanjut.

## **Contoh Hasil Output dan Visualisasi**
Pada bagian ini, kami akan menunjukkan contoh hasil output dan visualisasi yang dihasilkan setelah menerapkan algoritma **K-Means** dan **Gaussian Mixture Model (GMM)** untuk clustering, serta evaluasi model dan visualisasi clustering menggunakan **PCA**.

## **Interpretasi dan Visualisasi Hasil**
Hasil clustering yang telah diperoleh divisualisasikan menggunakan **Principal Component Analysis (PCA)** untuk mereduksi dimensi data dan memudahkan pemahaman pola pemisahan antar cluster.
- **Visualisasi Scatter Plot** menunjukkan pemisahan yang jelas antar cluster.
- Analisis statistik terhadap distribusi skor **DASS** dan karakteristik **demografis** responden semakin memperkuat bahwa cluster yang terbentuk memiliki makna psikologis yang signifikan, yang memisahkan responden dengan tingkat depresi, kecemasan, dan stres yang berbeda.

![Clustering Tanpa ADASYN](visualisasi/tanpa_adasyn.png)

![Clustering dengan ADASYN](visualisasi/dengan_adasyn.png)

## **Kesimpulan**

Penelitian ini berhasil melakukan segmentasi responden berdasarkan data **Depression Anxiety Stress Scales (DASS)** menggunakan metode clustering **K-Means** dan **Gaussian Mixture Model (GMM)**. Berdasarkan hasil eksperimen yang dilakukan, berikut adalah beberapa kesimpulan utama yang dapat diambil:

## **Kualitas Data dan Preprocessing**
Proses preprocessing yang dilakukan terbukti sangat efektif dalam mempersiapkan dataset untuk analisis clustering. Langkah-langkah preprocessing meliputi:
- **Pembersihan Data**: Menggunakan **Vocabulary Check List (VCL)** untuk mendeteksi data tidak valid dan menghapus responden yang tidak memenuhi kriteria validitas.
- **Normalisasi Fitur**: Menggunakan **StandardScaler** untuk menormalisasi data sehingga semua fitur berada pada skala yang seragam, menghindari bias dalam model clustering.
- **Penanganan Ketidakseimbangan Data**: Dengan menggunakan teknik **ADASYN** untuk menghasilkan data sintetis pada kelas minoritas, sehingga distribusi data menjadi lebih seimbang dan menghasilkan clustering yang lebih representatif.

Dengan langkah-langkah ini, dataset yang digunakan memiliki kualitas yang lebih baik, yang memungkinkan model clustering menghasilkan hasil yang lebih akurat.

## **Pemilihan Metode Clustering**
Kedua metode clustering yang digunakan, yaitu **K-Means** dan **GMM**, berhasil mengelompokkan data ke dalam **empat cluster optimal** yang merepresentasikan tingkat kondisi psikologis responden, mulai dari **risiko rendah hingga tinggi**.
- **K-Means**: Memberikan hasil yang cukup jelas dalam hal pemisahan cluster, namun metode ini bergantung pada jarak centroid dan tidak dapat menangani overlapping cluster dengan baik.
- **Gaussian Mixture Model (GMM)**: Memberikan hasil yang lebih fleksibel dalam pengelompokan data dan lebih efektif dalam menangani data dengan tumpang tindih antar cluster, karena pendekatan probabilistik yang digunakannya.

## **Evaluasi Model dan Validitas Cluster**
Penentuan jumlah cluster optimal dilakukan dengan tiga pendekatan evaluasi yang berbeda:
- **Elbow Method**: Menunjukkan titik optimal pada jumlah cluster yang memberikan penurunan signifikan dalam nilai within-cluster sum of squares (WCSS).
- **Silhouette Score**: Mengukur seberapa baik data cocok dengan klaster yang ada, di mana nilai yang lebih tinggi menunjukkan kualitas clustering yang lebih baik.
- **Bayesian Information Criterion (BIC)**: Digunakan untuk GMM dan membantu dalam memilih model dengan jumlah komponen yang optimal.

Penilaian menggunakan **Silhouette Score** yang baik dan **peningkatan** setelah penggunaan ADASYN menegaskan bahwa model menghasilkan clustering yang memadai dan valid secara statistik.

Secara keseluruhan, model clustering ini berhasil mengelompokkan mahasiswa berdasarkan tingkat risiko gangguan mental mereka, memberikan dasar yang kuat untuk pengembangan sistem deteksi dini dan pencegahan gangguan mental di kalangan mahasiswa.
