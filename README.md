# Sentiment Analysis using SVM ( (Support Vector Machine)
Pada praktikum ini, kami mempelajari bagaimana membangun sebuah model analisis sentimen dengan menggunakan algoritma Support Vector Machine (SVM) yang dikombinasikan dengan teknik TF-IDF vectorization.
Tujuan utama dari proyek ini adalah mengklasifikasikan ulasan produk menjadi dua kelas utama: positif atau negatif.
## 🧩 Tahapan - Tahapan dalam Pembuatan Model 🧩
### 1. Mengimport library
- pandas
- sklearrn
- pickle
- time
- matplotlib
- seaborn
### 2. Memuat Dataset
Pada tahap ini, terdapat dua buah dataset yang diambil secara langsung dari URL GitHub dalam format .csv yang digunakan untuk :
- training : "https://raw.githubusercontent.com/Vasistareddy/sentiment_analysis/master/data/train.csv"
Data training digunakan untuk melatih model SVM agar dapat mengenali pola dan hubungan antara teks ulasan (Content) dan label sentimen (Label). Jumlah datanya 1600 baris.
- testing  : "https://raw.githubusercontent.com/Vasistareddy/sentiment_analysis/master/data/test.csv"
Data testing digunakan untk menguji performa model setelah proses pelatihan selesai. Jumlah datanya 400 baris.

Didalam kedua dataset tersebut terdapat 2 kolom :
- content : yang berisi ulasan pelanggan
- label : berisi label sentimen dgn "pos" review positif dan "neg" review negatif.

### 3. TF-IDF Vectorization
Data teks diubah ke bentuk numerik menggunakan TfidfVectorizer. Hal ini penting karena model machine learning tidak bisa memahami teks secara langsung.
## 4. Melatih Model
Model SVM dengan kernel linear dilatih menggunakan data latih (train.csv) yang telah diubah menjadi representasi TF-IDF.
### 5. Evaluasi Model
Setelah model dilatih, model diuji pada data test.csv. Evaluasi dilakukan menggunakan metrik:
- Precision
- Recall
- F1-Score
### 6. Menguji dengan data baru
Model diuji menggunakan beberapa review baru untuk melihat apakah mampu mengenali sentimen dengan baik.
### 7. Menyimpan Model dan Vectorizer
Model dan vectorizer disimpan dalam file .sav agar dapat digunakan kembali tanpa perlu pelatihan ulang.

## 📈 Hasil Percobaan
Berdasarkan hasil confusion matrix, model menunjukkan performa yang cukup baik dalam mengklasifikasikan data uji. Dari total 200 data uji, model berhasil memprediksi:
- 91 review positif secara benar.
- 92 review negatif secara benar.
- Hanya terdapat 17 kesalahan prediksi.

Selain itu, hasil evaluasi menggunakan metrik klasifikasi seperti precision, recall, dan f1-score juga mendukung bahwa model memiliki performa yang seimbang dan akurat :
- Kelas positif dan negatif memiliki nilai metrik yang tinggi, yaitu di kisaran 0.91 hingga 0.92.
- Hal ini menunjukkan bahwa model tidak bias terhadap salah satu kelas, dan mampu mengenali keduanya dengan baik.

Begitu juga pengujian pada databaru, model mampu memberikan prediksi yang sesuai konteks, membuktikan bahwa model yang dibangun sudah cukup handal dan siap digunakan untuk klasifikasi sentimen pada review produk.
