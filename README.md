
# Teori Terkait Pemrosesan Citra
Ruang Warna (Color Space):

1.RGB (Red, Green, Blue): Ruang warna aditif yang memadukan tiga warna dasar, yaitu merah, hijau, dan biru, untuk menghasilkan spektrum warna yang luas. RGB banyak digunakan dalam berbagai aplikasi pengolahan gambar digital.

2.HSV (Hue, Saturation, Value): Ruang warna yang memisahkan informasi tentang warna (hue) dari kecerahan (value). HSV sangat berguna dalam pemrosesan citra karena lebih mendekati cara manusia memahami warna.
Hue: Representasi warna dalam bentuk derajat pada lingkaran warna, berkisar antara 0 hingga 360 derajat.
Saturation: Mengukur intensitas atau kejenuhan warna, dinyatakan dalam persentase dari 0 hingga 100%.
Value: Mengukur kecerahan warna, juga dinyatakan dalam persentase dari 0 hingga 100%.

3.Konversi Ruang Warna:Mengubah gambar dari ruang warna RGB ke HSV mempermudah proses segmentasi warna. Dalam ruang warna HSV, warna-warna yang mirip dapat diidentifikasi lebih mudah dibandingkan dalam ruang warna RGB.

4.Segmentasi Citra:Segmentasi adalah proses membagi citra digital menjadi beberapa bagian atau objek yang lebih kecil. Tujuannya adalah untuk menyederhanakan atau mengubah representasi gambar sehingga lebih bermakna dan mudah dianalisis.
Thresholding: Teknik segmentasi yang memisahkan objek berdasarkan intensitas warna. Dalam kode yang diberikan, thresholding dilakukan menggunakan fungsi cv2.inRange() untuk menghasilkan gambar biner (mask).

5.Masking:
Mask Biner: Gambar biner yang menandai bagian dari citra yang memenuhi kriteria tertentu. Dalam konteks ini, mask menunjukkan piksel yang berada dalam rentang warna yang ditentukan.
Bitwise Operations: Operasi logika yang diterapkan pada gambar untuk memanipulasi piksel sesuai dengan mask yang diberikan. Contohnya adalah cv2.bitwise_and(), yang digunakan untuk mengaplikasikan mask pada gambar asli, menampilkan hanya piksel yang sesuai dengan mask.

6.Visualisasi Hasil:
Matplotlib: Pustaka Python yang digunakan untuk membuat visualisasi data, termasuk grafik dan gambar.
Subplots: Membuat beberapa gambar kecil dalam satu figure besar untuk membandingkan berbagai hasil atau tahap pemrosesan. Subplots membantu dalam menganalisis hasil pemrosesan citra dengan menyajikan beberapa gambar secara berdampingan.


## Penjelasan :

Jadi disini saya melakukan segmentasi warna pada citra mangga dan memisahkan  mangga (kuning) dan daun (hijau) berdasarkan ruang warna HSV.Izinkan saya menjelaskan ini secara detail mengenai Tugas Ujian Akhir ini.Pertama Tama, gambar asli di file mangga.jpg dimuat  menggunakan cv2.imread.OpenCV memuat gambar dalam format BGR (biru, hijau, merah), jadi konversikan gambar ke format RGB menggunakan cv2.cvtColor agar sesuai dengan format yang digunakan  matplotlib untuk menampilkan gambar.Setelah gambar dalam format RGB, gambar tersebut dikonversi ke ruang warna HSV menggunakan cv2.cvtColor(original_image, cv2.COLOR_RGB2HSV).Ruang warna HSV (hue, saturation, value) sering digunakan untuk segmentasi warna karena dapat memisahkan komponen warna dengan lebih baik dibandingkan ruang warna RGB.Selanjutnya, tentukan rentang warna  mangga dan daun dalam ruang warna HSV.Mangga kuning, mangga_ bawah, dan mangga_atas.Daun hijau daun_bawah dan daun_atas.Setelah Anda menentukan rentang warna, gunakan cv2.inRange untuk membuat topeng.Masker ini menyoroti piksel dalam gambar yang termasuk dalam rentang warna mangga dan daun yang telah ditentukan.Setelah mask dibuat, gunakan cv2.bitwise_and untuk melakukan segmentasi.Ini menciptakan gambar yang hanya menampilkan bagian dari gambar asli yang berada dalam rentang warna mangga atau daun, tergantung pada masker yang diterapkan.Hasil segmentasi  ditampilkan dalam subplot menggunakan matplotlib.pyplot.Gambar asli ditampilkan pada subplot pertama (sumbu[0, 0]), masker  mangga dan daun ditampilkan pada subplot kedua (sumbu[0, 1]), dan hasil segmentasi mangga dan daun akan ditampilkan.di dalam.Subplot ketiga dan keempat (sumbu [1, 0] dan sumbu [1, 1]).Terakhir, gunakan plt.tight_layout()  untuk memastikan tata letak subplot yang rapi sebelum menggunakan plt.show()  untuk menampilkan keseluruhan plot kepada pengguna.Jadi tidak hanya melakukan segmentasi warna pada gambar mangga, tetapi juga memvisualisasikan hasilnya dengan jelas menggunakan Matplotlib.
