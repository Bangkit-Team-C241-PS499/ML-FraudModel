# ML-FraudModel

## Dataset
Dataset yang digunakan dalam proyek ini berupa pesan teks dalam Bahasa Indonesia yang masing-masing memiliki label. Dataset ini terdiri dari 1143 pesan teks yang dikategorikan ke dalam tiga label: Normal, Penipuan, dan Promo. Setiap pesan teks memiliki satu label yang sesuai dengan kontennya. Berikut adalah distribusi jumlah pesan teks untuk setiap label: Normal (569 pesan), Penipuan (335 pesan), dan Promo (239 pesan).
## Preprocessing
Untuk memastikan data siap digunakan dalam pelatihan model machine learning, kami melakukan beberapa langkah preprocessing sebagai berikut:
- Lowercase: Semua teks diubah menjadi huruf kecil untuk menghindari perbedaan antara huruf besar dan kecil.
- Remove Punctuation: Tanda baca dihapus untuk membersihkan teks.
- Remove Extra Spaces: Spasi berlebih dihapus untuk konsistensi.
- Stopword Removal: Menggunakan modul Sastrawi, kami menghapus stopword Bahasa Indonesia yang tidak memiliki makna penting dalam konteks analisis teks.
- Stemming: Kata-kata diubah ke bentuk dasarnya menggunakan modul Sastrawi Serta kata-kata yang disingkat diubah ke bentuk aslinya menggunakan kamus slang yang disimpan dalam file slang.txt.
- Tokenisasi: Teks dipecah menjadi kata-kata atau token untuk memudahkan analisis lebih lanjut.
## Make Classification Model
Label teks dalam dataset diubah ke dalam bentuk integer agar lebih mudah diproses oleh model machine learning. Berikut adalah mapping label:
* Normal: 0
*	Penipuan: 1
*	Promo: 2
Untuk membangun model klasifikasi, kami menggunakan arsitektur Bidirectional Long Short Term Memory (BiLSTM). Arsitektur ini dipilih karena kemampuannya dalam menangkap dependensi jangka panjang dalam teks, yang penting untuk analisis teks berbahasa alami. Berikut adalah detail arsitektur model yang digunakan:
`Arsitektur Model`
*	Embedding Layer: Mengubah kata-kata dalam teks menjadi representasi vektor.
*	SpatialDropout1D Layer: Menambahkan dropout untuk mengurangi overfitting.
* Bidirectional LSTM Layer: Menangkap konteks dari kedua arah (maju dan mundur) dalam teks.
*	Dense Layer: Layer fully connected untuk menghasilkan prediksi akhir.
*	Activation Function: Menggunakan softmax untuk menghasilkan probabilitas untuk setiap kelas.
## Evaluation
Model dilatih menggunakan optimizer Adam dengan learning rate 0.001 dan categorical cross-entropy sebagai loss function. Setelah proses pelatihan, model mencapai akurasi validasi sebesar 92%.
Berikut Gambaran performa model setiap epoch

Didapatkan matriks konfusi sebagai berikut
