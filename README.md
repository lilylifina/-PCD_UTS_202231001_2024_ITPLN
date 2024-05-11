# -PCD_UTS_202231001_2024_ITPLN

Projek ini terkait dengan pemrosesan gambar dan analisis citra, yang merupakan area penting dalam pengembangan teknologi komputer dan kecerdasan buatan. Berikut adalah beberapa teori yang mendukung projek ini:

### 1. Pemrosesan Gambar:
Pemrosesan gambar adalah bidang ilmu yang berkaitan dengan manipulasi gambar secara digital. Teori-teori dalam pemrosesan gambar meliputi:

- **Konversi Ruang Warna:** Konversi ruang warna seperti BGR (Blue-Green-Red) ke RGB (Red-Green-Blue) atau HSV (Hue-Saturation-Value) penting dalam analisis dan manipulasi gambar.
  
- **Penyesuaian Kontras dan Kecerahan:** Penyesuaian kontras dan kecerahan adalah teknik penting dalam memperbaiki kualitas gambar atau untuk menyesuaikan gambar agar sesuai dengan kebutuhan analisis.

- **Ekstraksi Saluran Warna:** Ekstraksi saluran warna terpisah memungkinkan analisis terperinci pada komponen warna tertentu dalam sebuah gambar.

- **Histogram:** Histogram gambar adalah representasi distribusi intensitas piksel dalam gambar. Ini memberikan informasi tentang distribusi warna dan kontras dalam gambar.

### 2. Analisis Citra:
Analisis citra melibatkan ekstraksi informasi yang bermakna dari gambar atau citra. Beberapa konsep kunci dalam analisis citra meliputi:

- **Segmentasi Citra:** Segmentasi adalah proses membagi gambar menjadi bagian-bagian yang berarti atau objek. Ini bisa dilakukan dengan mengaplikasikan thresholding, clustering, atau teknik deteksi tepi.

- **Ekstraksi Fitur:** Ekstraksi fitur melibatkan identifikasi dan ekstraksi atribut-atribut yang relevan dari gambar. Ini bisa mencakup fitur-fitur seperti tekstur, bentuk, atau pola dalam gambar.

- **Klasifikasi:** Klasifikasi adalah proses untuk mengelompokkan objek-objek berdasarkan fitur-fitur yang diekstraksi. Ini melibatkan penggunaan algoritma pembelajaran mesin seperti k-Nearest Neighbors (k-NN), Support Vector Machines (SVM), atau Convolutional Neural Networks (CNN).

### 3. Ruang Warna HSV:
Model warna HSV (Hue-Saturation-Value) merupakan representasi yang lebih intuitif daripada model RGB. Dalam analisis citra, seringkali lebih mudah untuk memisahkan objek berdasarkan warna dalam ruang warna HSV daripada dalam model RGB, terutama karena HSV memisahkan informasi warna dari kecerahan dan saturasi.

### 4. Thresholding:
Thresholding adalah teknik sederhana yang digunakan untuk segmentasi citra. Ini melibatkan pengaturan nilai ambang untuk memisahkan piksel menjadi dua kelas berdasarkan intensitasnya. Dalam projek ini, thresholding digunakan untuk membuat citra biner yang menyoroti area tertentu dalam gambar.

Dengan memahami konsep-konsep tersebut, kita dapat menerapkan teknik-teknik pemrosesan gambar dan analisis citra dengan lebih efektif dalam projek seperti yang telah ditunjukkan dalam kode yang diberikan.
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

**Import Library**
```python
import cv2
import numpy as np
from matplotlib import pyplot as plt
```
Baris kode ini mengimpor modul cv2 dari OpenCV untuk pemrosesan gambar, modul numpy sebagai np untuk manipulasi array, dan fungsi pyplot dari modul matplotlib.pyplot sebagai plt untuk membuat plot.

**Baca Gambar dan Ubah ke Format RGB**
```python
img_source = cv2.imread("LILY_UTS.jpg")
img_rgb = cv2.cvtColor(img_source, cv2.COLOR_BGR2RGB)
```
Kode ini membaca gambar dengan nama file "LILY_UTS.jpg" menggunakan OpenCV dan kemudian mengubah format warnanya dari BGR (yang digunakan oleh OpenCV) menjadi RGB (yang digunakan oleh matplotlib) menggunakan fungsi cv2.cvtColor().

**Tampilkan Gambar Asli dan Ubah ke Grayscale**

```python
plt.imshow(img_rgb)
gray_img = cv2.cvtColor(img_source, cv2.COLOR_BGR2GRAY)
```
Kode ini menampilkan gambar asli dalam format RGB menggunakan plt.imshow(), dan juga mengonversi gambar asli ke citra grayscale menggunakan fungsi cv2.cvtColor().

**Penyesuaian Kontras dan Kecerahan**
```python
contrast_factor = 1.5  
brightness_factor = 30    
adjusted_img = cv2.convertScaleAbs(img_source, alpha=contrast_factor, beta=brightness_factor)
```
Dua variabel contrast_factor dan brightness_factor menentukan faktor kontras dan kecerahan yang akan diterapkan pada gambar.
Gambar asli kemudian disesuaikan dengan kontras dan kecerahan menggunakan fungsi cv2.convertScaleAbs().

**Tampilkan Gambar Asli dan yang Sudah Disesuaikan**
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
```
Kode ini membuat subplot dengan ukuran (10, 5), dan menampilkan gambar asli dan yang sudah disesuaikan dalam dua subplot.
Sumbu pada plot dihilangkan menggunakan plt.axis('off').

**Tampilkan Saluran Warna Terpisah (RGB)**
```python
fig, axs = plt.subplots(2, 2, figsize=(10, 10))

# Saluran merah
red_channel = cv2.cvtColor(adjusted_img, cv2.COLOR_BGR2RGB)[:, :, 0]
axs[0, 0].imshow(red_channel, cmap="gray")
axs[0, 0].set_title('Red Channel')

# Saluran hijau
green_channel = cv2.cvtColor(adjusted_img, cv2.COLOR_BGR2RGB)[:, :, 1]
axs[0, 1].imshow(green_channel, cmap="gray")
axs[0, 1].set_title('Green Channel')

# Saluran biru
blue_channel = cv2.cvtColor(adjusted_img, cv2.COLOR_BGR2RGB)[:, :, 2]
axs[1, 0].imshow(blue_channel, cmap="gray")
axs[1, 0].set_title('Blue Channel')

# Saluran kecerahan
original_channel = cv2.cvtColor(adjusted_img, cv2.COLOR_BGR2RGB)
axs[1, 1].imshow(original_channel)
axs[1, 1].set_title('Original Channel')
plt.show()

```
Kode ini membuat subplot dengan ukuran (10, 10), dan menampilkan saluran warna terpisah (merah, hijau, biru) serta saluran kecerahan dalam subplot.
Setiap saluran warna diekstrak menggunakan pemanggilan fungsi cv2.cvtColor().Kode ini membuat subplot dengan ukuran (10, 10), dan menampilkan saluran warna terpisah (merah, hijau, biru) serta saluran kecerahan dalam subplot.
Setiap saluran warna diekstrak menggunakan pemanggilan fungsi cv2.cvtColor().

**Tampilkan Histogram untuk Setiap Saluran Warna**

```python
channels = [red_channel, green_channel, blue_channel]
colors = ['Red', 'Green', 'Blue']

for i, channel in enumerate(channels):
    plt.figure(figsize=(15, 5))
    plt.subplot(1, 2, 1)
    plt.imshow(channel, cmap='gray')
    plt.title(f'{colors[i]} Channel')
    
    plt.subplot(1, 2, 2)
    hist = cv2.calcHist([channel], [0], None, [256], [0, 256])
    plt.plot(hist)
    plt.title(f'{colors[i]} Channel Histogram')
    plt.xlabel('Pixel Intensity')
    plt.ylabel('Frequency')
    
    plt.show()
```
channels: List yang berisi saluran warna terpisah (merah, hijau, biru).
colors: List yang berisi nama warna yang sesuai dengan saluran warna.

for i, channel in enumerate(channels): Melakukan iterasi melalui setiap saluran warna dan indeksnya menggunakan fungsi enumerate().
plt.figure(figsize=(15, 5)): Membuat figure baru dengan ukuran (lebar, tinggi) = (15, 5).
plt.subplot(1, 2, 1): Membuat subplot pertama dalam grid 1x2 untuk menampilkan gambar saluran warna.
plt.imshow(channel, cmap='gray'): Menampilkan saluran warna dalam citra grayscale.
plt.title(f'{colors[i]} Channel'): Memberi judul pada subplot dengan nama saluran warna yang sesuai.
plt.subplot(1, 2, 2): Membuat subplot kedua dalam grid 1x2 untuk menampilkan histogram.
hist = cv2.calcHist([channel], [0], None, [256], [0, 256]): Menghitung histogram dari saluran warna menggunakan cv2.calcHist().
plt.plot(hist): Menampilkan histogram menggunakan plot garis.
plt.title(f'{colors[i]} Channel Histogram'): Memberi judul pada subplot histogram dengan nama saluran warna yang sesuai.
plt.xlabel('Pixel Intensity') dan plt.ylabel('Frequency'): Memberi label pada sumbu-x dan sumbu-y.
plt.show(): Menampilkan plot.

**Inisialisasi Subplot untuk Citra Biner**
```python
fig, axs = plt.subplots(2, 2, figsize=(10, 10))

# Ambang batas untuk mendapatkan citra biner (NONE)
(thresh, binary1) = cv2.threshold(gray_img, 0, 255, cv2.THRESH_BINARY)
axs[0, 0].imshow(binary1, cmap='gray')
axs[0, 0].set_title('NONE')

# Mask untuk warna biru dalam HSV
img_hsv = cv2.cvtColor(img_source, cv2.COLOR_BGR2HSV)
blue_lower = np.array([100, 50, 50])
blue_upper = np.array([140, 255, 255])
mask_blue = cv2.inRange(img_hsv, blue_lower, blue_upper)
axs[0, 1].imshow(mask_blue, cmap='gray')
axs[0, 1].set_title('BLUE')

# Ambang batas untuk mendapatkan citra biner (RED-BLUE)
(thresh, binary3) = cv2.threshold(gray_img, 105, 255, cv2.THRESH_BINARY)
axs[1, 0].imshow(binary3, cmap='binary')
axs[1, 0].set_title('RED-BLUE')

# Ambang batas untuk mendapatkan citra biner (RED-GREEN-BLUE)
(thresh, binary4) = cv2.threshold(gray_img, 140, 255, cv2.THRESH_BINARY)
axs[1, 1].imshow(binary4, cmap='binary')
axs[1, 1].set_title('RED-GREEN-BLUE')
plt.show()

```
fig, axs = plt.subplots(2, 2, figsize=(10, 10)): Membuat subplot dengan ukuran (10, 10) dan 2x2 grid.
(thresh, binary1) = cv2.threshold(gray_img, 0, 255, cv2.THRESH_BINARY): Melakukan ambang biner pada citra grayscale menggunakan cv2.threshold().
axs[0, 0].imshow(binary1, cmap='gray'): Menampilkan citra biner yang dihasilkan dari ambang biner pertama.
axs[0, 1].imshow(mask_blue, cmap='gray'): Menampilkan citra biner yang dihasilkan dari pemilihan warna biru menggunakan ruang warna HSV.
axs[1, 0].imshow(binary3, cmap='binary'): Menampilkan citra biner yang dihasilkan dari ambang biner kedua.
axs[1, 1].imshow(binary4, cmap='binary'): Menampilkan citra biner yang dihasilkan dari ambang biner ketiga.
plt.show(): Menampilkan plot.


