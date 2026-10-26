# Trash Sorting Robot — Transfer Learning

Proyek klasifikasi gambar sampah untuk mendukung Trash Sorting Robot menggunakan transfer learning dengan MobileNetV2 dan TensorFlow/Keras.

## Tujuan
- Mengklasifikasikan gambar ke kategori sampah pada dataset.
- Menerapkan transfer learning dari bobot MobileNetV2 pralatih ImageNet.
- Mengukur performa dengan validation accuracy, classification report, dan confusion matrix.
- Menyiapkan model untuk eksperimen lanjutan dengan kamera robot.

## Dataset
Dataset awal: TrashNet — https://github.com/garythung/trashnet

Dataset tidak disertakan dalam repository. Unduh dari sumber asli dan periksa ketentuan lisensinya. Notebook dapat meminta file ZIP saat dijalankan di Google Colab.

## Mulai cepat
1. Buka `notebooks/TrashSorting_TransferLearning.ipynb` di Google Colab.
2. Jalankan sel berurutan.
3. Unggah ZIP dataset TrashNet ketika diminta (atau sesuaikan `ZIP_PATH`).
4. Tunggu pelatihan selesai. Notebook akan menghasilkan model `.keras`, grafik, metrik, dan confusion matrix.
5. Uji gambar sampah dan unduh ZIP hasil dari sel terakhir.
6. Masukkan hasil aktual ke folder `models/` dan `results/` sebelum mengklaim model telah dilatih.

## Struktur
- `notebooks/`: notebook pelatihan dan evaluasi.
- `src/`: lokasi untuk skrip inferensi/pengembangan lanjutan.
- `docs/`: referensi dataset dan catatan metodologi.
- `models/`: tempat menyimpan model setelah pelatihan.
- `results/`: tempat menyimpan metrik/grafik aktual.
- `samples/`: contoh gambar uji yang boleh dibagikan.

## Metode
1. Dataset dipecah menjadi 80% training dan 20% validation.
2. Gambar diubah menjadi 224×224.
3. MobileNetV2 dengan bobot ImageNet digunakan sebagai ekstraktor fitur; backbone dibekukan pada tahap awal.
4. Lapisan klasifikasi softmax dilatih selama maksimal 10 epoch dengan early stopping.
5. Performa dievaluasi pada validation split.

## Hasil
Isi bagian ini setelah notebook benar-benar dijalankan:
- Validation accuracy: belum diukur.
- Validation loss: belum diukur.
- Catatan pengujian kamera robot: belum dilakukan.

## Batasan
Validasi pada dataset publik tidak menjamin performa pada kamera robot. Lakukan pengujian tambahan dengan foto robot, variasi pencahayaan, latar, dan objek yang belum pernah dilihat. Jangan gunakan prediksi sebagai satu-satunya dasar mekanisme robot tanpa validasi keselamatan.

## Lingkungan
Lihat `requirements.txt`. Notebook dirancang untuk Google Colab.
