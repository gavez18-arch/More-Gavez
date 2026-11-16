# Ledgr — panduan pasang dan uji

Aplikasi pencatat pemasukan dan pengeluaran yang berjalan sepenuhnya di HP-mu.
Tidak ada server dan tidak ada akun: data disimpan di penyimpanan aplikasi di HP.

## Isi folder

| File | Fungsi |
|---|---|
| `index.html` | Kerangka halaman |
| `styles.css` | Tampilan (warna, tata letak, animasi) |
| `app.js` | Semua logika: simpan, hitung, grafik, cadangan, PIN |
| `sw.js` | Membuat aplikasi bisa dibuka tanpa internet |
| `manifest.webmanifest` | Nama dan ikon saat dipasang di layar utama |
| `icons/`, `fonts/` | Ikon aplikasi dan huruf Plus Jakarta Sans |

## A. Mengunggah ke GitHub Pages (gratis, sekitar 10 menit, lewat laptop)

1. Buka github.com, buat akun (Sign up) kalau belum punya, lalu masuk.
2. Klik tombol **+** di kanan atas, pilih **New repository**.
3. Isi **Repository name** dengan `catatin`, pilih **Public**, lalu klik **Create repository**.
   Yang terlihat publik hanya kode aplikasinya. Data keuanganmu tidak pernah ada di GitHub.
4. Di halaman repository yang baru, klik tautan **uploading an existing file**.
5. Ekstrak file zip di laptop. Buka folder `ledgr`, pilih SEMUA isinya
   (termasuk folder `icons` dan `fonts`), lalu seret ke halaman GitHub.
   Yang diseret adalah isi foldernya, bukan folder `ledgr` itu sendiri.
6. Tunggu sampai semua file terdaftar, lalu klik **Commit changes**.
7. Buka **Settings** (menu atas repository), lalu **Pages** (menu kiri).
8. Di bagian **Build and deployment**: Source = **Deploy from a branch**,
   Branch = **main**, folder = **/ (root)**. Klik **Save**.
9. Tunggu 1 sampai 2 menit, lalu muat ulang halaman itu. Alamat aplikasimu muncul di atas,
   bentuknya `https://NAMA-AKUNMU.github.io/catatin/`.

## B. Memasang di layar utama iPhone

1. Buka alamat tadi di **Safari** (harus Safari, bukan Chrome).
2. Ketuk tombol **Bagikan** (kotak dengan panah ke atas).
3. Pilih **Tambah ke Layar Utama** (Add to Home Screen), lalu **Tambah**.
4. Mulai sekarang, selalu buka lewat ikon **Ledgr** di layar utama.

Penting: di iPhone, aplikasi di layar utama punya penyimpanan terpisah dari Safari.
Jadi mulailah mencatat dari ikon di layar utama, bukan dari Safari.

## C. Menjaga data tetap aman

- Buka **Lainnya > Cadangkan data** secara rutin (misalnya tiap akhir bulan) dan
  simpan filenya ke iCloud Drive/Files. Aplikasi akan mengingatkan kalau sudah lebih dari 30 hari.
- Ganti HP: pasang Ledgr di HP baru, lalu **Lainnya > Pulihkan dari cadangan**.
- Jangan menghapus ikon Ledgr dari layar utama sebelum mencadangkan. Menghapus ikon
  ikut menghapus datanya.
- **Kunci PIN** (Lainnya > Pasang kunci PIN) menutup aplikasi dari orang yang memegang HP-mu.
  Ini kunci layar, bukan enkripsi. Kalau lupa PIN, satu-satunya jalan adalah menghapus data
  lalu memulihkan dari cadangan.

## D. Kalau nanti kodenya diubah

Unggah ulang file yang berubah ke GitHub, lalu di `sw.js` naikkan angka versinya
(misalnya `ledgr-v9` menjadi `ledgr-v10`). Tutup dan buka lagi aplikasinya dua kali supaya versi baru terpakai.

## E. Memasang pembaruan (tab Aset)

1. Ekstrak zip yang baru di laptop.
2. Buka repository `catatin` di GitHub, klik **Add file > Upload files**.
3. Seret semua isi folder `ledgr` yang baru (sama seperti pemasangan pertama).
   File dengan nama yang sama otomatis menggantikan yang lama.
4. Klik **Commit changes**, lalu tunggu 1 sampai 2 menit.
5. Di iPhone, buka Ledgr, tutup sepenuhnya (geser ke atas dari daftar aplikasi),
   lalu buka lagi. Ulangi sekali lagi kalau tab **Aset** belum muncul.

Nama di bawah ikon layar utama tidak ikut berubah otomatis. Supaya tertulis Ledgr:
tekan **Cadangkan data** dan simpan filenya, hapus ikon lama, buka lagi alamatnya di
Safari, pilih **Tambah ke Layar Utama**, lalu **Pulihkan dari cadangan**. Menghapus ikon
ikut menghapus data, jadi jangan lewati langkah cadangan. Alamat aplikasi tetap sama.

Data transaksimu tidak berubah oleh pembaruan ini. Tetap lebih aman kalau kamu
menekan **Cadangkan data** dulu sebelum memperbarui.

Yang ada di versi ini:
- **Bahasa:** buka ikon roda gigi, lalu pilih Bahasa Indonesia atau English. Nama kategori
  buatanmu tidak ikut diterjemahkan.
- **Beranda** berisi ringkasan saldo, insight, transaksi terbaru, dan statistik
  (rangkuman bulanan berbentuk pie chart dengan pilihan bulan, pengeluaran per kategori, tren,
  perbandingan per bulan).
- **Anggaran** (di Beranda, tombol **Buat anggaran**) punya dua jenis. *Batas bulanan*
  menghitung pengeluaran bulan berjalan, dari satu kategori atau dari semua pengeluaran,
  lalu memberi tahu sisa dan kalau sudah lewat batas. *Target tabungan* (misalnya liburan
  atau HP baru) diisi lewat tombol **Tabung**; angkanya dicatat terpisah dan tidak
  mengurangi saldo dompet.
- **Dompet** bersifat opsional. Ketuk jenisnya (Tunai, Bank, E-wallet, Kredit), lalu pilih
  bank atau e-wallet-nya (BCA, BNI, Mandiri, GoPay, OVO, dan lain-lain) dan isi saldonya.
  Tiap pilihan punya lencana inisial berwarna; ini bukan logo resmi. Satu jenis bisa berisi
  beberapa dompet. Dompet tampil sebagai tumpukan kartu: ketuk kartu di belakang untuk
  memindahkannya ke depan, ketuk kartu paling depan untuk mengubah nama, menyesuaikan saldo,
  atau menghapusnya. Di form transaksi kamu memilih dompetnya: pemasukan menambah saldo,
  pengeluaran mengurangi.
- **Sembunyikan saldo:** ikon mata di kanan atas menyamarkan semua nominal. Ketuk lagi
  untuk menampilkannya.
- **Aset** bersifat opsional: pilih dulu jenisnya (Saham, Emas, Deposito, Obligasi,
  Reksadana, Properti, Crypto, Cash), lalu isi nominal harga beli. Total aset adalah jumlah
  harga beli, bukan nilai pasar. Alokasinya tampil sebagai pie chart.
- Aplikasi tidak terhubung ke internet untuk data apa pun.
- Tampilan memakai tema hitam.
- Menu pengaturan dan cadangan dibuka lewat ikon roda gigi di kanan atas.

## F. Checklist pengujian

Pemasangan
- [ ] Alamat GitHub Pages terbuka di Safari dan tampil halaman Ledgr
- [ ] Ikon Ledgr muncul di layar utama dan terbuka layar penuh (tanpa bilah alamat Safari)
- [ ] Mode pesawat aktif: aplikasi tetap terbuka dan tetap bisa mencatat

Anggaran dan dompet
- [ ] Buat anggaran batas bulanan untuk satu kategori: persentasenya sesuai pengeluaran bulan ini
- [ ] Buat target tabungan, ketuk Tabung, isi nominal: jumlah terkumpul bertambah
- [ ] Tambah dompet Bank, pilih BCA: kartu biru berlencana BCA muncul paling depan
- [ ] Ketuk kartu di belakang: kartu itu pindah ke depan
- [ ] Geser layar mulai dari tumpukan kartu: halaman tetap bisa di-scroll, menu bawah diam
- [ ] Form anggaran dan form dompet bisa di-scroll saat keyboard terbuka

Input transaksi
- [ ] Ketuk +, isi nominal, pilih kategori, Simpan: selesai di bawah 10 detik
- [ ] Nominal otomatis berformat titik (ketik 1250000 menjadi 1.250.000)
- [ ] Simpan dengan nominal kosong: muncul "Nominal belum diisi."
- [ ] Simpan dengan nominal 0: muncul "Nominal harus lebih dari 0."
- [ ] Simpan tanpa kategori: muncul "Pilih satu kategori."
- [ ] Tanggal otomatis hari ini dan bisa diganti
- [ ] Setelah menyimpan muncul notifikasi "Transaksi tersimpan"
- [ ] Tutup aplikasi sepenuhnya lalu buka lagi: transaksi masih ada

Beranda
- [ ] Pemasukan, pengeluaran, dan saldo bersih cocok dengan hitungan manual
- [ ] Hari ini, Minggu ini, Bulan ini, dan Custom mengubah angka dengan benar
- [ ] Insight menampilkan kategori terbesar, rata-rata harian, dan perbandingan periode
- [ ] Bagian Statistik tampil di bawah transaksi terbaru, diawali kartu Rangkuman bulanan
- [ ] Rangkuman bulanan: memilih bulan (daftar atau panah) mengganti pie chart dan totalnya
- [ ] Tampilan Pengeluaran dan Pemasukan menunjukkan porsi tiap kategori; Arus kas menunjukkan pemasukan vs pengeluaran
- [ ] Setelah mengganti bulan atau tampilan, halaman tetap di posisi yang sama dan masih bisa di-scroll
- [ ] Mengetuk batang grafik menampilkan nilainya

Scroll dan tampilan (iPhone)
- [ ] Saat halaman di-scroll, navigasi bawah (Beranda, Riwayat, +, Dompet, Aset) tetap diam di tempatnya
- [ ] Menarik halaman melewati batas atas atau bawah tidak ikut menggeser navigasi
- [ ] Seluruh aplikasi bertema hitam, termasuk bilah status di atas

Bahasa
- [ ] Roda gigi > English mengubah semua teks, termasuk navigasi dan form
- [ ] Pilihan bahasa tetap sama setelah aplikasi ditutup dan dibuka lagi

Dompet
- [ ] Tab Dompet pertama kali menampilkan empat jenis; mengetuk salah satunya membuka form tambah dompet
- [ ] Bisa menambah dua dompet berjenis Bank dengan nama berbeda (misalnya BCA dan BNI)
- [ ] Form transaksi menampilkan semua dompetmu dan mengingat yang terakhir dipakai
- [ ] Pengeluaran Rp 50.000 dari satu dompet mengurangi saldo dompet itu sebesar Rp 50.000
- [ ] Pemasukan menambah saldo dompet yang dipilih
- [ ] Ketuk dompet, ubah saldo: angka di daftar dan total ikut berubah
- [ ] Pengeluaran dengan dompet Kredit tampil sebagai utang
- [ ] Menghapus dompet meminta konfirmasi dan transaksinya tetap ada

Form dan sembunyikan saldo (iPhone)
- [ ] Tekan +: form terbuka, bisa di-scroll saat keyboard tampil, dan tombol Simpan selalu terlihat
- [ ] Ikon mata menyamarkan semua nominal di Beranda, Riwayat, Dompet, dan Aset
- [ ] Pilihan sembunyikan saldo tetap sama setelah aplikasi dibuka lagi

Riwayat, ubah, hapus
- [ ] Pencarian menemukan transaksi dari catatan, kategori, atau nominal
- [ ] Filter jenis, kategori, dan tanggal bekerja; "Hapus filter" mengembalikan semua
- [ ] Ketuk transaksi, ubah nominal, simpan: angka di Beranda ikut berubah
- [ ] Hapus transaksi: muncul konfirmasi; Batal tidak menghapus, Hapus menghapus

Cadangan dan keamanan
- [ ] Cadangkan data menghasilkan file .json yang bisa disimpan ke Files
- [ ] Pulihkan dari cadangan mengembalikan transaksi
- [ ] Ekspor CSV bisa dibuka di Google Sheets
- [ ] Setelah PIN dipasang, aplikasi meminta PIN saat dibuka; PIN salah ditolak

Aset
- [ ] Tab Aset pertama kali menampilkan pilihan delapan jenis aset, termasuk Cash
- [ ] "Simpan pilihan" tanpa memilih apa pun ditolak dengan pesan yang jelas
- [ ] Setelah memilih, hanya jenis yang dipilih yang muncul, masing-masing dengan tombol "Isi nominal"
- [ ] Isi nominal: harga beli kosong atau 0 ditolak; nama boleh kosong
- [ ] Total aset = jumlah semua nominal; pie chart alokasi berjumlah 100%
- [ ] "Atur jenis aset" bisa menambah jenis baru; jenis yang masih berisi aset tidak bisa dimatikan
- [ ] Ketuk aset untuk mengubah nominal; hapus aset meminta konfirmasi
- [ ] Besoknya, grafik "Total aset dari waktu ke waktu" mulai tampil
- [ ] File cadangan baru memulihkan transaksi, saldo dompet, aset, dan pilihan jenis aset
- [ ] Ikon roda gigi membuka menu Lainnya
