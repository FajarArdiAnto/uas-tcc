# Beginner linux

Di lab ini, kita akan melihat beberapa perintah Docker dasar dan alur kerja build-ship-run sederhana. Kami akan mulai dengan menjalankan beberapa wadah sederhana, lalu kami akan menggunakan Dockerfile untuk membangun aplikasi khusus. Terakhir, kita akan melihat cara menggunakan bind mounts untuk memodifikasi wadah yang sedang berjalan seperti yang Anda lakukan jika Anda secara aktif mengembangkan menggunakan Docker.

# Klon Repo GitHub Lab

Gunakan perintah berikut untuk mengkloning repo lab dari GitHub (Anda dapat mengklik perintah atau mengetiknya secara manual). Ini akan membuat salinan repo laboratorium di sub-direktori baru bernama.

# Tugas 1: Jalankan beberapa wadah Docker sederhana

Ada berbagai cara untuk menggunakan wadah. Ini termasuk:

Untuk menjalankan satu tugas: Ini bisa berupa skrip shell atau aplikasi khusus. Interaktif: Ini menghubungkan Anda ke wadah yang mirip dengan cara Anda SSH ke server jauh. Di latar belakang: Untuk layanan jangka panjang seperti situs web dan basis data. Di bagian ini Anda akan mencoba masing-masing opsi tersebut dan melihat bagaimana Docker mengelola beban kerja.

Jalankan satu tugas dalam wadah Alpine Linux
Pada langkah ini kita akan memulai sebuah wadah baru dan memerintahkannya untuk menjalankan hostnameperintah. Wadah akan mulai, jalankan hostnameperintah, lalu keluar.

Jalankan perintah berikut di konsol Linux Anda

Docker menjaga wadah berjalan selama proses itu dimulai di dalam wadah masih berjalan. Dalam hal ini hostnameproses keluar segera setelah output ditulis. Ini artinya wadah berhenti. Namun, Docker tidak menghapus sumber daya secara default, sehingga wadah masih ada di Exitednegara.

Jalankan wadah Ubuntu interaktif
Anda dapat menjalankan sebuah wadah berdasarkan versi Linux yang berbeda dari yang dijalankan pada host Docker Anda.

Dalam contoh berikut, kita akan menjalankan wadah Ubuntu Linux di atas host Alpine Linux Docker (Play With Docker menggunakan Alpine Linux untuk node-node-nya).

Jalankan wadah Docker dan akses cangkangnya.

Jalankan perintah berikut dalam wadah.

ls /akan mencantumkan isi direktur root dalam wadah, ps auxakan menunjukkan proses yang berjalan dalam wadah, cat /etc/issueakan menunjukkan distro Linux mana wadah berjalan, dalam hal ini Ubuntu 18.04.3 LTS.

Ketik exituntuk meninggalkan sesi shell. Ini akan menghentikan bashproses, menyebabkan wadah untuk keluar.

Untuk bersenang-senang, mari kita periksa versi host VM kami.

Jalankan latar belakang wadah MySQL
Kontainer latar belakang adalah cara Anda menjalankan sebagian besar aplikasi. Berikut ini contoh sederhana menggunakan MySQL.

docker container execmemungkinkan Anda untuk menjalankan perintah di dalam sebuah wadah. Dalam contoh ini, kita akan gunakan docker container execuntuk menjalankan setara baris perintah mysql --user=root --password=$MYSQL_ROOT_PASSWORD --versiondi dalam wadah MySQL kita.


Ketik exituntuk meninggalkan sesi shell interaktif.

# Tugas 2: Paket dan menjalankan aplikasi khusus menggunakan Docker

Bangun gambar situs web sederhana
Mari kita lihat Dockerfile yang akan kita gunakan, yang membangun situs web sederhana yang memungkinkan Anda mengirim tweet.

Pastikan Anda berada di linux_tweet_appdirektori.

Tampilkan konten Dockerfile.

Untuk membuat perintah berikut ini lebih ramah salin / tempel, ekspor variabel lingkungan yang berisi DockerID Anda (jika Anda tidak memiliki DockerID, Anda bisa mendapatkannya secara gratis melalui Docker Hub ).

Gema nilai variabel kembali ke terminal untuk memastikan itu disimpan dengan benar.

Gunakan docker image buildperintah untuk membuat gambar Docker baru menggunakan instruksi di Dockerfile.

# Tugas 3: Memodifikasi situs web yang sedang berjalan

Ketika Anda secara aktif mengerjakan aplikasi, tidak nyaman harus menghentikan wadah, membangun kembali gambar, dan menjalankan versi baru setiap kali Anda membuat perubahan pada kode sumber Anda.

Salah satu cara untuk merampingkan proses ini adalah dengan memasang direktori kode sumber pada mesin lokal ke wadah yang sedang berjalan. Ini akan memungkinkan setiap perubahan yang dilakukan pada file pada host segera tercermin dalam wadah.

Kami melakukan ini menggunakan sesuatu yang disebut bind mount .

Saat Anda menggunakan bind mount, file atau direktori pada mesin host dipasang ke sebuah wadah yang berjalan di host yang sama.

# Mulai aplikasi web kami dengan bind mount

Mari mulai aplikasi web dan pasang direktori saat ini ke dalam wadah. Dalam contoh ini kita akan menggunakan --mountbendera untuk memasang direktori saat ini di host ke /usr/share/nginx/htmldalam wadah. Pastikan untuk menjalankan perintah ini dari dalam linux_tweet_appdirektori pada host Docker Anda.
Ubah situs web yang berjalan
Bind mounts berarti bahwa setiap perubahan yang dilakukan pada sistem file lokal segera tercermin dalam wadah yang berjalan.

# Salin yang baru index.htmlke dalam wadah.

Repo Git yang Anda tarik sebelumnya berisi beberapa versi file index.html yang berbeda. Anda dapat secara manual menjalankan lsperintah dari dalam ~/linux_tweet_appdirektori untuk melihat daftar mereka. Pada langkah ini kita akan ganti index.htmldengan index-new.html.

Buka situs web yang sedang berjalan dan segarkan halaman . Perhatikan bahwa situs tersebut telah berubah.