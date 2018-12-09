## Persyaratan dasar

Firewall Rule

EPEL
Nginx
PHP-FPM v7

separate php-fpm process per user
separate nginx web directory per user


Firewall-CMD
firewall-cmd --get-default-zone = note jawabannya
firewall-cmd --zone=public --permanent --add-service=http
firewall-cmd --zone=public --permanent --add-service=https
firewall-cmd --reload

Nginx
yum install epel-release
yum install nginx

config


PHP-FPM
install
https://blog.remirepo.net/pages/Config-en
install package remirepo
enable repo php-fpm yang dimau


new users (adduser)
didi
ferdi
bayu
paragita

prepare dirs
mkdir /var/webapp
chmod g+s webapp
chown root:nginx webapp
mkdir /var/webapp/didi,ferdi,bayu,paragita

selinux
semanage fcontext -a -t httpd_log_t "/var/webapp/[^/]+/logs(/.*)?"
semanage fcontext -a -t httpd_var_run_t "/var/webapp/[^/]+/php-fpm-session(/.*)?"
setsebool httpd_can_sendmail 1 = biar bisa send email
setsebool httpd_can_network_connect 1 = biar roundcube bisa akses imap
setsebool httpd_can_network_connect_db 1 = biar bisa akses db network

/etc/hosts
ip capella.pojoksantai.com #email
ip db.pojoksantai.com #database

/etc/postfix/main.cf
relayhost = [capella.pojoksantai.com]

systemctl enable postfix
systemctl start postfix

https://blog.ferdi.id/2017/12/23/instalasi-nginx/ -> setup nginx.conf


https://blog.ferdi.id/2017/12/23/instalasi-php-fpm/ -> setup pool php-fpm

pindahin file
scp -r motorscene/ bayu_web:/var/webapp/bayu/files/

systemctl enable nginx
systemctl enable php-fpm

force postfix to resolve natively
https://www.linuxquestions.org/questions/linux-software-2/force-postfix-to-refer-etc-hosts-857662/
smtp_host_lookup = native in main.cf

semanage mungkin ga bisa pake rule yang bener-bener fleksibel. Mungkin folder yang berupa wordpress bisa diprepend dengan "wp_" gitu sehingga bisa ditarget lebih presis. Saat ini dia filenya bisa diupdate, tapi ga bisa dicreate sama proses php-fpm under nama user bersangkutan.

move sertifikat first -> selinuxnya juga, selinux tu buat postfix


roundcube better off reinstallling

baikal try reinstalling first, then moving 

database didi yang banyak plugin ajaibnya, harus diperiksa sql dumpnya