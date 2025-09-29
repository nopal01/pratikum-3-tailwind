Beberapa Catatan dan Refleksi
1. Pengaturan Grid Foto (grid-cols dan gap)
Saya mengatur grid dan jaraknya agar enak dilihat di semua ukuran layar, dari HP sampai desktop. Pertimbangannya begini:

Tampilan HP (Default): grid-cols-2, gap-1
Untuk layar kecil, saya putuskan pakai 2 kolom (grid-cols-2). Walaupun Instagram aslinya pakai 3 kolom, saya rasa dengan 2 kolom, tiap foto jadi sedikit lebih besar dan lebih jelas. Jaraknya (gap-1) saya buat sangat tipis, hanya sebagai garis pemisah agar mirip dengan tampilan asli Instagram.

Tampilan Tablet (md): md:grid-cols-3, md:gap-4
Saat layar lebih lebar seperti di tablet, 3 kolom (md:grid-cols-3) jadi pilihan yang paling pas. Tampilannya langsung terasa familiar seperti Instagram versi web. Jarak antar fotonya (md:gap-4) saya perlebar sedikit supaya tidak terlalu padat dan lebih nyaman dilihat.

Tampilan Desktop (lg): lg:grid-cols-4, lg:gap-6
Di layar desktop yang luas, saya manfaatkan dengan menampilkan 4 kolom (lg:grid-cols-4). Dengan begini, lebih banyak foto yang bisa terlihat dalam sekali pandang. Jaraknya (lg:gap-6) juga saya buat paling lebar di sini agar seluruh tata letak terlihat bersih dan tidak sesak.

2. Solusi Masalah Layout dengan Class Responsif
Tantangan utamanya adalah mengubah layout yang di HP tersusun ke bawah (vertikal) menjadi menyamping (horizontal) di desktop. Class responsif dari Tailwind sangat membantu untuk ini.

Mengatur Header Profil: Di HP, kalau foto profil dan bio ditaruh menyamping, pasti jadi sempit. Solusinya, saya buat susunannya ke bawah (flex-col). Begitu masuk ukuran tablet (md:), susunannya otomatis berubah jadi menyamping (md:flex-row). Ini cara yang simpel tapi langsung menyelesaikan masalah.

Menukar Posisi Elemen: Saya perhatikan, posisi blok statistik (jumlah post, follower) di aplikasi HP dan web itu berbeda. Untuk menirunya, saya pakai utility order. Dengan memberi class order-3 md:order-2 pada blok statistik, posisinya bisa "melompat" ke atas bio saat di tampilan desktop, tanpa mengubah struktur di HTML-nya.

Membuat Tombol Adaptif: Tombol "Edit Profile" juga saya buat berbeda. Di HP, ukurannya saya buat penuh (w-full) agar mudah disentuh jari. Tapi di desktop, tombolnya kembali ke ukuran normal (md:w-auto) dan posisinya pindah ke samping username.

3. Untung Rugi Pakai Utility Class vs Bikin Komponen Sendiri
Selama mengerjakan tugas ini, saya jadi lebih paham plus minus antara menulis banyak class langsung di HTML (cara Tailwind) dengan membuat class komponen di file CSS terpisah.

Pakai Banyak Utility Class
Enaknya: Cepat sekali! Desain bisa langsung jadi di file HTML, tidak perlu bolak-balik ke file CSS atau pusing mikirin nama class yang bagus.
Tidak enaknya: Kalau komponennya agak rumit, tag HTML-nya jadi ramai sekali dengan class yang panjang. Kalau ada 10 tombol yang desainnya sama, kita harus menyalin-tempel class yang sama itu 10 kali.

Bikin Class Komponen (misal pakai @apply)
Enaknya: HTML jadi jauh lebih bersih dan rapi (misalnya, cukup tulis class="tombol-utama"). Kalau mau ganti desain tombol, cukup ubah di satu tempat di file CSS.
Tidak enaknya: Sedikit lebih lambat karena harus pindah-pindah file. Kadang kita juga bisa terjebak membuat class komponen yang sebenarnya hanya dipakai sekali.

Kesimpulan saya: Untuk proyek satu halaman seperti ini, pakai utility class langsung di HTML adalah cara yang paling efisien. Tapi kalau nanti mengerjakan proyek yang lebih besar dengan banyak komponen berulang (seperti tombol, kartu, atau notifikasi), mungkin lebih baik sebagian desainnya diekstrak menjadi komponen agar kode lebih mudah dikelola.
