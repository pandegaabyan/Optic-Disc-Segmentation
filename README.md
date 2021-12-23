# Eksplorasi Metode Segmentasi Optic Disc pada Citra Fundus

---

Imam Syahrizal, Izzun Nafis Ibadik, Pandega Abyan Zumarsyah

imamsyahrizal@mail.ugm.ac.id, izzunnafis2018@mail.ugm.ac.id, pandegaabyan@mail.ugm.ac.id

Departemen Teknik Elektro dan Teknologi Informasi Universitas Gadjah Mada

---

Pengolahan citra fundus menjadi topik yang cukup populer sebagai cara untuk membantu menganalisis kondisi mata. Analisis ini dapat bermanfaat untuk deteksi beberapa penyakit mata seperti glaukoma dan retinopati. Pada penelitian ini, dilakukan eksplorasi beberapa metode untuk memperoleh hasil segmentasi terbaik. Metode pertama berkaitan dengan proses segmentasi berbasis region dengan algoritma GrowCut. Pada metode pertama ini juga memerlukan preprocessing dengan beberapa operasi morfologi. Metode kedua melakukan proses segmentasi dengan thresholding yang nilai threshold-nya diperoleh berdasarkan operasi turunan kedua dari data histogram derajat keabuan. Hasil thresholding ini kemudian digunakan sebagai nilai awal dari segmentasi berbasis region dengan algoritma GrabCut. Metode ketiga menggunakan algoritma Random Forest yang mana masukannya diperoleh dari hasil beberapa filter seperti sobel, prewitt, canny, dan beberapa filter lain. Dengan masukan tersebut, model dilatih untuk mengklasifikasikan piksel pada citra. Metode keempat menggunakan deep learning dengan arsitektur UNet dan model MobileNetV2. Berbagai metode tersebut dievaluasi dengan tiga dataset: dataset lokal, DRIONS-DB, dan RIM-ONE v3. 

Model UNet-MobileNetV2 memberikan hasil yang baik untuk ketiga dataset tersebut. Model Random Forest juga mampu melakukan segmentasi pada ketiga dataset, namun tidak menunjukkan hasil yang memuaskan pada dataset RIM-ONE v3. Sementara itu, metode 1 dan 2 mampu memberikan hasil yang cukup baik hanya saat diterapkan pada dataset lokal. Tanpa penyesuaian parameter, kedua metode ini sulit mengimbangi performa dari model UNet-MobileNetV2. 

---

Program ini melakukan segmentasi optic disc pada citra fundus dengan menggunakan berbagai dataset dan berbagai metode

### Dataset
- **Dataset 1 ([source](https://drive.google.com/drive/u/1/folders/1Y2HpGf74_K5NYS0Fn4zMSMhOzLA7K0_l))**: Terdiri atas 100 citra fundus dengan resolusi 3072x2048 piksel. Kemudian terdapat ground truth berbentuk matriks berekstensi .mat yang mengandung informasi daerah optic disc dan optic cup
- **Dataset 2 (DRIONS-DB)**: Terdiri atas 110 citra fundus yang secara acak dipilih dari Ophthalmology Service di Miguel Servet Hospital, Saragossa (Spain). Citra disimpan dengan resolusi 600x400 piksel. Sebanyak 23% merupakan citra dari penderita glaukoma sementara 77% sisanya dari penderita hipertensi mata. Ground truth nya merupakan hasil anotasi oleh 2 ahli oftalmologi
- **Dataset 3 (RIM-ONE r3)**: Terdiri atas 159 citra fundus dari data milik Hospital Universitario de Canarias, Hospital Clínico San Carlos, dan Hospital Universitario Miguel Servet. Ketiganya merupakan rumah sakit Spanyol. Pada data ini, citra direpresentasikan sebagai citra stereo yang disusun horizontal. Anotasi dilakukan terhadap fitur optic disc sebelah kiri oleh dua ahli oftalmologi

### Metode
- **Metode 1**: Preprocessing => Blood Vessel Removal => Circular Hough Transform => GrowCut
- **Metode 2**: Empat metode yang saling berhubungan dengan memanfaatkan Thresholding, Grabcut, dan Fit-Ellipse
- **Metode 3**: Machine Learning dengan model Random Forest untuk Segmentasi
- **Metode 4**: Deep Learning berbasis Arsitektur UNet dengan Model MobileNetV2 lalu implementasinya menggunakan bantuan PyTorch

### Alur

Setiap metode dikembangkan utamanya untuk Dataset 1. Setelah itu berhasil untuk Dataset 1, barulah diuji untuk Dataset 2 dan 3. Namun, hasil untuk kedua dataset itu belum optimal, bahkan ada metode yang belum bisa memberikan hasil karena mengalami eror. 

Struktur dari program ini:
- Loading dataset dari Google Drive
- Pendefinisian berbagai fungsi umum
- Pendefinisian berbagai fungsi untuk setiap metode
- Running dengan menggunakan fungsi-fungsi yang sudah didefinisikan
- Perbandingan dari berbagai hasil yang sudah didapatkan

### Video Penjelasan

Video presentasi terkait project: https://youtu.be/0XucamfgYRE
