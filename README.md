# SIG_TEORI_TGS6
 basic raster styling and analysis
 
 # Langkah Kerja :

1. Buka QGIS dan cari file yang diunduh di panel Browser. Perluas file gpw-v4-population-count-rev11_2000_2pt5_min_tif.zip dan seret file gpw-v4-population-count-rev11_2000_2pt5_min.tif ke kanvas.

2. Lapisan baru gpw-v4-population-count-rev11_2000_2pt5_min akan ditambahkan ke panel Lapisan. Demikian pula, cari file gpw-v4-population-count-rev11_2010_2pt5_min_tif.zip dan seret file gpw-v4-population-count-rev11_2010_2pt5_min.tif ke kanvas.

3. Mari jelajahi lapisan ini. Klik tombol Identifikasi pada Bilah Alat Atribut. Setelah alat dipilih, klik titik mana pun di kanvas.

4. Nilai yang terkait dengan piksel tersebut akan ditampilkan di panel Identify Results yang baru. Di panel Identify Results, ubah Mode ke Top down. Ini akan menampilkan nilai piksel dari semua raster, bukan hanya lapisan paling atas. Bandingkan nilai dari kedua layer. Karena resolusi raster kira-kira 5km x 5km, nilai piksel mewakili total populasi di area (25 km persegi) yang diwakili oleh piksel.

5. Tutup panel Identify Results. Mari buat visualisasi layer yang lebih baik. Klik tombol Open the layer Styling panel di panel Layers.

6. Di panel Layer Styling, klik dropdown Render type dan pilih Singleband pseudocolor renderer.

7. Renderer ini akan memberi style pada layer menggunakan color ramp. Ramp warna default adalah putih-merah di mana nilai minimum akan diberi warna putih dan nilai maksimum di lapisan akan diberi warna merah. Nilai tengah akan diberi warna interpolasi linier merah. Perluas Pengaturan Nilai Min / Maks dan pilih opsi pemotongan hitungan kumulatif. Anda akan melihat bahwa visualisasi peta sekarang jauh lebih baik. Rentang data standar ditetapkan dari 2% hingga 98% dari nilai data, artinya outlier tidak akan digunakan untuk menetapkan nilai minimum dan maksimum, sehingga menghasilkan visualisasi yang jauh lebih representatif.

8. Tutup panel Layer Styling. Kita bisa menerapkan gaya serupa ke lapisan lain juga. Namun ada cara yang lebih mudah untuk mentransfer gaya dari satu lapisan ke lapisan lainnya. Klik kanan layer gpw-v4-population-count-rev11_2010_2pt5_min dan pilih Styles ‣ Copy Style.

9. Sekarang klik kanan layer gpw-v4-population-count-rev11_2000_2pt5_min yang tidak ditata dan pilih Styles Paste Style.

10. Parameter gaya yang sama akan diterapkan ke lapisan lainnya. Fitur ini sangat berguna ketika Anda ingin membandingkan lapisan yang berbeda menggunakan kategorisasi yang sama. Saat Anda mengaktifkan visibilitas lapisan atas, Anda dapat melihat perubahan populasi secara visual.

11. Tugas kita adalah membuat peta tematik perubahan populasi. Mari kita hitung perbedaan antara 2 lapisan dan buat raster lain di mana setiap piksel mewakili perubahan populasi. Buka Raster Kalkulator raster.

12. Di bagian Raster bands, Anda dapat memilih layer dengan mengklik dua kali pada layer tersebut. Band diberi nama setelah nama raster diikuti dengan @ dan nomor band. Karena setiap raster kami hanya memiliki 1 band, Anda akan menambahkan nama dengan @1 ke nama layer. Kalkulator raster dapat menerapkan operasi matematika pada piksel raster. Dalam hal ini kita ingin memasukkan rumus sederhana untuk mengurangkan populasi tahun 2010 dari tahun 2000. Masukkan ekspresi berikut. Selanjutnya, klik tombol … di sebelah lapisan Keluaran. "gpw-v4-population-count-rev11_2010_2pt5_min@1" - "gpw-v4-population-count-rev11_2000_2pt5_min@1"

13. Masukkan population_change_2010_2000.tif sebagai file Output. Klik OK untuk memulai perhitungan.

14. Setelah selesai layer baru population_change_2010_2000 akan ditambahkan ke panel Layers. Mari kita ubah gayanya agar perubahan populasi negatif dan positif dapat divisualisasikan dengan lebih baik. Klik tombol Open the layer Styling panel di panel Layers.

15. Salah satu opsinya adalah menggunakan teknik penataan yang serupa seperti sebelumnya dan memilih jalan warna yang berbeda. Klik drop-down Color ramp dan pilih Spectral ramp. Klik drop-down lagi dan pilih Invert Color Ramp untuk menetapkan warna biru ke nilai rendah dan merah ke nilai tinggi.

16. Ini adalah visualisasi yang bagus, tetapi tidak mudah untuk ditafsirkan. Mari buat peta yang lebih baik dengan 4 kategori terpisah, Tolak, Netral, Pertumbuhan, dan Pertumbuhan Tinggi. Gulir ke bawah ke tabel dengan kelas. Tahan tombol Shift dan pilih semua baris. Klik tombol Hapus baris yang dipilih.

17. Ubah mode Interpolasi ke Diskrit. Kami sekarang akan membuat peta warna secara manual. Klik tombol Tambahkan nilai secara manual. Masukkan -100 sebagai Nilai dan Tolak sebagai Label. Tetapkan warna biru untuk kategori ini. Cara kerja peta warna adalah semua nilai yang lebih rendah dari nilai yang dimasukkan akan diberi warna entri tersebut. Anda akan melihat bahwa kanvas hanya akan menampilkan area dengan perubahan populasi negatif.

18. Lengkapi peta warna dengan nilai yang sesuai. Saya memilih 100, 1000 dan 100000 sebagai batas atas untuk masing-masing kategori Netral, Pertumbuhan, dan Pertumbuhan Tinggi. Tetapkan warna untuk setiap kategori yang dibuat, misalnya krem, oranye, dan merah.
