## Referensi Konfigurasi

| Variabel | Nilai |
| - | - |
| Sistem Operasi | CentOS 7 |
| Paket tambahan | `telnet`<br>`nmap`<br>`firewalld` |

Hal yang dilakukan setelah membuat *instance*:

* Matikan (atau hapus) `postfix` untuk menutup port `25` [^1]
* Matikan `rpcbind` untuk menutup port `111` [^2]
* Nyalakan `firewalld` [^3]

Perintah:
```
# systemctl stop postfix
# systemctl disable postfix
# systemctl stop rpcbind
# systemctl disable rpcbind
# systemctl start firewalld
# systemctl enable firewalld
```
[^1]: Normalnya tidak dibutuhkan, kecuali untuk kasus Web.
[^2]:
    Lihat di [sini](https://forums.fedoraforum.org/showthread.php?282560-rpcbind-service-disabled-but-runs-on-startup-anyway), di [sini](https://superuser.com/a/1281946)
[^3]:
    Versi terbaru CentOS 7 tidak memasang firewalld secara standar.


