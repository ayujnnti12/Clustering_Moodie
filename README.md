# **ANALISIS PERBANDINGAN CLUSTERING DASS (DEPRESSION ANXIETY STRESS) MENGGUNAKAN K-MEANS DAN GMM SEBELUM DAN SESUDAH PENYEIMBANGAN DATA DENGAN ADASYN**

## **Deskripsi Singkat Proyek**
Proyek ini bertujuan untuk menerapkan teknik **clustering** dalam mendeteksi potensi gangguan kesehatan mental pada mahasiswa menggunakan hasil survei **DASS** (Depression, Anxiety, Stress Scales). Pendekatan ini berbasis data, menggunakan algoritma **K-Means** dan **Gaussian Mixture Model (GMM)** untuk mengelompokkan mahasiswa berdasarkan tingkat risiko gangguan mental, serta membandingkan kinerja kedua metode tersebut dengan dan tanpa teknik penyeimbangan data **ADASYN**. **ADASYN** digunakan untuk mengatasi masalah ketidakseimbangan data, yang sering terjadi ketika kelompok dengan risiko tinggi lebih sedikit dibandingkan dengan kelompok risiko rendah atau sedang.

## **Latar Belakang Masalah**
Kesehatan mental merupakan salah satu aspek penting dalam kualitas hidup individu, terutama bagi mahasiswa yang tengah berada dalam fase transisi menuju kedewasaan dan karier profesional. Tekanan akademik, adaptasi sosial, dan ekspektasi dari lingkungan sekitar menjadi pemicu utama gangguan mental pada mahasiswa. Berdasarkan data dari World Health Organization (WHO), sekitar 12,5% dari total populasi dunia mengalami gangguan mental, dengan kelompok usia muda dewasa termasuk mahasiswa menjadi yang paling rentan.

Masalah ini semakin krusial dengan hasil **Riset Kesehatan Dasar (Riskesdas) 2018** di Indonesia, yang menyebutkan bahwa gangguan mental emosional pada usia 15 tahun ke atas mencapai 9,8%. Beberapa kampus telah menyadari masalah ini, seperti **Universitas Negeri Semarang (UNNES)** yang telah mendirikan layanan konseling “Kawan Dengar” untuk mahasiswa. Oleh karena itu, metode clustering yang digunakan dapat menjadi langkah efektif untuk mendeteksi dan memahami kondisi psikologis mahasiswa.

Pada penelitian ini, dua metode clustering, yaitu **K-Means** dan **GMM**, diterapkan untuk mengelompokkan mahasiswa berdasarkan tingkat risiko gangguan mental mereka. Salah satu tantangan yang dihadapi dalam clustering adalah masalah ketidakseimbangan data, yang dapat mengarah pada hasil yang bias. Oleh karena itu, teknik penyeimbangan data **ADASYN** digunakan untuk meningkatkan kualitas hasil clustering.

## **Deskripsi Dataset**
Dataset yang digunakan dalam penelitian ini berasal dari survei DASS yang mengukur tingkat depresi, kecemasan, dan stres mahasiswa. Dataset ini memiliki format **CSV** yang memuat 39.775 baris dan 172 kolom, dengan fitur-fitur seperti skor untuk masing-masing aspek DASS (Depresi, Kecemasan, Stres), informasi demografis, dan faktor psikologis lainnya. Data ini digunakan untuk mengelompokkan mahasiswa ke dalam cluster berdasarkan risiko gangguan mental mereka.

File dataset **`data.csv`** berisi:
- **42 kolom terkait skor DASS (Q1A-Q42A)** yang mewakili hasil survei pada masing-masing kategori.
- **Kolom demografis dan psikologis** lainnya yang meliputi usia, jenis kelamin, dan skor terkait kepribadian.

## **Algoritma yang Digunakan**

### **K-Means Clustering**
**K-Means** adalah algoritma clustering berbasis centroid yang mengelompokkan data ke dalam sejumlah cluster berdasarkan kedekatannya dengan pusat cluster (centroid). K-Means efektif untuk mengelompokkan data yang memiliki bentuk cluster yang jelas dan seragam.

### **Gaussian Mixture Model (GMM)**
**GMM** adalah model probabilistik yang mengasumsikan bahwa data berasal dari distribusi Gaussian campuran. GMM lebih fleksibel dibandingkan K-Means, karena dapat menangani data dengan distribusi yang tidak berbentuk bulat dan dapat menangani cluster yang tumpang tindih (overlap).

### **ADASYN (Adaptive Synthetic Sampling)**
**ADASYN** digunakan untuk menyeimbangkan dataset yang tidak seimbang, terutama ketika jumlah kelas minoritas lebih sedikit. **ADASYN** menghasilkan data sintetis berdasarkan distribusi lokal data minoritas, sehingga menghasilkan segmentasi yang lebih akurat dan representatif.

## **Panduan Menjalankan Kode**

### **Prasyarat**
Pastikan telah menginstall beberapa pustaka yang diperlukan:
- `numpy`
- `pandas`
- `matplotlib`
- `seaborn`
- `sklearn`
- `imblearn`

Instal pustaka yang diperlukan menggunakan pip:
pip install numpy pandas matplotlib seaborn scikit-learn imbalanced-learn

### **Langkah-langkah Menjalankan Kode**
1. Menjalankan Eksperimen Tanpa Penyeimbangan Data 
- Buka notebook `clustering_tanpa_penyeimbangan.ipynb`.
- Jalankan setiap sel di notebook secara berurutan dengan menekan Shift + Enter.
- Pada notebook ini, lakukan eksplorasi data (EDA), pembersihan data, normalisasi, dan menerapkan K-Means dan Gaussian Mixture Model (GMM) untuk clustering.
- Langkah-langkah dalam notebook ini:

Eksplorasi Data (EDA): Memahami struktur data, memeriksa nilai hilang, dan mengevaluasi distribusi kelas.

Pembersihan Data: Menghapus data yang tidak valid menggunakan teknik Vocabulary Check List (VCL).

Normalisasi: Menggunakan StandardScaler untuk menstandarisasi fitur sehingga model tidak bias terhadap fitur dengan skala yang lebih besar.

Clustering: Menggunakan K-Means dan GMM untuk melakukan clustering pada dataset yang telah diproses.

Visualisasi: Melakukan PCA untuk mereduksi dimensi data dan menampilkan hasil clustering dalam bentuk scatter plot.

2. Menjalankan Eksperimen dengan Penyeimbangan Data (ADASYN)
- Setelah eksperimen tanpa penyeimbangan selesai, buka notebook `clusteringg_dengan_adasyn.ipynb`.
- Jalankan setiap sel secara berurutan dengan menekan Shift + Enter.
- Pada notebook ini, mengimplementasikan teknik ADASYN untuk menyeimbangkan data dan mengulang eksperimen clustering dengan K-Means dan GMM.
- Langkah-langkah dalam notebook ini:

Penyeimbangan Data dengan ADASYN: Menggunakan ADASYN untuk menyeimbangkan dataset dengan menghasilkan data sintetis pada kelas minoritas.

Clustering dengan ADASYN: Setelah data diseimbangkan, lakukan eksperimen clustering menggunakan K-Means dan GMM seperti pada eksperimen sebelumnya.

Evaluasi dan Visualisasi: Evaluasi dilakukan menggunakan Silhouette Score dan BIC untuk GMM. Visualisasi clustering dilakukan menggunakan PCA yang sama seperti eksperimen sebelumnya.

Perbandingan Hasil: Di sini dapat membandingkan hasil clustering sebelum dan sesudah penyeimbangan data, serta melihat peningkatan kinerja.

## **Contoh Hasil Output dan Visualisasi**
Pada bagian ini, kami akan menunjukkan contoh hasil output dan visualisasi yang dihasilkan setelah menerapkan algoritma **K-Means** dan **Gaussian Mixture Model (GMM)** untuk clustering, serta evaluasi model dan visualisasi clustering menggunakan **PCA**.

## **Interpretasi dan Visualisasi Hasil**
Hasil clustering yang telah diperoleh divisualisasikan menggunakan **Principal Component Analysis (PCA)** untuk mereduksi dimensi data dan memudahkan pemahaman pola pemisahan antar cluster.
- **Visualisasi Scatter Plot** menunjukkan pemisahan yang jelas antar cluster.
- Analisis statistik terhadap distribusi skor **DASS** dan karakteristik **demografis** responden semakin memperkuat bahwa cluster yang terbentuk memiliki makna psikologis yang signifikan, yang memisahkan responden dengan tingkat depresi, kecemasan, dan stres yang berbeda.

![Deskripsi Gambar](images/dengan adasyn.png)

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
