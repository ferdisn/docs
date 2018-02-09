# Member Management
## API Design

| HTTP Verb | Endpoint | Description |
| ------------- | ------------- | ------------- |
| GET | /member | get all member |
| GET | /member/{id} | get one member |
| POST | /member | create new member |
| PUT | /member | update member |
| DELETE | /member/{id} | delete member |

## Web App

| HTTP Verb | Endpoint | Description |
| ------------- | ------------- | ------------- |
| GET | /member | get all member |
| GET | /member/{id} | get one member |
| POST | /member | create new member |
| PUT | /member | update member |
| DELETE | /member/{id} | delete member |
| GET | /member/{id}/edit | open form for edit |

PUT ga ada dalam form.method.
Elemen data member yang sekarang diturunkan jadi one-to-many seperti Contact, Education, Address mau dimanage terpisah dari API ini atau digabung? direplace atau diappend?

1. nyari sdm job
   * bagian dari siklus member management, tapi bukan mayor, cuma penyedia data. Kalo dari deskripsi existing, mereka kesulitan cari data orang di luar angkatan aktif, artinya khusus keperluan job ini harus ada flag yang menandakan orang-orang yang available untuk ditanya2in soal job regardless of its angkatan. Kebijakan dari BPH sendiri gmn? apakah privilege ikut job masih lekat ke orang yang registrasi ulang atau engga?
2. ulang tahun (ini pd dasarnya baca birthDay member, trus kirim reminder yang prepared, via email dan SMS, ditrigger cronjob laravel. apakah reminder untuk HCD saja, atau mau untuk member langsung juga?_
   * pengingat ulang tahun (mungkin H-3)
   * pengingat hari H
   * sebagai tambahan bisa pake [SMS Gateway](../Environments#SMS-Gateway "popup") untuk notifikasi SMS, incur cost jadi minimize.
3. pendataan anggota
   * apakah dibatasi dari anggota yang udah jelas diterima, atau mau cover case rekrutmen? NB: rekrutmen bisa dipisah ke sistem sendiri yang lebih kecil, DB terpisah, atau kalau mau masih tradisional bisa tetap dengan google form, mengingat kalo handle user 500 ukuran droplet digitalocean yang dipake harganya di luar kesanggupan gw.
4. kehadiran
   * seperti nomor satu, masih hanya bagian kecil dari member management. Kemungkinan ini mayornya di event management, tapi apakah event harus dipersempit menjadi konser dan job? Atau dianggap sama saja namun beda skala?
5. manajemen info untuk keperluan graduation, misal menandai tanggal tertentu dan mengasumsikan perkiraan kelulusan dari masing-masing anggota mengikuti status pendidikan di UI mereka.
   * implikasinya, object Education harus diperluas, tapi ga wajib, jadi ntar orang HCD bisa dapet reminder untuk cari info lebih dahulu

problem yang sering terjadi: ref #1 nyari ke mana apabila angkatan yang aktif habis