
# Step 1 orkestrasi

Jadi, apa itu orkestrasi? Yah, orkestrasi mungkin paling baik digambarkan menggunakan contoh. Katakanlah Anda memiliki aplikasi yang memiliki lalu lintas tinggi bersama dengan persyaratan ketersediaan tinggi. Karena persyaratan ini, Anda biasanya ingin menggunakan setidaknya 3+ mesin, sehingga jika tuan rumah gagal, aplikasi Anda masih dapat diakses dari setidaknya dua lainnya. Jelas, ini hanya sebuah contoh dan kasus penggunaan Anda kemungkinan akan memiliki persyaratan sendiri, tetapi Anda mendapatkan idenya.

Tetapi, dengan Perkakas orkestrasi, Anda biasanya dapat melepas sebagian besar pekerjaan manual ini dan membiarkan otomatisasi melakukan pekerjaan berat. Salah satu fitur keren Orkestrasi dengan Docker Swarm, adalah Anda dapat menggunakan aplikasi di banyak host dengan hanya satu perintah (setelah mode Swarm diaktifkan).

# Step 2 konfigurasi mode gerombolan

Aplikasi dunia nyata biasanya digunakan di beberapa host seperti yang dibahas sebelumnya. Ini meningkatkan kinerja aplikasi dan ketersediaan, serta memungkinkan komponen aplikasi individu untuk skala secara mandiri. Docker memiliki alat asli yang tangguh untuk membantu Anda melakukan ini.

Tapi, ini hanya pada satu node. Apa yang terjadi jika simpul ini turun? Nah, aplikasi kita baru saja mati dan tidak pernah restart. Untuk memulihkan layanan, kita harus masuk secara manual ke mesin ini, dan mulai mengubah hal-hal untuk membuatnya kembali dan berjalan. Jadi, akan sangat membantu jika kita memiliki beberapa jenis sistem yang memungkinkan kita menjalankan aplikasi / layanan "tidur" ini di banyak mesin.

- Step 2.1 buat simpul manager

- Step 2.2 bergabung dengan node pekerja ke swarm
hasil

# Step 3 menyebarkan aplikasi di beberapa host

Sekarang setelah Anda memiliki swarm up dan running, sekarang saatnya untuk menggunakan aplikasi tidur kami yang sangat sederhana.

- Step 3.1 menyebarkan komponen aplikasi sebagai layanan Docker


Status layanan dapat berubah beberapa kali hingga berjalan. Gambar sedang diunduh dari Docker Store ke mesin lain di Swarm. Setelah gambar diunduh, wadah masuk ke keadaan berjalan di salah satu dari tiga node. Pada titik ini mungkin tidak tampak bahwa kami telah melakukan sesuatu yang sangat berbeda dari hanya menjalankan a docker run .... Kami sekali lagi menggunakan satu wadah pada satu host. Perbedaannya di sini adalah bahwa wadah telah dijadwalkan pada gugus gerombolan. Sudah selesai dilakukan dengan baik. Anda telah menyebarkan aplikasi tidur ke Swarm baru Anda menggunakan layanan Docker.

# Step 4 skala aplikasi

Salah satu hal hebat tentang layanan adalah Anda dapat menaikkan dan menurunkannya untuk memenuhi permintaan. Pada langkah ini Anda akan meningkatkan skala layanan dan kemudian kembali.


# Step 5 kuras simpul dan jadwalkan ulang wadah

Aplikasi tidur Anda telah melakukan yang luar biasa setelah mencapai Reddit dan HN. Sekarang nomor 1 di App Store! Anda telah meningkatkan selama liburan dan turun selama musim yang lambat. Sekarang Anda sedang melakukan pemeliharaan di salah satu server Anda sehingga Anda harus dengan anggun mengeluarkan server dari kerumunan tanpa mengganggu layanan kepada pelanggan Anda.

