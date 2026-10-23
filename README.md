# Laura Virtual Assistant: paket PWA dan APK

Isi paket: `docs/` (aplikasi web + PWA), `assets/icon-only.png` (ikon Laura), `.github/workflows/android.yml` (pembuat APK otomatis, gratis), `capacitor.config.json`, `package.json`.

## Jalur A: PWA (Android dan Windows)
1. Buat akun GitHub, lalu repositori baru berstatus **Public** (misalnya `laura-assistant`). GitHub Pages gratis hanya untuk repositori public.
2. Unggah seluruh isi folder ini (Add file, Upload files). Pastikan folder `.github` ikut terunggah. Jika tidak terlihat di komputer, aktifkan "tampilkan file tersembunyi", atau buat manual lewat Add file, Create new file dengan nama `.github/workflows/android.yml` lalu tempel isinya.
3. Settings, Pages, Source: Deploy from a branch, Branch `main`, folder `/docs`, Save.
4. Tunggu 1 sampai 2 menit. Alamatnya `https://NAMA-GITHUB-ANDA.github.io/laura-assistant/`.
5. Android (Chrome): menu tiga titik, Instal aplikasi. Windows (Edge): menu tiga titik, Apps, Install this site as an app.

## Jalur B: APK Android (pengingat jalan saat aplikasi tertutup)
1. Di repositori yang sama buka tab **Actions**, pilih **Build Laura APK**, lalu Run workflow (juga berjalan otomatis setiap ada perubahan).
2. Tunggu sekitar 5 sampai 10 menit sampai tanda centang hijau. Buka run tersebut, bagian Artifacts, unduh **Laura-APK**.
3. Ekstrak zip, kirim `app-debug.apk` ke HP, buka, dan izinkan "instal dari sumber tidak dikenal".
4. Saat pertama dibuka, izinkan **Notifikasi** dan **Alarm dan pengingat**. Lalu di Pengaturan HP, Aplikasi, Laura, Baterai, pilih **Tanpa pembatasan**.

## Cara kerja pengingat
- **APK:** pengingat salat dan jadwal dijadwalkan ke sistem Android untuk 7 hari ke depan. Jadwal diperbarui setiap Laura dibuka atau data berubah, jadi buka Laura minimal seminggu sekali. Saat aplikasi tertutup yang muncul adalah notifikasi bersuara. Suara Laura sendiri hanya terdengar saat aplikasi terbuka.
- **PWA:** pengingat hanya berjalan saat aplikasi terbuka. PWA tidak bisa menjadwalkan alarm saat tertutup.
- Waktu salat dihitung perkiraan untuk Jakarta (parameter Kemenag RI). Cocokkan dengan jadwal resmi atau masjid terdekat.

## Pengaturan di panel Laura (Pengaturan suara)
- **API key Anthropic:** diperlukan agar chat AI Laura aktif di aplikasi mandiri. Berbayar per pemakaian. Tersimpan hanya di perangkat Anda. Jika kosong, jadwal, pengingat, dan salat tetap berfungsi.
- **Link agen D-ID:** tempel link share agen Anda untuk tombol Laura Video.
- **Jangan menaruh API key atau link D-ID di file repositori public.** Isi hanya lewat Pengaturan di perangkat.

## Batasan
- APK ini berstatus debug (untuk dipasang sendiri, bukan untuk Play Store).
- Ikon dibuat dari foto beresolusi rendah, sehingga agak lembut. Ganti `assets/icon-only.png` dengan foto yang lebih tajam (1024 x 1024) bila ada.
- Data tersimpan per perangkat dan tidak otomatis sinkron antara HP dan laptop.
