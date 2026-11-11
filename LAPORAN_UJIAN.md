# Laporan UTS Web Software Tools

**Nama:Muhmmad Fathurrohman Syahrian**
**Nomor Induk Mahasiswa:12523006**
**Kelas:Teknik Informatika A**
**Tanggal:11 November 2026**

## A. Bukti pemeriksaan masalah
| Masalah | Alat yang digunakan | Bukti pemeriksaan | Perkiraan penyebab | Perbaikan | Hasil setelah perbaikan |
|---|---|---|---|---|---|
| Produk | Browser, pemeriksaan kode | Browser gagal memuat produk; client meminta `/api/barang`, sedangkan server menyediakan `/api/products`. | Endpoint client dan server tidak sama. | Samakan URL pada `public/app.js` dengan endpoint server. | Browser menampilkan 4 produk. |
| Tombol keranjang | Browser, pemeriksaan kode | Tombol memakai kelas `.add-button`, tetapi event listener mencari `.add-to-cart`. | Selector tidak sesuai dengan kelas tombol. | Pasang event listener pada `.add-button`. | Klik menambah barang; dua klik Mouse Nirkabel menampilkan jumlah 2. |
| Total belanja | `npm run test:once`, browser | Sebelum perbaikan 5 dari 7 tes lolos; total belum mengalikan harga dengan jumlah. | Fungsi total hanya menjumlahkan harga satuan. | Hitung `harga × jumlah` untuk setiap baris keranjang. | Dua Mouse Nirkabel menampilkan total `Rp 150.000`; seluruh tes lolos. |

## B. Hasil pengujian
- Jumlah pengujian sebelum perbaikan: 5 dari 7 berhasil.
- Jumlah pengujian berhasil setelah perbaikan: 7 dari 7 berhasil (`npm run test:once`).
- Catatan perubahan pada fungsi yang diperiksa: `calculateTotal` sekarang memperhitungkan kuantitas setiap produk.

## C. Kualitas kode
- Temuan sebelum perbaikan: dependency Biome belum terpasang; setelah dipasang ditemukan format yang belum sesuai dan variabel `discount` yang tidak digunakan.
- Perbaikan yang dilakukan: format ulang dengan Biome dan hapus variabel yang tidak digunakan.
- Hasil pemeriksaan ulang: `npm run quality:check` selesai tanpa temuan.

## D. Git
- Branch (jika membuat): `master`.
- Ringkasan commit: `chore: initial project setup` dan `fix: repair product loading and cart totals`.
- Hasil pemeriksaan `git status`: bersih setelah commit perbaikan.

## E. Pemakaian kecerdasan buatan (jika digunakan)
- Nama alat: GitHub Copilot.
- Pertanyaan/instruksi yang diberikan: periksa seluruh butir checklist aplikasi dan pastikan benar.
- Bagian jawaban yang diterapkan: penyelarasan endpoint produk dan selector tombol, perbaikan perhitungan total, serta penghapusan variabel tidak terpakai.
- Cara memeriksa apakah saran tersebut benar: jalankan 7 tes otomatis, `npm run quality:check`, dan uji tampilan serta tombol di browser.

## F. Refleksi singkat
- Satu pelajaran paling penting dari ujian ini: periksa kesesuaian antarmuka client-server dan uji kuantitas lebih dari satu, bukan hanya kasus dasar.
