# **ANALISIS PERBANDINGAN CLUSTERING DASS (DEPRESSION ANXIETY STRESS) MENGGUNAKAN K-MEANS DAN GMM SEBELUM DAN SESUDAH PENYEIMBANGAN DATA DENGAN ADASYN**

## **Deskripsi Singkat Proyek**
Proyek ini bertujuan untuk menerapkan teknik **clustering** dalam mendeteksi potensi gangguan kesehatan mental pada mahasiswa menggunakan hasil survei **DASS** (Depression, Anxiety, Stress Scales). Pendekatan ini berbasis data, menggunakan algoritma **K-Means** dan **Gaussian Mixture Model (GMM)** untuk mengelompokkan mahasiswa berdasarkan tingkat risiko gangguan mental, serta membandingkan kinerja kedua metode tersebut dengan dan tanpa teknik penyeimbangan data **ADASYN**. **ADASYN** digunakan untuk mengatasi masalah ketidakseimbangan data, yang sering terjadi ketika kelompok dengan risiko tinggi lebih sedikit dibandingkan dengan kelompok risiko rendah atau sedang.

## **Latar Belakang Masalah**
Kesehatan mental merupakan salah satu aspek penting dalam kualitas hidup individu, terutama bagi mahasiswa yang tengah berada dalam fase transisi menuju kedewasaan dan karier profesional. Tekanan akademik, adaptasi sosial, dan ekspektasi dari lingkungan sekitar menjadi pemicu utama gangguan mental pada mahasiswa. Berdasarkan data dari World Health Organization (WHO), sekitar 12,5% dari total populasi dunia mengalami gangguan mental, dengan kelompok usia muda dewasa (termasuk mahasiswa) menjadi yang paling rentan.

Masalah ini semakin diperparah dengan hasil **Riset Kesehatan Dasar (Riskesdas) 2018** di Indonesia, yang menyebutkan bahwa gangguan mental emosional pada usia 15 tahun ke atas mencapai 9,8%. Beberapa kampus telah menyadari masalah ini, seperti **Universitas Negeri Semarang (UNNES)** yang telah mendirikan layanan konseling “Kawan Dengar” untuk mahasiswa. Oleh karena itu, pendekatan berbasis data-driven, seperti clustering, dapat menjadi langkah efektif untuk mendeteksi dan memahami kondisi psikologis mahasiswa.

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
Pastikan Anda memiliki **Python 3.x** dan beberapa pustaka yang diperlukan:
- `numpy`
- `pandas`
- `matplotlib`
- `seaborn`
- `sklearn`
- `imblearn`

Instal pustaka yang diperlukan menggunakan pip:
```bash
pip install numpy pandas matplotlib seaborn scikit-learn imbalanced-learn
