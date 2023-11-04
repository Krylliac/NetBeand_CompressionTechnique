# NetBeand_CompressionTechnique
Compression for text using runlenght, huffman, shannon-fano, LZW and MTF

(1) RUN-LENGTH
Merupakan metode kompresi data yang secara fisik mengurangi urutan karakter, “run” disini merupakan kejadian berulang pada karakter yang sama. Jadi semisal kita memasukkan aabbcc maka yang keluar adalah @a2@b2@c2. Sementara yang saya masukkan pada aplikasi adalah nama saya yaitu “Pranestya” dimana tidak ada pengulangan huruf jadi hasilnya semuanya adalah 1 yaitu @P1@r1@a1@n1@e1@s1@t1@y1@a1. Perlu diketahui meskipun huruf “a” disini muncul 2 kali tetapi tidak bisa dinamakan perulangan, perulangan yang dimaksud disini adalah jika ada 2 huruf yang atau lebih yang sama muncul secara urut contohnya “aaaaa”,”bbbb”, “ccc”.

![RLC](https://github.com/Krylliac/NetBeand_CompressionTechnique/assets/117600120/a712b4eb-7c47-4a93-9dfc-671c47a16ae2)

(2) HUFFMAN
Pada metode Huffman hasil output yang didapatkan adalah berupa kode binary, kode ini bisa dihitung dengan dijumlahkan sehingga menghasilkan berapa bit ukuran dari hasil kompresi yang telah dilakukan. Pada metode ini akan dihitung beratnya terlebih dahulu untuk pembagian yang saya masukkan adalah teks “Pranestya” dimana a memiliki berat frekuensi muncul 2 kali dan yang lain adalah 1 kali. Selanjutkan akan dilakukan perhitungan dengna Huffman tree dan pemberian node, sehingga didapatlah kode Huffman seperti pada aplikasi tersebut.

![huffman](https://github.com/Krylliac/NetBeand_CompressionTechnique/assets/117600120/afc806b7-f5a0-45d2-a03b-38d650dbbf08)

(3) Shannon-Fano
Pada metode ini dengan masukkan “Pranestya” akan dilakukan penyortiran frekuensi terlebih dahulu, jadi disini yang paling banyak keluar frekuensinya akan ditaruh di atas, pada kasus diatas adalah “a” dengan muncul 2 kali, selanjutnya akan dibentuk sebuah table, dimana table tersebut akan dibagi menjadi 2 yaitu bagian atas lebih besar mendekati jumlah total frekuensi pada bagian bawah. Lalu diberikanlah kode di bagian atas yaitu 0 dan dibagian bawah 1, proses ini diulangi secara terus menerus sampai selesai. Pada kasus diatas dihasilkan kode Shannon fanno seperti yang tertera pada aplikasi untuk masukkan “Pranestya” sama-sama menggunakan code binary dan penjumlahan bit bisa dijadikan sebagai patokan ukuran, tetapi berbeda dengan jumlah yang ada pada Huffman-code.

![huffman](https://github.com/Krylliac/NetBeand_CompressionTechnique/assets/117600120/53538013-f552-4c21-83db-441a2f41431c)

(4) LZW-DIctionary
Pada metode LZW dictionary bekerja dengan membangun sebuah kamus frase (kelompok dari 1 atau lebih karakter), nah saat frase ditemukan mesin kompresi akan mengecek apakah frase tersebut sudah ada dalam dictionary atau belu. Jadi semakin banyak kita memasukkan frase maka semakin banyak pula data pada dictionary yang tersimpan. Jika frase yang dimasukkan belum ada di dictionary maka proses akan dilakukan dengan penentuan posisi frase dijadikan outputnya, setelah itu posisi yang terbaru menjadi outputnya, pada aplikasi “Pranestya” adalah frase baru lalu dimasukkan ke dalam dictionary dan dilakukan penyimpanan jadi kode yang dihasilkan disini adalah index yang dibentuk setelah frase itu dimasukkan ke dalam dictionary.

![LZW2](https://github.com/Krylliac/NetBeand_CompressionTechnique/assets/117600120/43c51520-4cc2-4ab6-8ebf-9518d757004b)
![LZW1](https://github.com/Krylliac/NetBeand_CompressionTechnique/assets/117600120/1a01c366-1d65-4ee6-add7-eca5d34104c9)

(5) MTF (Move to Forward)
Metode MTF (Move to Forward) merupakan metode yang menggunakan pemodelan ASCII sebagai patokan awal. Jadi ada 255 kode yang bisa dijadikan dictionary untuk melakukan proses MTF, pada kasus diatas frase”Pranestya” disini akan dijadikan ASCII, sensifitas huruf juga berlaku dimana huruf besar berbeda dengna huruf kecil. Bisa diliat pada contoh diatas huruf “P” besar berbeda dengan “p” kecil. Jadi hasil pertama adalah menjadi bentuk ASCII terlebih dahulu, setelah itu aka nada huruf yang sama contohnya diatas “Pranestya” memiliki 2 huruf “a” disini akan dilakukan kompresi dengan move forward, bisa dilihat hasilnya adalah (80,114,98, 111,103,115,116,121,5) kode ASCII ini mewakili setiap huruf, tetapi pada kasus huruf yang sama, “a” pertama  yang akan dilakukan pengkodean menggunakan ASCII lalu untuk “a” yang terakhir akan dilakukan perhitungan berapa karakter yang ada di depan “a” pertama sampai pada “a” kedua. Disini “Pranestya” jarak “a” pertama sampai “a” kedua dipisahkan dengan “n,e,s,t,y” ada 5 huruf. Maka kode yang keluar pada “a” kedua bukan lagi kode ASCII melainkan “5” yaitu jarak dari huruf “a” pertama ke “a” kedua.

![MTF](https://github.com/Krylliac/NetBeand_CompressionTechnique/assets/117600120/9726ced1-9b3b-48a8-bac4-abfefe551a27)

