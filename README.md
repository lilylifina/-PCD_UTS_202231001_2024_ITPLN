# -PCD_UTS_202231001_2024_ITPLN

**Analisis Gambar dan Histogram:**

1. **Gambar Asli dan Disesuaikan**: Pada gambar asli, terlihat warna-warna yang beragam dengan tingkat kontras yang mungkin kurang. Setelah disesuaikan, gambar terlihat lebih cerah dan kontrasnya ditingkatkan.

2. **Saluran Warna Terpisah**: Ketika saluran warna terpisah ditampilkan, kita dapat melihat kontribusi masing-masing warna terhadap gambar secara terpisah. Saluran merah menyoroti area dengan intensitas merah yang tinggi, demikian pula dengan saluran hijau dan biru.

3. **Histogram**: Histogram untuk setiap saluran warna memberikan informasi tentang distribusi intensitas piksel dalam gambar. Histogram merah menunjukkan adanya puncak di sekitar nilai intensitas yang lebih tinggi, menandakan keberadaan warna merah yang kuat dalam gambar. Demikian juga, histogram hijau dan biru menunjukkan pola yang mirip untuk saluran warna tersebut.

4. **Segmentasi Warna**: Citra biner yang dihasilkan dari segmentasi warna membagi gambar menjadi beberapa area berdasarkan warna tertentu. Misalnya, citra biner "NONE" menyoroti area-area di mana tidak ada warna yang melebihi ambang batas tertentu. Sedangkan citra biner "BLUE" menyoroti area di mana warna biru dalam gambar berada dalam rentang nilai tertentu dalam ruang warna HSV.

**Tahapan Cara Menyelesaikan Projek:**

1. **Membaca Gambar**: Program dimulai dengan membaca gambar yang akan dianalisis menggunakan OpenCV.

2. **Penyesuaian Kontras dan Kecerahan**: Kontras dan kecerahan gambar disesuaikan menggunakan faktor yang ditentukan sebelumnya.

3. **Pemisahan Saluran Warna**: Gambar yang telah disesuaikan dibagi menjadi saluran warna merah, hijau, dan biru untuk menganalisis kontribusi masing-masing warna.

4. **Perhitungan Histogram**: Histogram dihitung untuk setiap saluran warna untuk memberikan wawasan tentang distribusi intensitas piksel.

5. **Segmentasi Warna**: Berdasarkan histogram dan karakteristik warna gambar, citra biner dihasilkan untuk mengidentifikasi area dengan warna tertentu.

6. **Menampilkan Hasil**: Hasil analisis, termasuk gambar yang telah disesuaikan, saluran warna terpisah, histogram, dan citra biner, ditampilkan menggunakan matplotlib untuk evaluasi lebih lanjut.

Dengan langkah-langkah tersebut, program dapat memberikan pemahaman yang komprehensif tentang karakteristik gambar, termasuk komposisi warna, distribusi intensitas piksel, dan segmentasi warna.

```python
CODE
```
* SasbKASB
* dhbska
