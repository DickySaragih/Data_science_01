# Proyek Akhir: Menyelesaikan Permasalahan Perusahaan Edutech

# **Bussines Understanding**
Perusahaan Jaya Jaya Maju merupakan salah satu perusahaan multinasional yang telah berdiri sejak tahun 2000. Perusahaan ini memiliki lebih dari 1000 karyawan yang tersebar di berbagai wilayah di Indonesia. Seiring dengan pertumbuhan perusahaan yang semakin besar, tantangan dalam pengelolaan sumber daya manusia (SDM) pun semakin kompleks. Salah satu tantangan utama yang dihadapi adalah tingginya attrition rate, yaitu rasio jumlah karyawan yang keluar dibandingkan dengan total keseluruhan karyawan.
Tingkat attrition yang melebihi angka 10% menjadi indikator bahwa terdapat permasalahan serius dalam pengelolaan dan retensi karyawan. Kondisi ini dapat berdampak langsung pada produktivitas, efisiensi operasional, serta menimbulkan biaya tambahan akibat proses rekrutmen dan pelatihan karyawan baru. Oleh karena itu, diperlukan sebuah pendekatan berbasis data untuk memahami faktor-faktor yang mempengaruhi tingginya tingkat attrition di perusahaan ini.
Departemen Human Resources (HR) Jaya Jaya Maju memiliki inisiatif untuk melakukan analisis prediktif guna mengidentifikasi faktor-faktor penting yang berkorelasi dengan keputusan karyawan untuk meninggalkan perusahaan. Selain itu, manajemen juga memerlukan dashboard bisnis interaktif yang dapat membantu memonitor faktor-faktor utama penyebab attrition secara real-time, sehingga pengambilan keputusan strategis dapat dilakukan secara lebih cepat dan tepat sasaran.
Sebagai bagian dari proyek ini, telah disediakan dataset terkait informasi karyawan yang dapat digunakan untuk proses analisis. Dataset tersebut dapat diunduh melalui tautan berikut: [dataset](https://github.com/dicodingacademy/dicoding_dataset/blob/main/employee/employee_data.csv)

### Permasalahan Bisnis.

Berdasarkan kode yang dianalisis, permasalahan bisnis utama yang dihadapi adalah **tingginya tingkat perputaran karyawan (employee attrition)** di perusahaan edutech. Tingkat perputaran karyawan yang tinggi dapat menyebabkan berbagai kerugian bagi perusahaan, antara lain:
1. Biaya Rekrutmen dan Pelatihan: Perusahaan harus mengeluarkan biaya yang signifikan untuk mencari, merekrut, dan melatih karyawan baru untuk menggantikan karyawan yang pergi.
2. Hilangnya Pengetahuan dan Pengalaman: Karyawan yang berpengalaman membawa pengetahuan dan keahlian berharga. Kepergian mereka dapat menyebabkan hilangnya institutional knowledge yang sulit digantikan.
3. Penurunan Produktivitas: Periode transisi saat karyawan baru beradaptasi dapat menurunkan produktivitas tim secara keseluruhan.
4. Peurunan Moral Karyawan: Tingkat perputaran yang tinggi dapat menciptakan ketidakstabilan dan menurunkan moral karyawan yang bertahan.
5. Citra Perusahaan yang Negatif: Tingkat perputaran yang tinggi dapat merusak reputasi perusahaan di mata calon karyawan. 
Perusahaan edutech ini ingin memahami faktor-faktor apa saja yang paling berkontribusi terhadap keputusan karyawan untuk keluar, dan yang terpenting, mereka ingin dapat memprediksi karyawan mana yang berisiko tinggi untuk keluar sehingga tindakan pencegahan proaktif dapat diambil untuk mempertahankan talenta terbaik mereka.

# **Cakupan Proyek**
Cakupan proyek ini mencakup tahapan-tahapan berikut:
1. Pengumpulan Data:Menggunakan data karyawan yang telah dikumpulkan oleh perusahaan. Dalam kasus ini, data diperoleh dari file CSV yang di-host di GitHub.
2. Pemahaman Data (Data Understanding): Melakukan eksplorasi awal data untuk memahami struktur, tipe data, distribusi variabel, dan mengidentifikasi potensi masalah seperti missing values. Memvisualisasikan hubungan antar variabel, khususnya dengan variabel target (Attrition).
3. Persiapan Data (Data Preparation): Membersihkan dan mengubah data agar siap untuk dimodelkan. Ini termasuk menangani missing values, menghapus kolom yang tidak relevan, melakukan encoding pada fitur kategorikal, dan melakukan normalisasi fitur numerik. Data juga akan dibagi menjadi set pelatihan dan pengujian.
5. Pemodelan (Modeling): Membangun model machine learning menggunakan algoritma klasifikasi (dalam kasus ini, Random Forest) untuk memprediksi kemungkinan karyawan mengalami Attrition.
6. Evaluasi Model (Evaluation): Mengukur kinerja model menggunakan metrik evaluasi yang relevan seperti Akurasi, Classification Report (Precision, Recall, F1-score), dan Confusion Matrix untuk menilai seberapa baik model dapat memprediksi kelas Attrition.
6. Analisis Hasil dan Interpretasi (Implicit in the code): Memahami faktor-faktor yang paling berkontribusi terhadap prediksi model melalui analisis feature importance. Hasil ini dapat memberikan wawasan bisnis tentang faktor-faktor yang mendorong Attrition.
7. Visualisasi Hasil: Mempresentasikan hasil evaluasi model dan insights dari feature importance dalam bentuk visual yang mudah dipahami.
Proyek ini **tidak mencakup** implementasi model ke dalam sistem produksi atau pengembangan strategi retensi karyawan berdasarkan hasil model (ini merupakan langkah lanjutan setelah proyek data science ini selesai). Fokus utamanya adalah membangun dan mengevaluasi model prediktif.

# **3. Persiapan**
ahapan persiapan yang diperlukan untuk menjalankan proyek ini meliputi:
1. Akses ke Data: Memastikan akses ke file data karyawan (`employee_data.csv`). Dalam kode ini, data diakses langsung dari URL GitHub, yang memerlukan koneksi internet.
2. Lingkungan Pengembangan: Menggunakan lingkungan yang mendukung eksekusi kode Python, seperti Google Colaboratory atau Jupyter Notebook.
3. Instalasi Library yang Dibutuhkan: Memastikan bahwa semua library Python yang digunakan dalam kode sudah terinstal. Berdasarkan import dalam kode, library yang dibutuhkan adalah:
   `pandas` untuk manipulasi data.
   `numpy` untuk komputasi numerik.
    `matplotlib.pyplot` untuk visualisasi dasar.
   `seaborn` untuk visualisasi statistik yang lebih menarik.
   `sklearn` (Scikit-learn) untuk machine learning, termasuk:\
   `train_test_split` dari `sklearn.model_selection`
   `LabelEncoder` dan `StandardScaler` dari `sklearn.preprocessing`
   `RandomForestClassifier` dari `sklearn.ensemble`
   `classification_report`, `confusion_matrix`, `accuracy_score` dari `sklearn.metrics`
4. Pemahaman Dasar Python: Memiliki pemahaman dasar tentang sintaks dan struktur bahasa pemrograman Python.
5. Pemahaman Dasar Konsep Data Science dan Machine Learning: Mengerti konsep dasar tentang data cleaning, preprocessing, pemodelan klasifikasi, dan metrik evaluasi.
6. Spesifikasi Komputer (Opsional, namun direkomendasikan untuk dataset yang lebih besar): Memiliki komputer atau lingkungan cloud dengan sumber daya (CPU, RAM) yang cukup untuk memuat dan memproses dataset, meskipun dataset dalam contoh ini relatif kecil.

