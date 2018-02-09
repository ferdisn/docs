# Email Infrastructure

Original note from Google Keep:

***
Dovecot replication
<http://blog.le-vert.net/?p=160> 

Tutorial basic mail
<https://www.rosehosting.com/blog/mailserver-with-virtual-users-and-domains-using-postfix-and-dovecot-on-a-centos-6-vps/>

Relayhost postfix utk smtp2go
<https://www.smtp2go.com/setupguide/postfix/>

IMAPS
<https://www.rosehosting.com/blog/set-up-ssl-encrypted-connection-in-postfix-dovecot-and-apache/>

IMAPS
STARTTLS di port 587
no auth di port 25
opportunistic di port 25

gedein ukuran mail
***
connect SSH Tunnel untuk PgAdmin `ssh -L 5433:localhost:5432 root_bellatrix`

<https://wiki.gentoo.org/wiki/Complete_Virtual_Mail_Server/Postfix_to_Database>

<http://shirkerphp.blogspot.co.id/2013/10/howto-rebuild-postfix-with.html>

reject_unknown_client akan menolak semua mail dari IP yang tidak punya PTR record. Simsalabim berkurang drastis.

variable untuk setting query postfix <http://www.postfix.org/pgsql_table.5.html>

REASSIGN OWNED <https://www.postgresql.org/docs/8.2/static/sql-reassign-owned.html> buat mindahin right ke user yang bener

# Dovecot Password Integration (dengan ini email yang disetup di Laravel beserta passwordnya akan berlaku utk otentikasi email dan alamatnya

Silakan disuling, banyak banget infonya.

<https://wiki2.dovecot.org/HowTo/DovecotPostgresql> basicnya
<https://wiki.dovecot.org/AuthDatabase/SQL>

<https://wiki.dovecot.org/Authentication/PasswordSchemes> password encryption

<https://www.christianroessler.net/tech/2014/auth-log-fix-pam-unix-dovecot-auth-error.html> pam_db interfering

debugging dovecot <https://wiki.dovecot.org/Debugging/Authentication>

variables in sql query <https://wiki.dovecot.org/Variables>

Blowfish not in glibc of RHEL, jadi, Laravel via PHP generate versi SHA512 khusus untuk dovecot. Laravel tetap di Blowfish.

this is the most direct answer <https://mad9scientist.com/dovecot-password-creation-php/>

bcrypt support in Red Hat <https://access.redhat.com/articles/1519843>

