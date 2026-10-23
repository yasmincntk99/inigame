# Gaameai – Tiga Jalur

Game MOBA 2D ringan (HTML5 canvas, satu file, tanpa library). Aset dan kode orisinal.

## Cara main

1. Pilih peta dan hero dasar (Penjaga, Pemanah, Penyihir).
2. **Draft skill ala Legends of Dota**: pilih 3 skill biasa + 1 ultimate dari 12 skill (atau tekan *Acak*). Urutan pilihan menentukan tombol Q, W, E; ultimate di R.
3. Ketuk tanah untuk berjalan, ketuk musuh untuk menyerang. Skill dipakai dengan tombol di layar atau keyboard Q W E R (tanpa membidik, cocok untuk HP).
4. Kumpulkan emas dari kill dan waktu, belanja di **Toko** (pedang, zirah, sepatu, jimat cooldown, cincin pemulih). Game berhenti sementara saat toko terbuka.
5. Hancurkan markas merah. Musuh juga membawa skill acak.
6. Kamp hutan (bulatan cokelat) memberi emas dan level; kamp hidup lagi setelah 45 detik. Kamp besar memberi lebih banyak.

## Peta

| Peta | Isi | Durasi kira-kira |
|---|---|---|
| Tiga Jalur | 3 jalur, 6 kamp hutan | 5 menit |
| Lembah Dua Jalur | 2 jalur melengkung, kamp besar di tengah | 5 menit |
| Arena Kilat | 1 jalur berkelok, 2 hero musuh | 2–4 menit |

Menambah peta baru cukup menambah satu objek di array `MAPS` di `index.html`: ukuran, posisi dua markas, titik belok tiap jalur, posisi menara, kamp hutan, jumlah creep per jalur, jumlah hero musuh, dan warna tema. Thumbnail di layar pilih peta digambar otomatis dari data itu. Jaga kamp minimal sekitar 300 piksel dari jalur supaya creep jalur tidak menyerangnya.

## Skill

Biasa: Tebasan Putar, Panah Kilat, Hentak Bumi (stun), Kabut Lambat (slow), Terjang (dash), Pemulihan, Hisap Nyawa, Perisai Batu.
Ultimate: Meteor, Amuk, Gempa Agung, Penghukum.

Menambah skill baru cukup menambah satu baris di array `SKILLS` di `index.html`. Tipe yang tersedia: `burst`, `bolt`, `stun`, `slow`, `dash`, `heal`, `drain`, `buff`, `execute`.

## Grafik (pixel art)

Semua gambar digambar lewat kode di `index.html`, tanpa file gambar, jadi tetap satu file dan orisinal. Sprite berukuran 14x14 piksel, diberi outline otomatis, lalu disimpan sekali ke kanvas tersembunyi dan ditempel ulang tiap frame.

- **Penjaga:** ksatria berhelm berbulu, perisai besar, pedang.
- **Pemanah:** tudung hijau, tabung panah, busur.
- **Penyihir:** topi runcing, jubah ungu bertabur bintang, tongkat berbola.
- Tim dibedakan lewat warna aksen (hijau kebiruan = kamu, merah = musuh) dan cincin di kaki hero. Hero musuh memakai salah satu dari tiga sprite itu.
- Prajurit jalur, lumpur hutan (kamp biasa dan kamp besar), menara, dan markas punya sprite sendiri.
- Tanah, jalur, dan dekorasi (pohon, kristal, kaktus, batu) mengikuti tema tiap peta. Dekorasi ditaruh otomatis dengan seed tetap dan tidak menutup jalur, kamp, atau markas.

Menambah atau mengubah sprite cukup menambah satu entri di `SPRDEF` (daftar kotak warna `p(x,y,lebar,tinggi,warna)`).

## Ringan (LOD)

Unit jauh dari kamera diproses lebih jarang dan digambar sebagai titik; unit di luar layar tidak digambar.

## Jalankan

Buka `index.html` di browser, atau aktifkan GitHub Pages (Settings → Pages → branch `main`).
