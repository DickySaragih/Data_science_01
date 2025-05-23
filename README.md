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

2. Apakah karyawan dengan penghasilan bulanan rendah lebih rentan mengalami attrition dibandingkan karyawan dengan penghasilan tinggi?

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
5. Pemahaman Dasar Konsep Data Science dan Machine Learning adapun proses cakupanya sebagai berikut:
**Import Library:**
Tahap pertama dalam proyek ini adalah mengimpor library Python yang dibutuhkan. Library seperti pandas digunakan untuk manipulasi dan analisis data tabular, numpy untuk komputasi numerik, matplotlib.pyplot dan seaborn untuk visualisasi data. Selain itu, library dari sklearn diimpor untuk keperluan pemisahan data, *preprocessing*, pemodelan, dan evaluasi model. Penggunaan library ini sangat penting karena menyediakan fungsi-fungsi siap pakai yang mempercepat dan mempermudah proses pengolahan data, mulai dari membaca data, membersihkan data, hingga membangun dan mengevaluasi model machine learning.
**Load Dataset:**
Dataset yang akan dianalisis dimuat ke dalam *environment* kerja. Dalam proyek ini, dataset dimuat langsung dari *repository* GitHub menggunakan URL. Memuat dataset adalah langkah krusial karena merupakan sumber data utama yang akan diolah. Proses ini memastikan bahwa data tersedia dan dapat diakses untuk tahapan-tahapan berikutnya.
**Data Understanding:**
Setelah dataset berhasil dimuat, dilakukan tahap pemahaman data. Langkah ini melibatkan pemeriksaan dasar terhadap struktur dan isi dataset. Informasi yang diperoleh meliputi ukuran dataset (df.shape), tipe data setiap kolom (df.info()), statistik deskriptif kolom numerik (df.describe()), dan jumlah nilai yang hilang (df.isnull().sum()). Tahap pemahaman data ini sangat penting untuk mendapatkan gambaran awal mengenai karakteristik data, mengidentifikasi potensi masalah seperti nilai yang hilang atau tipe data yang tidak sesuai, serta memahami distribusi data. Pemahaman yang baik tentang data akan memandu langkah-langkah selanjutnya dalam proses *preprocessing* dan pemodelan.
**Cleaning Data:**
Tahap pembersihan data (data cleaning) dilakukan untuk menangani isu-isu kualitas data yang teridentifikasi pada tahap pemahaman data. Dalam proyek ini, baris-baris yang memiliki nilai kosong pada kolom target Attrition dihapus (df = df.dropna(subset=['Attrition'])). Penghapusan ini dilakukan untuk memastikan bahwa semua *instance* yang digunakan dalam analisis dan pemodelan memiliki label target yang lengkap dan valid, yang krusial untuk pelatihan model klasifikasi.
**Exploratory Data Analysis (EDA):**
Meskipun tidak secara eksplisit ditunjukkan di *code* yang diberikan, tahap selanjutnya yang umum dilakukan adalah EDA. EDA bertujuan untuk menggali wawasan mendalam dari data melalui visualisasi dan analisis statistik deskriptif lebih lanjut. EDA dapat mencakup pembuatan histogram untuk melihat distribusi fitur, *boxplot* untuk mengidentifikasi *outlier*, *scatter plot* untuk melihat hubungan antar fitur, serta analisis korelasi. Alasan melakukan EDA adalah untuk memahami pola dalam data, mengidentifikasi hubungan antar variabel, dan menemukan *insight* yang dapat digunakan untuk menginformasikan pilihan fitur dan strategi pemodelan.
**Data Preparation:**
Tahap persiapan data melibatkan serangkaian transformasi untuk membuat data siap digunakan oleh algoritma machine learning. Dalam *code* yang diberikan, salah satu langkah yang dilakukan adalah mengubah tipe data kolom Attrition menjadi integer (df['Attrition'] = df['Attrition'].astype(int)) agar sesuai dengan format yang dibutuhkan oleh model klasifikasi. Selain itu, kolom-kolom yang dianggap tidak relevan seperti EmployeeId, Over18, StandardHours, dan EmployeeCount dihapus (df.drop(columns=cols_to_drop, inplace=True, errors='ignore')) untuk mengurangi dimensi data dan menghilangkan fitur yang tidak informatif. Tahap persiapan data juga biasanya mencakup penanganan variabel kategorikal (misalnya dengan *encoding* seperti *One-Hot Encoding* atau *Label Encoding*) dan *scaling* fitur numerik (misalnya menggunakan StandardScaler) untuk memastikan bahwa semua fitur berada dalam skala yang serupa, yang dapat meningkatkan kinerja beberapa algoritma machine learning. Data kemudian dipisahkan menjadi data pelatihan (train_test_split) untuk melatih model dan data pengujian untuk mengevaluasi kinerja model pada data yang belum pernah dilihat sebelumnya.
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

**kesimpulan**
Melalui proyek analisis prediktif ini, perusahaan Jaya Jaya Maju berhasil memperoleh pemahaman yang lebih mendalam mengenai penyebab utama tingginya tingkat attrition di lingkungan kerja. Dengan menggabungkan teknik data science, machine learning (Random Forest), dan dashboard interaktif Metabase, tim HR dapat mengidentifikasi faktor risiko utama secara kuantitatif dan visual.
Temuan Utama dari Dashboard Visualisasi:
1. Apakah terdapat hubungan antara lembur (OverTime) dan tingkat attrition?:
- Berdasarkan grafik pertama, terlihat bahwa karyawan yang bekerja lembur (OverTime = Yes) memiliki tingkat attrition jauh lebih tinggi dibandingkan yang tidak lembur.
- Meskipun total karyawan yang lembur lebih sedikit, jumlah attrition-nya sangat tinggi, dengan attrition rate yang jauh lebih besar dibandingkan kelompok non-lembur.
- Hal ini menandakan bahwa kelelahan kerja akibat lembur menjadi faktor penting dalam keputusan resign.
2.Apakah karyawan dengan penghasilan bulanan rendah lebih rentan mengalami attrition dibandingkan karyawan dengan penghasilan tinggi?
- Visualisasi kedua menunjukkan distribusi attrition berdasarkan lama kerja sejak promosi terakhir.
- Karyawan dengan masa kerja 3 tahun sejak promosi terakhir memiliki proporsi attrition terbesar (19.07%), disusul oleh mereka yang sudah 15 tahun dan 1 tahun sejak promosi terakhir. Ini menunjukkan adanya pola bahwa karyawan yang terlalu lama tidak dipromosikan atau tidak mendapat pengakuan atas kontribusinya lebih cenderung untuk meninggalkan perusahaan.
3. Apakah lama bekerja dan waktu sejak promosi terakhir memengaruhi keputusan untuk keluar?
- Dari grafik ketiga, karyawan dengan penghasilan rendah (Low Income) memiliki tingkat attrition tertinggi dibandingkan kelompok Medium dan High Income.
- Hal ini mengindikasikan bahwa ketidakpuasan finansial menjadi pemicu signifikan terhadap turnover, dan peningkatan kompensasi dapat menjadi strategi retensi yang efektif.

Tingkat Penghasilan Bulanan:
**akses akun metabase**
**email : dickysaragih050901@gmail.com
password : dickycandidsaragih5**
berikut merupakan link dashboard: https://localhost:3000/public/dashboard/e2427448-b421-418e-99cc-9b4c6c605660
