# Application Containerization and Microservice Orchestration

Dalam tutorial ini kita akan belajar tentang kontainerisasi aplikasi dasar menggunakan Docker dan menjalankan berbagai komponen aplikasi sebagai layanan microser. Kami akan menggunakan Docker Compose untuk orkestrasi selama pengembangan. Tutorial ini ditargetkan untuk pemula yang memiliki pengetahuan dasar dengan Docker. Jika Anda baru menggunakan Docker, kami sarankan Anda untuk memeriksa tutorial Docker untuk Pemula terlebih dahulu.

Kami akan mulai dari skrip Python dasar yang mengikis tautan dari laman web tertentu dan secara bertahap mengubahnya menjadi tumpukan aplikasi multi-layanan. Kode demo tersedia di repo Link Extractor . Kode ini disusun dalam langkah-langkah yang secara bertahap memperkenalkan perubahan dan konsep baru. Setelah selesai, tumpukan aplikasi akan berisi layanan microser berikut:

- Aplikasi web yang ditulis dalam PHP dan disajikan menggunakan Apache yang mengambil URL sebagai input dan merangkum tautan yang diekstrak darinya
- Aplikasi web berbicara ke server API yang ditulis dengan Python (dan Ruby) yang menangani ekstraksi tautan dan mengembalikan respons JSON
- Cache Redis yang digunakan oleh server API untuk menghindari pengambilan berulang dan ekstraksi tautan untuk halaman yang sudah dikikis
- Pengaturan Panggung
Mari kita mulai dengan kloning repositori kode demo, mengubah direktori kerja, dan memeriksa democabang keluar.

# Langkah 0: Skrip Extractor Tautan Dasar

# Langkah 1: Script Extractor Tautan Kontainer

# Langkah 2: Tautkan Modul Extractor dengan URI Lengkap dan Anchor Text

# Langkah 3: Layanan Link Extractor API

# Langkah 4: Link Extractor API dan Layanan Front Web

# Langkah 5: Layanan Redis untuk Caching

# Langkah 6: Tukar Layanan API Python dengan Ruby

Beberapa perubahan signifikan dari langkah sebelumnya meliputi:

Layanan API yang ditulis dengan Python diganti dengan implementasi Ruby yang serupa
Itu API_ENDPOINT variabel lingkungan diperbarui ke titik ke layanan API Ruby baru
Kejadian cache ekstraksi tautan (HIT / MISS) dicatat dan dipertahankan menggunakan volume