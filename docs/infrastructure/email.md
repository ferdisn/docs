At this point, very basic Postfix and Dovecot. Username controlled purely from a text file configuration.

Plan:

Kapasitas $15 dari DO lumayan menarik. Setidaknya 200rb bisa buat pakai 100 account yang juga belum tentu semuanya aktif.

So, tantangannya dengan layanan eksisting:

1. Akses webmail: Roundcube: [link](https://webmail.paragita.com) tapi murni cuma buat imel-imelan.
2. Penerangan soal cara konfigurasi IMAP/SMTP ke klien email: Thunderbird, Outlook (should we? probably no), emClient (personally pake), Gmail on Android, Apple Mail, iOS Mail, Android Mail (beda ama Gmail on Android).

Okay, usually email goes hand in hand with calendaring dan contact.
So what? Baikal already exists but no way to ask user to install CardDAV-Sync and CalDAV-Sync to their phone, mind you, they're paid apps. iOS users are in luck, DAV thingy is built-in. Apalagi minta mereka semua seragam pakai thunderbird.

Baikal dan upstreamnya sabre/* akan EOL. Probably better find another way to store Card and Cal things.

OTOH, mungkin anak-anak ini blm mengutilisasi fitur kalender, jadi masih bisa cari alternatif yang bisa bertahan long term.

[link](http://pjrlost.blogspot.co.id/2012/11/smtp-delivery-to-two-mail-servers-via.html)
Pake ini untuk split email, pertama ke capella, kedua ke server baru untuk pengujian. Jalanin paralel 3 bulan. Ingat kalau direktif Mailcow terlalu agresif, invoice gojek aja ga tembus karena ga dikirim dari domain yang existing.