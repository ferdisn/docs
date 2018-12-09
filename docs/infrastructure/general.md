Layanan yang dipelihara secara umum meliputi surat elektronik serta situs web.

## Struktur

Struktur yang dipakai untuk menjalankan layanan tersebut seperti berikut:

* Mail Server
* Database Server
* Web Server

Ketiganya merupakan instance yang berdiri sendiri. Lihat di [sini](/infrastructure/base_configuration.md) untuk pengaturan standar setiap instance.

## Program

Prinsip dasar pemilihan perangkat lunak adalah seumum dan senormal mungkin. Dalam menentukan perangkat lunak, saya menghindari pemilihan alat bantu pengaturan (*e.g.* CPanel) atau semacamnya untuk mengelola surel atau situs web. Hal ini mempertimbangkan skala pengelolaan.

Selanjutnya, apabila pada suatu program (seperti `postfix`) mendukung konfigurasi berbasis database, maka pengelolaannya akan disandarkan pada perangkat lunak yang ditulis sendiri. Bahasa yang akan digunakan adalah PHP.

Paket program yang dijalankan di setiap instance:

| Mail | Database | Web |
| - | - | - |
| postfix<br>dovecot<br>postgresql | postgresql<br>mariadb | nginx<br>php-fpm |

## *Port*

| Standar | *Port* | Lokasi | Keterangan |
| - | - | - | - |
| SMTP | 25 | Mail | mendukung TLS |
| SMTP<br>Submission | 587 | Mail | wajib TLS |
| IMAP | 993 | Mail | SSL |
| PostgreSQL | 5432 | Mail | Hanya konfigurasi surel |
| PostgreSQL | 5432 | Database | Database PostgreSQL |
| MariaDB | 3306 | Database | Database MariaDB |
| HTTP<br>HTTPS | 80<br>443 | Web | Ditentukan konfigurasi |

PHP-FPM dijalankan menggunakan soket Unix untuk alasan efisiensi dari Nginx yang memanggilnya.

## Komponen Luar
### G Suite
[G Suite](https://gsuite.google.com/) adalah perangkat produktivitas awan dari Google yang ditujukan untuk pebisnis segmen UMKM. Biaya USD 5 per pengguna per bulan. Pengguna dari Indonesia masih mungkin menerima diskon tambahan dari Google.

Pada saat ini, hanya satu organisasi dibawah pengelolaan saya yang memakai G Suite. *MX Record* domain organisasi tersebut saat ini masih mencantumkan Mail Server sebagai tujuan pengirima surel. Dari *instance* Mail Server tersebut, akan ada forwarding khusus untuk satu alamat email yang dikelola di G Suite.

??? note "Pengelolaan alias dan alamat surel"
    Saat ini sedang direncanakan akan dibangun mail server yang seluruh tabel referensinya disimpan di dalam database PostgreSQL. Apabila sudah selesai dan bisa di*expose* ke publik organisasi, pengaturan forwarding tersebut bisa diubah oleh pengguna secara mandiri.

### Let's Encrypt
Sertifikat SSL dikeluarkan oleh Let's Encrypt, dan diperbarui setiap tiga bulan.

### CloudFlare
DNS dikelola di CloudFlare. Tidak ada rencana untuk *host* DNS lokal karena seluruh aset berada di internet.

### Domain registrar
Pembahasan mengenai registrar. Mari jangan sebut merek. Serta jangan pilih TLD yang tidak long-lasting. Look at `co.de` example.

## Webmail
[Roundcube](https://roundcube.net/) adalah perangkat lunak yang dipilih untuk melihat ke dalam peladen surel. Pengguna bebas menggunakan program email apa saja untuk membaca dan mengirim email, selama program tersebut mengikuti standar IMAP dan SMTP. Untuk kebutuhan membaca email di tempat umum, program ini bisa diakses melalui URL tertentu. Program ini berbasis PHP, dan dijalankan di bawah instance PHP-FPM di bawah nama saya.
