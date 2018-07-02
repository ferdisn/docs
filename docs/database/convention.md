# Convention
atau Kaidah penamaan

## Kaidah penamaan yang dipakai dalam *database*

### Nama *database*
Harus memiliki karakteristik berikut:

* dalam bahasa Inggris, dengan penerjemahan Indonesia yang masuk akal,
* merujuk ke pemilik data,
* merujuk ke fungsi aplikasi yang memakai *database*,
* kalau terdiri dari dua kata atau lebih, pakai *underscore* (_) sebagai pemisah kata.

Contoh:

| Nama *database* | Dipakai untuk... | 
| --- | --- |
| mail_management | mengelola data peladen surel (Postfix dan Dovecot) | 
| paragita | mengelola data Paragita |

### Nama *schema*
Apabila DBMS mendukung sistem *schema*, nama *schema* harus memiliki karakteristik berikut:

* dalam bahasa Inggris,
* merujuk ke sifat data yang disimpan,
* referensi sebagai berikut: `production`, `simulation`, `development`.

Contoh:

| Nama *schema* | Dipakai untuk... | 
| --- | --- |
| mail_management.production | menyimpan data utama |
| mail_management.development | menyimpan data untuk pengembangan | 
| paragita.production | menyimpan data utama |

Catatan: abaikan *schema* standar dari DBMS, misalnya `public`.

### Nama tabel
Nama tabel harus memiliki karakteristik berikut:

* dalam bahasa Inggris,
* kata benda berbentuk jamak.

Contoh:

| Nama tabel | Dipakai untuk... | 
| --- | --- |
| domains | menyimpan data domain |
| mailboxes | menyimpan data kotak surat | 
| users | menyimpan data pengguna |
| addresses | menyimpan data alamat |

### Nama kolom/*field* TBD
Nama kolom harus memiliki karakteristik berikut:

* dalam bahasa Inggris,
* kata benda,
* kata sifat,

Contoh:

| Nama tabel | Dipakai untuk... | 
| --- | --- |
| domains | menyimpan data domain |
| mailboxes | menyimpan data kotak surat | 
| users | menyimpan data pengguna |
| addresses | menyimpan data alamat |


