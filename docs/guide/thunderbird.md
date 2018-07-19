## Konfigurasi Thunderbird dengan email server IMAP dan SMTP standar

### 1. Unduh dan pasang perangkat lunak
Windows dan OS X: Kunjungi situsnya di [https://www.thunderbird.net](https://www.thunderbird.net) lalu unduh versi terkini. Pasang executablenya.

Linux: Ambil dari *repo* distro Anda dengan perintah:

* Turunan Debian: `# apt-get install thunderbird`
* Turunan Red Hat Enterprise Linux: `# yum install thunderbird` | mulai versi 7 `yum` diganti dengan `dnf`
* Turunan Fedora `# dnf install thunderbird`

Jika Anda pemberani, silakan bangun dari kode sumber.

### 2. Konfigurasi
To be written.

## Konfigurasi Thunderbird dengan CalDAV/CardDAV server BaÃ¯kal

### 1. Unduh dan pasang perangkat lunak
Sama seperti yang diuraikan sebelumnya.

Tambahannya, pasang *plugin* CardBook dengan cara:

1. Klik Menu, lalu klik Plugin.
<br>
![menu-plugin][menu-plugin]
2. Buka menu Extensions di kiri, lalu di kanan atas, di kotak pencarian, ketik 'CardBook' lalu tekan Enter, dan akan muncul daftar plugin yang namanya sesuai.
<br>
![extensions-window][extensions-window]
3. Klik **Install** di sebelah kanan CardBook. (Lihat gambar sebelumnya)
4. Klik **Restart Now** yang muncul setelah pemasangan selesai.
<br>
![restart-now][restart-now]

### 2. Konfigurasi
Jalankan perangkat lunak.

* Apabila ada pertanyaan soal *System Integration*, abaikan saja dengan klik tombol **Skip Integration**.
* Jika ada pertanyaan soal konfigurasi akun email, abaikan saja dengan klik tombol **I think I'll configure my account later.**
* Jika ada pertanyaan terkait impor data kontak Thunderbird ke dalam CardBook, klik **Cancel**.

Lalu prosedur konfigurasi.

1. Klik tombol **CardBook** yang ada di sebelah tombol menu utama.
![entering-cardbook][cardbook-icon]

2. Klik tombol menu utama CardBook di kiri. Yang di kanan menu utama Thunderbird. Klik menu utama Cardbook, Address Book, New Address Book.
![opening-menu][cardbook-menu]

1. Pilih 'Remote' di lokasi Address Book. Klik **Next**.
![dialog-location][cardbook-dialog-location]

1. Di jendela berikutnya akan ada beberapa isian. Pilih dahulu 'CardDAV' sebagai tipe yang diinginkan.

1. Lalu, dapatkan URL address book yang akan diimpor. Karena ini BaÃ¯kal, maka skema URLnya biasanya berbentuk seperti:
        
    ```
    $HOST/dav.php/addressbooks/$BAIKAL_USER/$ADDRESSBOOK
    ```

1. Isikan URL ke kolom URL. Setelah itu isikan username dan password Anda, dan klik Validate. Kalau tidak bermasalah, bisa lanjut dengan klik Next.
![dialog-type-connection][cardbook-dialog-type-connection]

1. Selanjutnya tentukan nama dan warna. Silakan isi sesuka hati, atau biarkan saja.
![dialog-setting][cardbook-dialog-setting]
1. Klik Finish.

1. Selesai!!!
![look-of-book][cardbook-book]

Sekarang semua perubahan yang dilakukan di Address Book ini akan tersinkronisasi ke server, dan tersedia di semua aplikasi yang juga memakai server ini.


[//]: # (CardBook installation)
[menu-plugin]: https://asset.ferdi.id/thunderbird-cardbook/menu-plugin.jpg "Path to open Plugin Window"
[extensions-window]: https://asset.ferdi.id/thunderbird-cardbook/extensions-window.jpg "Extensions Window"
[restart-now]: https://asset.ferdi.id/thunderbird-cardbook/plugin-restart-now.jpg "Extensions Window"

[//]: # (Address Book configuration)
[cardbook-icon]: https://asset.ferdi.id/thunderbird-cardbook/cardbook-icon.jpg "Icon to access CardBook"
[cardbook-menu]: https://asset.ferdi.id/thunderbird-cardbook/create-new-address-book.jpg "Path to create new Address Book"
[cardbook-dialog-location]: https://asset.ferdi.id/thunderbird-cardbook/choose-location.jpg "Choose location of the new Address Book"
[cardbook-dialog-type-connection]: https://asset.ferdi.id/thunderbird-cardbook/carddav-connection.jpg "Choose type of the new Address Book and connection info"
[cardbook-dialog-setting]: https://asset.ferdi.id/thunderbird-cardbook/final-setting.jpg "Choose name and color of the new Address Book"
[cardbook-display]: https://asset.ferdi.id/thunderbird-cardbook/final-setting.jpg "Choose name and color of the new Address Book"
[cardbook-book]: https://asset.ferdi.id/thunderbird-cardbook/the-address-book.jpg "Appearance of the Address Book"

