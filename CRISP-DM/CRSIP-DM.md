Project DAMI : Predicting Employee’s Performance with Apriori Algorithm

# 1. Business Understanding
Tahap pertama pada metodologi CRISP-DM untuk melakukan prediksi kinerja karyawan adalah business understanding. Pada bab ini akan dijelaskan pemahaman mengenai substansi dari aktivitas data mining yang akan dilaksanakan serta kebutuhan dari perspektif bisnis. Aktivitasnya antara lain menentukan sasaran bisnis, memahami situasi bisnis, menerjemahkan tujuan atau sasaran bisnis ke dalam tujuan data mining.

## 1.1 Determine Bussiness Objective
Saat ini, banyak organisasi atau perusahaan yang berupaya untuk meningkatkan kualitas dari perusahaannya. Organisasi mencoba untuk mengenali faktor-faktor apa saja yang menjadi pengaruh kemajuan perusahaan mereka. Salah satu faktor penting yang menunjang kemajuan suatu perusahaan adalah sumber daya manusia ataupun karyawan yang dipekerjakan. Hal ini dapat dilihat pada berbagai test yang harus diselesaikan oleh pelamar kerja untuk mendapatkan suatu posisi atau jabatan dalam perusahaan. Dengan kata lain, perusahaan mencoba untuk menemukan karyawan yang tepat untuk membantu mereka dalam mengembangkan bisnis atau perusahaan[1]. Dalam menangani kualitas sumber daya manusia, umumnya perusahaan memiliki Human Resource Departement (HRD). HRD bertugas untuk merekrut dan menyeleksi pelamar kerja serta memastikan para karyawan yang bekerja mematuhi seluruh kebijakan yang ditetapkan oleh perusahaan. Selain itu, HRD juga berperan dalam melakukan evaluasi terhadap kinerja dari setiap karyawan yang bertujuan untuk memberikan penghargaan bagi pekerja, mengetahui kinerja dari setiap karyawan untuk selanjutnya digunakan dalam pengembangan kualitas sumber daya manusia.
HRD sebagai bagian yang berperan dalam memanajemen sumber daya manusia, perlu memperhatikan faktor apa saja yang berpengaruh terhadap kinerja dari karyawan perusahaan. Dalam mengevaluasi kinerja karyawan ada berbagai faktor yang terlibat, baik itu faktor dari karyawan maupun faktor dari perusahaan tersebut. Dari berbagai faktor tersebut, HRD perlu mengetahui faktor-faktor apa saja yang sangat berpengaruh dalam menentukan kinerja karyawan tersebut sehingga perusahaan mampu meningkatkan kemajuannya. 
HRD perlu menganalisis semua data terkait karyawan yang terdapat pada perusahaan tersebut, baik itu karyawan yang masih bekerja ataupu yang telah keluar dari perusahaan tersebut. Dalam kurun waktu yang lama setelah perusahaan berdiri, tentunya akan semakin banyak data karyawan yang perlu dianalisis untuk mengetahui faktor yang berpengaruh terhadap kinerja karyawan. Oleh karena itu, perlu dilakukan sebuah metode untuk menganalisis hal-hal apa saja yang berdampak pada kinerja karyawan tersebut, seberapa baikkah atau seberapa burukkah hal tersebut mempengaruhi kinerja dari karyawan. Dengan mengetahui hal tersebut, HRD dapat melakukan evaluasi terhadap hal-hal yang berpengaruh untuk ke depannya dapat meningkatkan kinerja dari setiap karyawan perusahaan tersebut. 

Sehingga objektif yang akan dicapai dari proyek ini adalah:
•	Menemukan faktor-faktor apa saja yang berpengaruh terhadap kinerja karwayan
•	Meningkatkan kinerja karyawan dengan mengevaluasi faktor yang berpengaruh terhadap kinerja

Proyek tersebut akan dikatakan sukses jika:
•	Ditemukan faktor-faktor yang berpengaruh terhadap kinerja karyawan
•	Proyek selesai dikerjakan dengan on time dan under budget.

## 1.2 Situation Assesment
Dalam pengerjaan proyek ini, perlu ditentukan ketersediaan sumber daya mencakup hardware, data sources, dan personel. Hardware yang digunakan untuk mengerjakan project tersebut adalah Laptop Lenovo Ideapad 310 dengan i5-7200 microprocessor dan 8GB RAM. Dataset yang akan dianalisis pada pengerjaan proyek ini adalah data employee yang diperoleh dari link: https://www.kaggle.com/shivan118/hranalysis?select=train.csv. Data tersebut merupakan data yang bersifat statis karena dalam format file CSV (Comma Separated Values) dan tidak ada data lebih lanjut yang akan dikumpulkan pada dataset tersebut dan metadata untuk dataset tersebut tidak tersedia. Selain itu, terkait personel yang dibutuhkan dalam pengerjaan proyek ini adalah 3 orang mahasiswa yang terlibat dalam setiap proses dalam proyek ini, baik itu dalam proses business understanding, data understanding, data preparation, modeling, evaluation, dan deployment.

Selain itu, asumsi dalam pengerjaan proyek ini adalah bahwa team management hanya perlu memahami hasil yang akan diperoleh dengan kata lain tidak perlu memahami model yang digunakan untuk pengklasifikasian.  Untuk risiko dalam pengerjaan proyek ini tidak terlalu signifikan. Projek akan dikerjakan secara daring oleh personel selama kurang lebih 4 minggu pengerjaan. Oleh karena itu, personel perlu berusaha dengan baik untuk memaksimalkan waktu dan sumber daya yang tersedia dalam pengerjaan proyek. Risiko lainnya yang mungkin terjadi adalah terkait masalah data, masalah teknologi. Namun hal tersebut masih memungkinkan untuk diatasi dengan baik. Cost/Benefit analysis juga perlu diperhatikan dalam pengerjaan proyek ini. Estimasi cost yang diperlukan mencakup pengumpulan data dan biaya operasi (berupa biaya akses internet). Sementara itu benefit yang diperoleh adalah mampu mencapai objektif utama, menambah wawasan yang diperoleh dari pemahaman data maupun pemahaman dalam tahapan pengerjaan proyek.

## 1.3 Determine Data Mining Goal
Tujuan bisnis pada penelitian ini untuk memprediksi bagaimana kinerja sumber daya manusia (karyawan) adalah menemukan faktor apa saja yang mempengaruhi kinerja karwayan serta melakukan evaluasi terhadap hubungan beberapa faktor yang berpengaruh terhadap kinerja karyawan. Manfaat dari penelitian ini yakni dapat menentukan karyawan yang berhak mendapatkan penghargaan, memberikan motivasi kepada karyawan, mengembangkan kualitas kerja dan potensi diri karyawan serta mengambil keputusan untuk menghentikan hubungan kerja terhadap karyawan. Sehingga penilaian kinerja karyawan dapat menjadi data acuan untuk evaluasi perusahaan di masa mendatang dalam mencapai tujuan bisnis perusahaan.  Dalam memprediksi tingkat kinerja karyawan diperlukan teknis penilaian yang efektif untuk mendapatkan keputusan secara subjektif. Maka dalam penelitian ini diterapkan suatu model yang dapat mengidentifikasi pola hubungan antara data. Model tersebut dapat dibentuk dengan metode data mining.
Data mining merupakan suatu proses untuk menemukan pola yang menarik dari data yang berjumlah besar[3]. Data mining task dikelompokkan menjadi description, estimation, prediction, classification, clustering, dan association [4]. Berdasarkan definisi data mining tersebut, data mining yang diterapkan pada penelitian ini merupakan proses menambang atau mengumpulkan data penilaian kinerja karyawan, lalu menemukan gambaran dan aturan yang diterapkan di data tersebut untuk mendapatkan informasi baru yang berguna. Ketika melakukan proses data mining, harus dilakukan beberapa tahapan antara lain, pembersihan data, integrasi data, pemilihan data, transformasi data, penemuan pola, evaluasi pola dan presentasi pengetahuan.

Dalam menemukan faktor apa saja yang berpengaruh terhadap kinerja karwayan serta melakukan evaluasi terhadap hubungan beberapa faktor yang berpengaruh terhadap kinerja karyawan diperlukan digunakan data mining task dengan teknik asosiasi. Association rule mining adalah metode pembelajaran mesin berbasis aturan untuk menemukan hubungan yang menarik antara variabel dalam data yang berjumlah besar[5]. Association Rule merupakan data mining task yang bertujuan untuk mencari pola yang sering muncul pada banyak transaksi, dimana pada setiap transaksinya terdiri dari beberapa item [6]. Penerapan data mining dengan association rules bertujuan menemukan informasi item-item yang saling berhubungan dalam bentuk aturan/rule. Association rules adalah teknik data mining untuk menemukan aturan asosiasi antara suatu kombinasi item [7]. Dengan menerapkan Association rules mining pada dataset karyawan pada penelitian ini, akan mudah untuk mengidentifikasi atribut-atribut yang berhubungan dengan kinerja karyawan dan memprediksi atribut apa saja yang mempengaruhi kinerja karyawan.

Dalam teknik Association rules mining ini dibutuhkan algoritma untuk mencari kandidat aturan asosiasi. Salah satu algoritma yang digunakan untuk teknik association rules adalah algoritma apriori. Kelebihan association rules dengan algoritma apriori ini adalah dapat menangani data yang berskala besar. Sedangkan algoritma lainnya memiliki kelemahan dalam penggunaan memori saat jumlah data besar. Hal tersebut tentu berpengaruh terhadap banyaknya item yang diproses. Association rules dapat diketahui dengan 2 parameter, minimum support (persen jumlah dari kombinasi item dalam database) dan minimum confidence (kuatnya hubungan antar item dalam aturan asosiatif), dimana kedua parameter tersebut ditentukan oleh user [3]. Penggunaan algoritma apriori pada penelitian ini digunakan untuk menemukan association rules dalam prediksi kinerja karyawan yaitu menambang keterhubungan antara item-item yang terkandung dalam data karyawan.

Pada penelitian yang dilakukan oleh M. Afdal dan Muhammad Rosadi, pada tahun 2019 yang berjudul “Penerapan Association Rule Mining Untuk Analisis Penempatan Tata Letak Buku Di Perpustakaan Menggunakan Algoritma Apriori”. Penelitian tersebut membuat model apriori algorithm menggunakan Association Rule Mining untuk mengatur penempatan buku dengan memperhatikan tingkat keseringan pengunjung dalam meminjam buku. Data yang digunakan adalah 11.550 transaksi peminjaman buku selama 3 tahun yang telah diproses menghasilkan 4 rules dengan kombinasi item terbesar adalah kategori buku agama dan ilmu sosial sering dipinjam secara bersamaan dengan nilai support 11,71% dan confidence 41,43%. Serta kategori buku teknologi dan ilmu sosial sering dipinjam secara bersamaan dengan nilai support 13,8% dan confidence 40,75% [8]. 
Penelitian lainnya terkait penerapan Association Rule Mining yaitu “Association Rule Mining with Permutation for Estimating Students Performance and Its Smart Education System” oleh Nongnuch Ketui, dkk. pada tahun 2019. Pada penelitian tersebut, menerapkan Association Rule Mining (ARM) untuk menemukan pola yang menarik antara berbagai prestasi akademik dalam dataset yang diperoleh. menggunakan 17.875 prestasi akademik dari 483 siswa. Hasil percobaan menunjukkan bahwa 248 rules pada confidence 0,2 dan support 0,7 sementara kinerja rules dengan set yang baru yaitu 76.00 % [5]. 

Berdasarkan penelitian-penelitian Association Rule Mining tersebut, algoritma Apriori dapat menangani hubungan antar item untuk melakukan prediksi kinerja karyawan, maka penelitian ini akan dilakukan dengan menerapkan Association Rule Mining dengan algoritma Apriori yang diharapkan menghasilkan prediksi yang akurat terhadap penelitian “Predicting Employee’s Performance with Apriori Algorithm” ini. Hasil keluaran dari implementasi teknik Association Rule Mining menggunakan algoritma apriori ini diharapkan dapat memenuhi minimum support 50 % dan minimum confidence 60%. 

## 1.4 Produce Project Plan
Tahap perencanaan yang dilakukan untuk mencapai tujuan data mining dan mencapai tujuan bisnis pada penelitian “Predicting Employee’s Performance with Apriori Algorithm” ini adalah sebagai berikut:

Tabel 1. Jadwal Pelaksanaan Proyek
**Tahapan**|**Waktu**|**Sumber daya yang dibutuhkan**|**Kegiatan**|**Ketergantungan**
:-----:|:-----:|:-----:|:-----:|:-----:
Bussiness Understanding|3 hari|Semua analysts|Menentukan tujuan utama bisnis, melakukan penilaian terhadap situasi, menentukan tujuan data mining, dan membuat project plan|Perkembangan penerapan konsep data mining
Data understanding|4 hari|Semua analysts|Mengumpulkan data yang akan digunakan, mendeskripsikan data, melakukan eksplorasi data, dan memverifikasi kualitas data|Masalah data dan teknologi
Data preparation|2 minggu|Data mining consultant, beberapa database analyst time|Memilih data yang akan digunakan, membersihkan data dari noise atau outlier, membangun data, menggabungkan data, dan membuat format data|Masalah data dan teknologi
Modelling|1 minggu|Data mining consultant, beberapa database analyst time|Memilih teknik pemodelan, membuat Test Design, membangun model, dan menilai model|Ketidakmampuan menemukan model yang tepat
Evaluation|3 hari|Semua analysts|Mengevaluasi hasil, meninjau proses, dan menentukan tahapan selanjutnya|Ketidakmampuan untuk menerapkan hasil, terjadi kesalahan pada proses pengerjaan proyek, perkembangan penerapan konsep data mining
Deployment|1 minggu|Data mining consultant, beberapa database analyst time|Membuat plan deployment, Monitoring and Maintenance Plan dan meninjau proyek|Ketidakmampuan untuk menerapkan hasil, perkembangan penerapan konsep data mining

Dalam pelaksanaan proyek dalam penelitian ini, diperlukan tools data mining yang mendukung metode untuk berbagai tahapan proses. Tools dan teknik yang digunakan dapat mempengaruhi keseluruhan proyek. Tools yang digunakan dalam mengerjakan proyek ini adalah python. Python adalah bahasa pemrograman berorientasi objek yang digunakan dalam pengembangan perangkat lunak maupun dalam analisis dan data science. Python memiliki berbagai library yang menyediakan fungsi untuk melakukan analisis data, memproses data, memvisualisasikan data, dll.
Python menyediakan library seperti scikit-learn, Keras, TensorFlow untuk membantu dalam pembuatan model data mining dengan cepat. Selain itu, terdapat juga library yang dapat digunakan untuk membagi dataset menjadi data training dan data test, misalnya menggunakan cross-validation. Metode atau algoritma yang akan digunakan dalam proyek ini adalah algoritma Apriori. Apriori merupakan algoritma yang menemukan frequent itemset (memenuhi minimum support) yang kemudian akan di-generate untuk mendapatkan rule yang memenuhi minimum confidence dari frequent itemset sebelumnya. Dalam pengimplementasian model dengan algoritma Apriori akan menggunakan library Apriori yang telah disediakan python.


# 2. Data Understanding
Tahap kedua pada metodologi CRISP-DM setelah business understanding untuk melakukan prediksi kinerja karyawan adalah data understanding. Pada bab ini akan dijelaskan mengenai pengumpulan data, pendeskripsian data untuk dapat memahami data yang akan digunakan dalam penelitian serta pengidentifikasian masalah yang berhubungan dengan data.

## 2.1 Collect Initial Data
Hal pertama yang dilakukan pada tahap data understanding adalah pengumpulan data yang merupakan langkah persiapan untuk menemukan data awal. Data berasal dari beberapa sumber yang relevan dengan tujuan proyek. Dataset yang akan digunakan untuk memprediksi kinerja dari employee adalah data employee yang dapat diakses pada link https://www.kaggle.com/shivan118/hranalysis?select=train.csv. Dataset tersebut memiliki format file CSV (Comma Separated Values) sehingga datanya bersifat statis.

## 2.2 Describe Data
Dataset yang digunakan untuk memprediksi kinerja dari karyawan menggunakan algoritma apriori adalah predicting-employee-performance dataset. Dataset ini berisi 14 atribut atau variabel dan memuat 54808 record. Dataset yang akan dianalisis pada proyek ini terdiri dari 8 atribut nominal, 8 atribut ordinal, 3 atribut binary, dan 9 atribut numerik. Berikut tabel untuk menjelaskan setiap atributnya. 

Tabel 2. Tabel Atribut pada Dataset
**No.**|**Nama atribut (variabel)**|**Tipe atribut**|**Deskripsi**
:-----:|:-----:|:-----:|:-----:	
1.|employee_id|Nominal|ID dari dari setiap karyawan (unik)
2.|department|Nominal|Nama departemen karyawan
3.|region|Nominal|Asal wilayah kerja
4.|education|Nominal|Tingkat pendidikan
5.|gender|Biary|Jenis kelamin karyawan
6.|recruitment_channel|Nominal|Kanal rekrutmen untuk karyawan
7.|no_of_trainings|Numerik|Total jumlah pelatihan yang diselesaikan pada tahun sebelumnya (seperti soft kill, technical skills, dll)
8.|age|Nominal|Usia karyawan
9.|rating|Ordinal|Peringkat karyawan
10|length_of_service|Numerik|Lama bekerja dalam beberapa tahun
11|KPIs_met >8No%|Binary|Jika persen KPI (Key Performance Indicators) lebih dari 80% => Yes, jika tidak => No
12|awards_won?|Binary|Jika karyawan memenangkan penghargaan pada tahun sebelumnya => Yes, jika tidak => No
13|avg_training_score|Numerik|Skor rata-rata dalam evaluasi pelatihan
14|is_promoted|Binary|Jika karyawan direkomendasikan untuk promosi => Yes, jika tidak => No

## 2.3 Explore Data
Exploratory Data Analysis (EDA) diperlukan sebagai sebuah pendekatan dalam menganalisis dataset untuk meringkas karakteristik utama dataset. Biasanya dilakukan dengan menggunakan metode visual. EDA digunakan untuk memahami data, mendapatkan konteks data, memahami variabel dan hubungan di antara variabel, dan merumuskan hipotesis yang berguna dalam membangun model prediksi. Atribut atau fitur pada dataset tidak semua diperlukan dalam mengananalisis. Fitur atau atribut yang digunakan merupakan atribut yang relevan dan sesuai dengan tujuan proyek yaitu fitur yang berpengaruh pada kinerja karyawan serta faktor-faktor lainnya yang dapat meningkatkan kinerja karyawan. Variabel yang relevan terkait kinerja karyawan pada proyek ini adalah variabel performance_rating dan hubungannya dengan variabel lain yang relevan dalam dataset akan dipelajari secara mendalam. Terdapat beberapa variabel terkait yang diprediksi berpengaruh terhadap kinerja dari karyawan. Hipotesis-hipotesis tersebut dirumuskan sebagai berikut:

  1. Education berpengaruh terhadap kinerja karyawan. Karyawan dengan education ‘Master’s & above’ akan memiliki kinerja yang lebih baik.
  2. No_of_trainings berpengaruh terhadap kinerja karyawan. Karyawan dengan jumlah training (no_of_trainings) yang lebih banyak akan memiliki kinerja yang lebih baik.
  3. KPIs_met>80% berpengaruh terhadap kinerja karyawan. Karyawan dengan KPIs lebih dari 80% akan memiliki kinerja yang lebih baik.
  4. Awards_won berpengaruh terhadap kinerja karyawan, karyawan yang memenangkan hadiah akan memiliki kinerja yang lebih baik.
  5. Rata-rata nilai karyawan selama pelatihan berpengaruh terhadap kinerja karyawan. Karyawan dengan avg_training_score yang tinggi akan memiliki kinerja yang lebih baik juga.

Dari beberapa hipotesis yang dirumuskan, terdapat beberapa atribut yang relevan yang selanjutnya akan digunakan untuk menentukan kinerja dari karyawannya, yaitu variabel education, no_of_trainings, KPIs_met >80%, awards_won, avg_training_score berpengaruh terhadap kinerja dari karyawan tersebut.
Setelah dilakukan eksplorasi pada data tersebut, ditemukan karakteristik-karakteristik baru yang berpengaruh terhadap hipotesis yang sebelumnya telah dirumuskan. Hal ini membuat perlu mengidentifikasi kembali subset data yang relevan untuk digunakan pada tahapan selanjutnya yang sesuai dengan tujuan data mining task pada proyek ini, yaitu untuk melakukan prediksi terhadap kinerja karyawan dalam perusahaan.


## 2.4 Verify Data Quality
Tahapan ini berisi evaluasi dan kualitas data dan kelengkapan data yang digunakan. Terjadinya error maupun kesalahan ketika input data mengakibatkan terjadinya missing value maupun noise pada data. Pada tahapan ini dilakukan pemeriksaan atribut yang hilang atau kosong. Data cleaning diperlukan untuk menjaga kekonsistenan dan menghilangkan data tidak relevan. Data cleaning pada proses data mining dapat mengurangi jumlah dan kompleksitas data. Memperkirakan apakah semua value dan ejaan nilai-nilai rasional serta apakah fitur dengan value yang berbeda memiliki pengertian yang sama.  Hasil penelusuran yang dilakukan menemukan :
a.  Terdapat atribut yang memiliki nilai null atau kosong, seperti pada atribut “education” dan “rating”, terdapat cell yang memiliki nilai null atau kosong.
b.	Format tipe data pada atribut “rating” dalam bentuk integer dan “is_promoted” yang dibuat dalam binary yang disajikan dalam angka akan menyebabakan kesulitan dalam   memahami data untuk menemukan asosiasi.


# Referensi

[1]	Q. A. Al-Radaideh and E. Al Nagi, “Using Data Mining Techniques to Build a Classification Model for Predicting Employees Performance,” Int. J. Adv. Comput. Sci. Appl., vol. 3, no. 2, 2012.

[2]	M. A. KAREEM and I. J. HUSSEIN, “The Impact of Human Resource Development on Employee Performance and Organizational Effectiveness,” Manag. Dyn. Knowl. Econ., vol. 7, no. 3, pp. 307–322, 2019.

[3]	H. Jiawei, M. Kamber, and P. Jian, Data mining: Data mining concepts and techniques. 2014.

[4]	D. T. Larose, Discovering Knowledge in Data: An Introduction to Data Mining: Second Edition, vol. 9780470908. 2014.

[5]	N. Ketui, W. Wisomka, and K. Homjun, “Association Rule Mining with Permutation for Estimating Students Performance and Its Smart Education System,” J. Comput., vol. 30, no. 2, pp. 93–102, 2019.

[6]	B. S. Hasugian, “Penerapan Metode Association Rule Untuk Menganalisa Pola Pemakaian Bahan Kimia Di Laboratorium Menggunakan Algoritma FP-Growth (Studi Kasus di Laboratorium Kimia PT. PLN (Persero) Sektor Pembangkitan Belawan Medan),” Algoritm. J. Ilmu Komput. dan Inform., vol. 3, no. 2, pp. 56–69, 2019.

[7]	N. R. Ardani and N. Fitriana, “Sistem Rekomendasi Pemesanan Sparepart Dengan Algoritma FP-Growth,” Semin. Nas. Apl. Teknol. Inf. Dan Multimed., vol. 5, no. 1, pp. 6–7, 2016.

[8]	M. Afdal and M. Rosadi, “PENERAPAN ASSOCIATION RULE MINING UNTUK ANALISIS PENEMPATAN TATA LETAK BUKU DI PERPUSTAKAAN MENGGUNAKAN ALGORITMA APRIORI,” J. Ilm. Rekayasa dan Manaj. Sist. Inf., vol. 5, no. 1, pp. 99–108, 2019.



