# Data Encryption Standard (DES)  🛡️

## Apa itu DES?
**Data Encryption Standard (DES)** adalah algoritma enkripsi kunci simetris yang menggunakan kunci yang sama untuk enkripsi dan dekripsi. DES mengolah data dalam blok **64-bit** dengan kunci efektif **56-bit**. Meskipun merupakan standar penting di masa lalu, kini DES dianggap tidak aman untuk banyak aplikasi karena panjang kuncinya yang relatif pendek.

## Cara Kerja Singkat
DES menggunakan struktur **Jaringan Feistel** dan melibatkan langkah-langkah utama berikut:

1.  **Permutasi Awal (IP)**: Bit-bit dalam blok data 64-bit diacak.
2.  **16 Putaran (Ronde)**: Setiap putaran melakukan operasi berikut pada data:
    * Blok dibagi menjadi dua bagian: 32-bit Kiri (L) dan 32-bit Kanan (R).
    * Bagian Kanan (R) diproses melalui "fungsi Feistel" (`f`):
        * **Ekspansi**: R diperluas dari 32-bit menjadi 48-bit.
        * **XOR dengan Subkunci**: Hasilnya di-XOR dengan subkunci 48-bit unik untuk putaran itu (subkunci berasal dari kunci utama 56-bit).
        * **S-box (Kotak Substitusi)**: Hasil XOR 48-bit dipecah dan dilewatkan melalui 8 S-box, menghasilkan output 32-bit. Ini adalah langkah non-linear krusial.
        * **P-box (Kotak Permutasi)**: Output 32-bit dari S-box diacak lagi.
    * Output fungsi `f` di-XOR-kan dengan bagian Kiri (L). Hasilnya menjadi bagian Kanan (R) baru.
    * Bagian Kanan (R) lama menjadi bagian Kiri (L) baru (kecuali pada putaran terakhir).
3.  **Permutasi Akhir (FP)**: Setelah 16 putaran, dilakukan permutasi terakhir yang merupakan kebalikan dari IP.

---
