# Ghost Detector Pro

Pemantau anomali berbasis sensor ponsel dalam satu file `index.html`. Tidak ada alat yang terbukti bisa mendeteksi hantu: setiap anomali hampir selalu punya sebab biasa (magnet, kabel, getaran lantai, derau, serangga di depan lensa).

## Fitur

- **Indeks anomali** 0 sampai 100 dari magnetometer, akselerometer, mikrofon, dan kamera, lengkap dengan level dan log kejadian.
- **Radar anomali**: sapuan dengan titik dari gerakan atau cahaya yang dilihat kamera, plus cincin EMF, suara, dan getaran 19 Hz.
- **Kamera**: deteksi gerak dan titik cahaya, mode malam, balik kamera, senter, tangkapan otomatis, dan gaya SLS (tampilan saja, bukan sensor kedalaman).
- **Rekam EVP otomatis**: klip pendek saat energi pita suara naik, bisa diputar ulang, diputar mundur, dan disimpan. Klip tidak diunggah.
- **Pelacak objek**: tiap area yang berubah diberi ID, jejak, kecepatan, dan arah (panah), lalu diklasifikasi (melintas, mendekat, menjauh, diam, berkedip). Objek besar, cepat, dan buram di dekat lensa diberi label `DEKAT?` dan skornya diturunkan karena biasanya serangga atau debu.
- **Resolusi adaptif**: kandidat diukur ulang pada 160×120 untuk kotak yang lebih rapat dan ukuran ketajaman tepi.
- **Kunci eksposur dan white balance** (kamera yang mendukung, umumnya Chrome Android), **frame-sync** lewat `requestVideoFrameCallback`, dan **penahan analisis** saat sensor gerak menunjukkan ponsel bergeser.
- **Deteksi kedip lampu** dari fluktuasi kecerahan antar frame, hanya dinilai saat pemandangan tenang, dan **penanda kemungkinan sumber inframerah** (CCTV, remote).
- **Eksposur panjang**: gerakan dan cahaya menumpuk sebagai jejak lalu memudar.
- **Bukti video**: rekam bergulir dengan pra-rekam sekitar 4 sampai 8 detik dan 3 detik sesudah anomali. Boros baterai, jadi dimatikan secara bawaan.
- **Filter manusia** (opsional): memuat model deteksi objek (TensorFlow.js dan COCO-SSD, versi dipatok, dari jsDelivr) hanya saat diaktifkan, lalu menandai orang sungguhan supaya tidak dihitung sebagai anomali. Butuh internet saat pertama dipakai.
- **Peringatan** getar dan bunyi pada level 2 ke atas.
- **Ekspor CSV** data tiap detik.

## Cara memakai

Buka lewat alamat `https://` (misalnya GitHub Pages), karena sensor dan kamera hanya jalan di konteks aman. Tekan "Mulai pemindaian", izinkan sensor, lalu arahkan ponsel ke satu area beberapa detik untuk kalibrasi.

**Posisi ponsel** (di pengaturan, tersimpan di browser):
- **Genggam atau bergerak** (bawaan): kamera mengompensasi geseran antar frame sehingga hanya gerakan independen yang dihitung, skor getaran 19 Hz diabaikan karena tremor tangan, dan latar magnet menyesuaikan lebih cepat (lonjakan mendadak tetap terbaca). Analisis kamera hanya ditahan bila ponsel diputar sangat cepat.
- **Diam di sandaran**: paling peka, cocok untuk sandaran atau tripod.

Saat dipegang, pembacaan EMF dan terutama getaran memang kurang andal. Gerakan kamera sangat cepat atau buram tetap tidak bisa dianalisis.

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
