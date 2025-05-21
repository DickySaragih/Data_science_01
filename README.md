# Proyek Akhir: Menyelesaikan Permasalahan Perusahaan Edutech

# **Bussines Understanding**
Perusahaan Jaya Jaya Maju merupakan salah satu perusahaan multinasional yang telah berdiri sejak tahun 2000. Perusahaan ini memiliki lebih dari 1000 karyawan yang tersebar di berbagai wilayah di Indonesia. Seiring dengan pertumbuhan perusahaan yang semakin besar, tantangan dalam pengelolaan sumber daya manusia (SDM) pun semakin kompleks. Salah satu tantangan utama yang dihadapi adalah tingginya attrition rate, yaitu rasio jumlah karyawan yang keluar dibandingkan dengan total keseluruhan karyawan.
Tingkat attrition yang melebihi angka 10% menjadi indikator bahwa terdapat permasalahan serius dalam pengelolaan dan retensi karyawan. Kondisi ini dapat berdampak langsung pada produktivitas, efisiensi operasional, serta menimbulkan biaya tambahan akibat proses rekrutmen dan pelatihan karyawan baru. Oleh karena itu, diperlukan sebuah pendekatan berbasis data untuk memahami faktor-faktor yang mempengaruhi tingginya tingkat attrition di perusahaan ini.
Departemen Human Resources (HR) Jaya Jaya Maju memiliki inisiatif untuk melakukan analisis prediktif guna mengidentifikasi faktor-faktor penting yang berkorelasi dengan keputusan karyawan untuk meninggalkan perusahaan. Selain itu, manajemen juga memerlukan dashboard bisnis interaktif yang dapat membantu memonitor faktor-faktor utama penyebab attrition secara real-time, sehingga pengambilan keputusan strategis dapat dilakukan secara lebih cepat dan tepat sasaran.
Sebagai bagian dari proyek ini, telah disediakan dataset terkait informasi karyawan yang dapat digunakan untuk proses analisis. Dataset tersebut dapat diunduh melalui tautan berikut: [dataset](https://github.com/dicodingacademy/dicoding_dataset/blob/main/employee/employee_data.csv)

### Permasalahan Bisnis.

Permasalahan utama yang dihadapi perusahaan adalah:
1. Tingginya tingkat attrition (>10%) yang menunjukkan ketidakstabilan dalam retensi karyawan.
2. Kurangnya pemahaman mengenai faktor-faktor utama yang menyebabkan karyawan meninggalkan perusahaan.
3. Minimnya sistem monitoring yang mudah dipahami untuk membantu pengambilan keputusan strategis oleh manajemen HR.

# **Cakupan Proyek**
Proyek ini dirancang untuk menjawab dan memvisualisasikan beberapa pertanyaan kunci yang ditujukan untuk memahami fenomena attrition di perusahaan Jaya Jaya Maju. Adapun pertanyaan dan cakupan analisis adalah sebagai berikut:
1. Apakah terdapat hubungan antara lembur (OverTime) dan tingkat attrition?
Cakupan: Menganalisis distribusi attrition berdasarkan status lembur karyawan.

2. Bagaimana pengaruh kepuasan kerja (Job Satisfaction) terhadap kemungkinan karyawan keluar?
Cakupan: Menganalisis tingkat rata-rata attrition berdasarkan skor kepuasan kerja.

3. Apakah lama bekerja dan waktu sejak promosi terakhir memengaruhi keputusan untuk keluar?
Cakupan: Membuat heatmap dua variabel waktu (YearsAtCompany dan YearsSinceLastPromotion) terhadap rasio attrition.

# **Persiapan**
Tahapan persiapan yang diperlukan untuk menjalankan proyek ini meliputi:
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
**Setup environtment yang digunakan dalam proyek sebagai berikut**

1.  **pandas:** Untuk manipulasi dan analisis data (membaca CSV, membersihkan data, transformasi, dll.).
2.  **numpy:** Untuk operasi numerik, terutama dalam konteks array dan perhitungan matematis.
3.  **matplotlib.pyplot:** Untuk membuat visualisasi data (plot, grafik).
4.  **seaborn:** Untuk membuat visualisasi statistik yang lebih menarik dan informatif.
5.  **sklearn (scikit-learn):** Pustaka utama untuk Machine Learning, digunakan untuk:
    *   `sklearn.model_selection.train_test_split`: Membagi data menjadi set pelatihan dan pengujian.
    *   `sklearn.preprocessing.LabelEncoder`: Melakukan encoding pada variabel kategorikal.
    *   `sklearn.preprocessing.StandardScaler`: Melakukan standarisasi/normalisasi pada fitur numerik.
    *   `sklearn.ensemble.RandomForestClassifier`: Membangun model klasifikasi Random Forest.
    *   `sklearn.metrics`: Menghitung metrik evaluasi model (classification_report, confusion_matrix, accuracy_score).
      
# Business Dashboard
Perusahaan Jaya Jaya Maju, sebagai salah satu perusahaan multinasional dengan lebih dari 1.000 karyawan, saat ini menghadapi tantangan serius dalam mengelola tenaga kerjanya. Salah satu indikator utama yang menjadi perhatian adalah tingginya angka attrition atau tingkat keluar-masuk karyawan yang telah mencapai lebih dari 10%. Untuk membantu departemen Human Resources (HR) dalam memahami akar permasalahan tersebut, telah dikembangkan sebuah business dashboard interaktif menggunakan Metabase. Dashboard ini menyajikan analisis menyeluruh terhadap berbagai faktor yang dapat memengaruhi keputusan karyawan untuk keluar dari perusahaan.
Dashboard ini dirancang dengan tiga fokus utama analisis. Pertama, visualisasi distribusi attrition berdasarkan departemen, jenis kelamin, dan status lembur (OverTime). Dari data yang ditampilkan, dapat dilihat bahwa karyawan di beberapa departemen tertentu, seperti Sales dan Research & Development, memiliki tingkat attrition lebih tinggi, terutama jika mereka juga bekerja lembur secara rutin. Kedua, dashboard menampilkan hubungan antara kepuasan kerja (JobSatisfaction) dan tingkat attrition, yang menunjukkan bahwa karyawan dengan tingkat kepuasan rendah memiliki kecenderungan lebih besar untuk meninggalkan perusahaan. Ketiga, analisis juga dilakukan terhadap hubungan antara masa kerja (YearsAtCompany), waktu sejak promosi terakhir (YearsSinceLastPromotion), dan tingkat attrition. Hasilnya menunjukkan bahwa karyawan yang telah bekerja cukup lama tanpa mendapatkan promosi memiliki risiko keluar yang lebih tinggi.
Visualisasi yang digunakan pada dashboard ini meliputi bar chart, line chart, dan heatmap, serta dilengkapi dengan fitur filter interaktif seperti Department, Gender, dan OverTime. Hal ini memudahkan manajemen untuk melihat data berdasarkan kelompok tertentu secara real-time. Dengan dashboard ini, HR dapat lebih cepat mengenali pola yang mengarah pada tingginya attrition, serta mengambil langkah strategis seperti peningkatan kesejahteraan, kebijakan promosi yang lebih adil, dan pengurangan beban kerja lembur. Secara keseluruhan, dashboard ini menjadi alat bantu penting dalam pengambilan keputusan berbasis data (data-driven decision making) dan meningkatkan retensi karyawan di Jaya Jaya Maju.
berikut merupakan link dashboard: https://localhost:3000/public/dashboard/e15e027b-c6d8-40e3-9abb-e806f1ef6047
