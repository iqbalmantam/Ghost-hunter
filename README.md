# Ghost Detector Pro

Pemantau anomali berbasis sensor ponsel dalam satu file `index.html`. Tidak ada alat yang terbukti bisa mendeteksi hantu: setiap anomali hampir selalu punya sebab biasa (magnet, kabel, getaran lantai, derau, serangga di depan lensa).

## Fitur

- **Indeks anomali** 0 sampai 100 dari magnetometer, akselerometer, mikrofon, dan kamera, lengkap dengan level dan log kejadian.
- **Radar anomali**: sapuan dengan titik dari gerakan atau cahaya yang dilihat kamera, plus cincin EMF, suara, dan getaran 19 Hz.
- **Kamera**: deteksi gerak dan titik cahaya, mode malam, balik kamera, senter, tangkapan otomatis, dan gaya SLS (tampilan saja, bukan sensor kedalaman).
- **Rekam EVP otomatis**: klip pendek saat energi pita suara naik, bisa diputar ulang, diputar mundur, dan disimpan. Klip tidak diunggah.
- **Peringatan** getar dan bunyi pada level 2 ke atas.
- **Ekspor CSV** data tiap detik.

## Cara memakai

Buka lewat alamat `https://` (misalnya GitHub Pages), karena sensor dan kamera hanya jalan di konteks aman. Tekan "Mulai pemindaian", izinkan sensor, lalu letakkan ponsel diam di permukaan datar beberapa detik untuk kalibrasi.

## Kompatibilitas

| Fitur | Chrome Android | Safari iPhone | Desktop Chrome |
| --- | --- | --- | --- |
| Magnetometer (EMF) | Ya, perlu flag `Generic Sensor Extra Classes` | Tidak | Tidak ada sensor |
| Akselerometer (getaran) | Ya | Ya, setelah izin gerak | Biasanya tidak ada |
| Mikrofon dan spektrogram | Ya | Ya | Ya |
| Kamera dan radar | Ya | Ya | Ya |
| Senter | Ya, jika kamera belakang mendukung | Tidak | Tidak |
| Rekam EVP | Ya | Ya (format M4A) | Ya |
| Getar peringatan | Ya | Tidak | Tidak |

## Batas alat

Web tidak punya akses ke sensor suhu, jadi titik dingin tidak diukur. Mikrofon ponsel memotong frekuensi sangat rendah, jadi infrasonik dibaca lewat getaran. Gaya SLS hanya meniru tampilan kamera SLS dari gerakan yang terlihat kamera biasa.

Developed by iqbalmantam
