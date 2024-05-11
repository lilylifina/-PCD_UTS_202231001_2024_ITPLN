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

**IMPORT LIBRARY**
```python
import cv2
import numpy as np
from matplotlib import pyplot as plt
```
import cv2: Mengimpor modul OpenCV untuk pengolahan gambar.
import numpy as np: Mengimpor modul NumPy untuk manipulasi array.
from matplotlib import pyplot as plt: Mengimpor fungsi pyplot dari modul matplotlib untuk membuat plot.

```python
img_source = cv2.imread("LILY_UTS.jpg")
img_rgb = cv2.cvtColor(img_source, cv2.COLOR_BGR2RGB)
```
img_source = cv2.imread("LILY_UTS.jpg"): Membaca gambar dari file "LILY_UTS.jpg" menggunakan OpenCV.
img_rgb = cv2.cvtColor(img_source, cv2.COLOR_BGR2RGB): Mengubah format warna gambar dari BGR (yang digunakan oleh OpenCV) menjadi RGB (yang digunakan oleh matplotlib) menggunakan fungsi cv2.cvtColor().

```python
plt.imshow(img_rgb)
```
plt.imshow(img_rgb): Menampilkan gambar dalam format RGB menggunakan matplotlib

```python
gray_img = cv2.cvtColor(img_source, cv2.COLOR_BGR2GRAY)
```
gray_img = cv2.cvtColor(img_source, cv2.COLOR_BGR2GRAY): Mengonversi gambar asli ke citra grayscale menggunakan fungsi cv2.cvtColor().

```python
contrast_factor = 1.5  
brightness_factor = 30    
adjusted_img = cv2.convertScaleAbs(img_source, alpha=contrast_factor, beta=brightness_factor)
``````python

contrast_factor = 1.5 dan brightness_factor = 30: Menentukan faktor kontras dan kecerahan yang akan diterapkan pada gambar.
adjusted_img = cv2.convertScaleAbs(img_source, alpha=contrast_factor, beta=brightness_factor): Menyesuaikan kontras dan kecerahan gambar menggunakan fungsi cv2.convertScaleAbs().

```python
plt.figure(figsize=(10, 5))
plt.subplot(1, 2, 1)
plt.title('Original Image')
plt.imshow(cv2.cvtColor(img_source, cv2.COLOR_BGR2RGB))
plt.axis('off')

plt.subplot(1, 2, 2)
plt.title('Brightened Image')
plt.imshow(cv2.cvtColor(adjusted_img, cv2.COLOR_BGR2RGB))
plt.axis('off')
plt.show()

``````python

plt.figure(figsize=(10, 5)): Membuat figure baru dengan ukuran (lebar, tinggi) = (10, 5).
plt.subplot(1, 2, 1): Membuat subplot pertama dalam grid 1x2.
plt.subplot(1, 2, 2): Membuat subplot kedua dalam grid 1x2.
plt.imshow(cv2.cvtColor(img_source, cv2.COLOR_BGR2RGB)) dan plt.imshow(cv2.cvtColor(adjusted_img, cv2.COLOR_BGR2RGB)): Menampilkan gambar asli dan yang sudah disesuaikan dalam subplot.
plt.axis('off'): Menghilangkan sumbu pada plot.
plt.show(): Menampilkan plot.
