# HR-ANALYTICS-DASHBOARD

## Overview

Sebuah dashboard analitik interaktif yang dirancang untuk memantau metrik tenaga kerja HR dan menganalisis pola pengunduran diri (*attrition*) karyawan menggunakan dataset *IBM HR Analytics*. Proyek ini mengubah data mentah HR menjadi wawasan visual strategis yang mencakup distribusi demografi, tingkat *turnover* per departemen, struktur gaji, dan dinamika masa kerja untuk mendukung strategi retensi talenta berbasis data.
<img width="3075" height="1763" alt="HR Analytics Copy_page-0001" src="https://github.com/user-attachments/assets/75b0575a-413b-48f1-9865-494583042192" />

## Business Questions Framework

Tabel berikut menguraikan pertanyaan bisnis utama yang ingin dijawab melalui analisis ini, dikelompokkan berdasarkan dimensi analitis pada dashboard:

| Dimensi Analisis | Pertanyaan Bisnis Utama |
| :--- | :--- |
| **Tenaga Kerja & Demografi** | • Berapa jumlah total dan karyawan aktif saat ini, serta bagaimana distribusi demografi berdasarkan kelompok usia (*Age Group*) dan jenis kelamin (*Gender*)[cite: 17]?<br>• Departemen mana yang memiliki volume jumlah karyawan tertinggi[cite: 17]? |
| **Attrition & Turnover** | • Berapa angka total dan persentase tingkat pengunduran diri (*Attrition Rate*) secara keseluruhan[cite: 17]?<br>• Bagaimana pola *attrition* berdasarkan kelompok rentang gaji (*Salary Slab*) dan lama tahun pengalaman kerja (*Total Working Years*)[cite: 17]? |
| **Peran & Kepuasan Kerja** | • Bagaimana korelasi antara tingkat kepuasan kerja (*Job Satisfaction*) dengan berbagai peran pekerjaan (*Job Role*) terhadap angka *attrition*[cite: 17]? |

## Data Cleaning & Preparation

1. **Redundant Column Removal:** Menghapus kolom konstan yang bernilai tunggal dan tidak variatif (`EmployeeCount`, `Over18`, `StandardHours`).
2. **Missing Value Handling:** Memastikan integritas data tanpa adanya nilai kosong pada atribut krusial.
3. **Data Type Validation:** Memastikan ketepatan tipe data (numerik untuk pendapatan/usia, teks untuk kategori).
4. **Feature Engineering (`AttritionNumeric`):** Membuat kolom bantuan numerik (`1` jika *Attrition* = 'Yes', `0` jika 'No') untuk mempermudah perhitungan *Attrition Rate* pada analisis dashboard.
5. **Grouping & Categorization:** Mengelompokkan usia ke dalam rentang kelompok umur (*Age Groups*) untuk analisis tren demografi.
   
## Visualizations & Dashboard Layout

* **KPI Cards:** Menampilkan metrik utama organisasi, meliputi *Total Employees* (1K), *Active Employees* (1.23K), *Attrition Count* (237), *Attrition Rate* (16.12%), *Avg Age* (36.92), dan *Avg Experience* (7.01 tahun).
* **Attrition by Department:** Diagram donat yang memvisualisasikan jumlah dan proporsi karyawan yang keluar berdasarkan masing-masing departemen (*Research & Development*, *Sales*, dan *Human Resources*).
* **Attrition by Salary Slab:** Grafik batang horizontal yang menganalisis tingkat pengunduran diri berdasarkan kelompok rentang gaji karyawan (*Up to 5K*, *5K - 10K*, *10K - 15K*, *15K+*).
* **Attrition by Job Role & Satisfaction:** Tabel matriks interaktif yang menghubungkan tingkat kepuasan kerja dengan berbagai peran pekerjaan (*Job Role*) terhadap jumlah *attrition*.
* **Age Group Distribution:** Grafik batang vertikal yang menunjukkan demografi jumlah karyawan berdasarkan kelompok umur (*26-35*, *36-45*, *46-55*, *18-25*, *55+*).
* **Attrition by Gender:** Diagram proporsi karyawan yang keluar berdasarkan jenis kelamin (*Male* vs *Female*).
* **Attrition Trend by Experience:** Grafik area (*area chart*) yang melacak tren pengunduran diri berdasarkan total tahun pengalaman kerja (*Total Working Years*).
* **Department Wise Employee Count:** Grafik batang horizontal yang merangkum total volume karyawan di setiap departemen.

## Dataset Fields

* **Demographics & Work History:** *Age*, *Gender*, *MaritalStatus*, *Education*, *EducationField*, *TotalWorkingYears*, *YearsAtCompany*, *YearsInCurrentRole*, dan *YearsWithCurrManager*.
* **Job & Department Details:** *Department*, *JobRole*, *JobLevel*, *BusinessTravel*, dan *DistanceFromHome*.
* **Compensation & Performance:** *MonthlyIncome*, *PercentSalaryHike*, *PerformanceRating*, dan *StockOptionLevel*.
* **Attrition Target:** *Attrition* ('Yes'/'No') & *AttritionNumeric* (1/0).

## Tools Used

* **Google Colab / Python (Pandas):** Digunakan untuk eksplorasi data awal, analisis statistik, dan pembersihan dataset *IBM HR Analytics*.
* **Power Query:** Digunakan untuk pembersihan data lanjutan, transformasi tipe data, pembuatan *custom column*, dan penggabungan tabel.
* **Power BI:** Platform utama untuk perancangan visualisasi data, *dashboard layout*, kartu KPI interaktif, dan publikasi laporan akhir.
* **Interactive Slicers & Filters:** Filter dinamis berdasarkan *Department* dan *Gender* untuk eksplorasi data secara mendalam.

## Key Business Insights

1. **Tingkat Attrition:** Tingkat *turnover* organisasi sebesar 16,12% (237 dari 1.470 karyawan).
2. **Turnover Berdasarkan Departemen:** Departemen *Sales* memiliki persentase tingkat *attrition* tertinggi (~20,6%), sedangkan *Research & Development* menyumbang jumlah kasus keluar terbanyak secara kuantitas (133 karyawan).
3. **Puncak Usia Kerja:** Mayoritas tenaga kerja berada pada kelompok usia 28–37 tahun.

## Strategic Recommendations

1. **Fokus Retensi Sales & R&D:** Evaluasi beban kerja, keseimbangan antara pekerjaan dan kehidupan pribadi (*work-life balance*), serta skema insentif untuk peran di departemen *Sales* dan *R&D* guna menekan tingkat kepindahan karyawan.
2. **Pengembangan Karir Jalur Tengah:** Buat program percepatan pengembangan karir dan peningkatan *engagement* yang jelas untuk kelompok usia produktif (28–37 tahun) agar loyalitas terhadap perusahaan tetap terjaga.
3. **Survei Kepuasan Kerja Periodik:** Lakukan evaluasi berkala terhadap faktor kompensasi, tingkat kepuasan kerja (*job satisfaction*), dan jalur promosi untuk menjaga kestabilan *turnover* organisasi.
