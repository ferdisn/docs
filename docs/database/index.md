# Database Model

ON CASCADE DELETE   
Secara umum tidak ada proses penghapusan untuk tiap baris, apabila ada kebutuhan, boleh dipertimbangkan untuk ada asal ada kemampuan untuk mempertahankan backup berkala.

ON CASCADE UPDATE   
Secara umum tidak perlu ada update atas nilai PK, karena PK memakai surrogate key.