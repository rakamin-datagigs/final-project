# Final Project Tim 6 Rakamin Data Science Batch 28

### Team 6 - DataGigs
1. Devina
2. Hani Kurnia
3. Yudanta A
4. Mutiara Farianda
5. Linda
6. Rudiyanti

Code Python ini digunakan untuk mengolah Dataset [Travel Insurance Prediction](https://www.kaggle.com/datasets/tejashvi14/travel-insurance-prediction-data) yang berasal dari Kaggle.

### Summary Insights
Berdasarkan exploratory data analysis yang telah dilakukan,  rekomendasi terkait strategi bisnis yang dapat dijalankan adalah sebagai berikut:
1. Berdasarkan hasil analisa terhadap **Jenis Pekerjaan** dari customer, dapat dianalisa bahwa persentase nasabah dari perusahaan swasta memiliki peluang lebih besar untuk menjadi nasabah travel perjalanan, sehingga dapat di jadikan target market kedepannya sebagai sasaran utama. Namun tidak menutup kemungkinan karyawan pemerintahan juga memiliki peluang untuk menjadi calon nasabah asuransi perjalanan, walaupun berdasarkan sample yang digunakan persentasenya lebih kecil. Kita dapat memberikan penawaran khusus sebagai bentuk kerjasama kita dengan staff pemerintahan, harapannya persentase nasabah dari staff pemerintahan ini bisa lebih meningkat untuk kedepannya.
2. Customer dengan anggota keluarga yang banyak memiliki kecenderungan untuk membeli asuransi perjalanan walaupun berdasarkan hasil analisa, jumlah customer yang membeli asuransi perjalanan lebih rendah daripada customer yang tidak membeli. Salah satu perkiraan halangan bagi customer untuk membeli asuransi perjalanan adalah karena income yang lebih terpakai untuk keperluan keluarga. Kita dapat menyusun kembali strategi paket asuransi perjalanan yang ditawarkan dari segi ganti rugi yang akan diberikan berdasarkan jumlah anggota keluarga yang ditanggung oleh customer namun wajar dan tidak merugikan perusahaan, dengan premi/biaya bulanan yang dapat disesuaikan dengan kondisi keuangan.
3. Dari 380 customer yang pernah melakukan perjalanan internasional, sebanyak 78,42% memiliki asuransi perjalanan. Hal ini dapat disebabkan oleh benefit yang menguntungkan dan dapat memberikan rasa aman jika terdapat kendala kesehatan ataupun finansial dalam perjalanan tersebut. Di sisi lain, dari 1607 customer yang belum pernah melakukan perjalanan internasional hanya terdapat 25,64% customer yang memiliki asuransi perjalanan. Kita dapat mempertimbangkan untuk menambahkan benefit yang akan meningkatkan rasa aman dan nyaman dalam perjalanan domestik seperti ganti rugi perubahan jadwal, fasilitas yang didapatkan jika terdapat halangan ataupun kendala dalam melakukan perjalanan, dan sejenisnya..

### Data Preprocessing
Pada Data Preprocessing dilakukan Data Cleansing dan Feature Engineering yang meliputi:
- Handle missing value: Tidak terdapat missing value pada data sehingga tidak perlu dilakukan imputasi.
- Handle duplicateion: Terdapat 738 baris data duplikat yang dihapus, sehingga baris data yang tersisa adalah sebesar 1249 baris data dari 1987 baris data.
- Handle outliers: Berdasarkan analisa terhadap boxplot dan menggunakan IQR, tidak terdapat outliers pada fitur numerikal.
- Feature selection: Karena hanya terdapat 9 fitur pada dataset, diputuskan untuk menggunakan seluruh fitur yang ada untuk proses selanjutnya. Dilakukan analisa chi square test melihat korelasi antara fitur-fitur kategorikal terhadap target.
- Feature extraction: Menambahkan fitur 'IncomeGroup' yang didasari oleh data 'AnnualIncome' dan merujuk pada artikel [How the middle class has turned cities into India’s growth engine](https://timesofindia.indiatimes.com/times-special/how-the-middle-class-has-turned-cities-into-indias-growth-engine/articleshow/95865472.cms) dari Times of India.
- Feature Transformation: Melihat dari skewness dan perbandingan antara mean dan median, distribusi data numerikal termasuk normal. Oleh karena itu, hanya dilakukan normalisasi untuk menyamakan skala values pada fitur-fitur nuemrikal tersebut. 
- Feature Encoding: Dilakukan Label Encoding terhadap fitur Employment Type, GraduateOrNot, FrequentFlyer, EverTravelledAbroad dan One Hot Encoding terhadap fitur 'IncomeGroup'.
- Class Imbalance: Setelah Splitting Data menjadi train dan test data, diketahui class imbalance tidak signifikan sehingga tidak perlu di handle.
