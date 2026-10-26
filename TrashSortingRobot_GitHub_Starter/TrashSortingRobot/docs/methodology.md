# Catatan metodologi

1. Dataset: TrashNet, enam kelas sampah.
2. Input: gambar RGB yang diubah ke ukuran 224 x 224 piksel.
3. Model: MobileNetV2 dengan bobot ImageNet, tanpa classifier bawaan (`include_top=False`).
4. Transfer learning: backbone dibekukan pada tahap awal; classifier softmax baru dilatih.
5. Pembagian: 80% training dan 20% validation dengan seed 42.
6. Evaluasi: validation loss, validation accuracy, classification report, dan confusion matrix.
7. Batasan: hasil validasi bukan bukti bahwa sistem siap mengontrol aktuator robot. Perlu pengujian dengan kamera dan kondisi lapangan yang representatif.
