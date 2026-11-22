# Instal Mimoto OS di mini PC booth

Panduan ini menuntun kamu memasang Mimoto OS ke mini PC booth foto, dari mengunduh file sampai booth aktif. Installer-nya berjalan sendiri, jadi kamu tinggal mengikuti 12 langkah di bawah secara berurutan.

> [!NOTE]
> Mimoto OS ini masih versi uji dan terhubung ke server uji. Versi ini belum untuk dijual.

> [!WARNING]
> Isi disk mini PC akan dihapus total saat instal. Pindahkan dulu data penting yang ada di mini PC itu.

## Siapkan ini dulu

- Mini PC x86 64-bit (prosesor Intel atau AMD) dengan **satu** disk internal.
- Flashdisk minimal 4 GB.
- Keyboard USB, cukup pinjam sebentar. Keyboard hanya dipakai di langkah 4 untuk memilih flashdisk di menu boot. Setelah itu semua lewat layar.
- Komputer lain (Mac atau Windows) untuk menulis installer ke flashdisk.
- Aplikasi balenaEtcher di komputer itu. Aplikasinya gratis, unduh di [etcher.balena.io](https://etcher.balena.io).

## File yang kamu unduh

Installer Mimoto OS berbentuk satu file ISO.

| | |
|---|---|
| Nama file | `mimoto-os-v2-a4995e0.iso` |
| Ukuran | 1,30 GB (1.296.171.008 byte) |
| SHA256 | `dbdce34848ce1ccf020db02dfe5d638f5df76cc445d6d617044b9a64b8093431` |

SHA256 adalah kode untuk memastikan file yang kamu unduh sama persis dengan file aslinya. Cara mengeceknya ada di bagian paling bawah, dan langkah itu opsional.

## Bagian 1. Buat flashdisk installer

Bagian ini kamu kerjakan di komputer Mac atau Windows.

1. Unduh file ISO dari halaman **Releases** repo ini.
2. Colok flashdisk ke komputer, lalu buka balenaEtcher.
   - Klik **Flash from file**, lalu pilih file ISO tadi.
   - Klik **Select target**, lalu pilih flashdisk kamu. Cek ukurannya supaya kamu tidak salah pilih disk.
   - Klik **Flash**, lalu tunggu sampai proses **Validating** selesai.

## Bagian 2. Instal ke mini PC

3. Colok flashdisk ke mini PC. Kabel LAN boleh ikut dicolok, tapi tidak wajib untuk instal.
4. Nyalakan mini PC, lalu buka menu boot. Lewat menu ini kamu menyuruh mini PC menyala dari flashdisk.
   - Di HP EliteDesk, tekan **Esc** berulang saat mini PC menyala, pilih **Boot Menu**, lalu pilih yang namanya diawali **UEFI: USB**.
   - Di merek lain, tombolnya biasanya **F12**, **F11**, **F9**, atau **Esc**.
5. Installer berjalan sendiri tanpa perlu keyboard. Layar menampilkan peringatan bahwa disk akan dihapus, disertai hitung mundur 15 detik. Kalau mau batal, cabut flashdisk sebelum hitungannya habis.
6. Kalau mini PC punya lebih dari satu disk internal, installer berhenti demi keamanan. Cabut disk tambahannya, lalu ulangi dari langkah 4.
7. Tunggu sekitar 3–5 menit sampai instal selesai dan mini PC mati sendiri. Setelah itu cabut flashdisk, lalu nyalakan mini PC lagi.
8. Saat pertama menyala, mini PC menyiapkan booth selama sekitar 2–10 menit. Tahap ini tidak butuh internet. Jangan matikan mini PC, karena nanti ia restart sendiri.

## Bagian 3. Hubungkan booth ke akun kamu

Setelah restart, layar menampilkan tulisan **Belum pairing**. Pairing artinya menghubungkan booth ini ke akun Mimoto kamu.

9. Sambungkan booth ke internet. Colok kabel LAN, atau tekan **Atur WiFi** dan isi lewat keyboard di layar.
10. Ganti nama booth. Tekan **Nama booth (ubah)**, lalu ketik namanya lewat keyboard di layar. Contoh: `playframe-01`. Aturan namanya:
    - hanya huruf kecil a–z, angka, dan tanda minus (-)
    - panjangnya 1–63 karakter
    - tidak diawali atau diakhiri tanda minus
    - tidak sama dengan nama booth lain di akun yang sama
11. Layar booth menampilkan kode pairing 8 karakter yang berlaku 10 menit. Buka dashboard Mimoto, login, lalu masukkan kode itu. Setelah itu, tekan **Ya, ini akun saya** di layar booth.
12. Booth sudah aktif. Kamera dan printer boleh kamu colok kapan saja, dan printer terdaftar otomatis. Untuk mengeceknya, buka menu **Tes Perangkat**. Di situ ada tombol **Deteksi printer**.

## Kalau instalnya gagal

Kalau instal gagal, layar berubah merah dan menampilkan dua pilihan, **Coba lagi** dan **Matikan komputer**. Foto layarnya, lalu kirim fotonya ke tim Mimoto.

## Perangkat yang didukung

| Jenis | Perangkat | Status |
|---|---|---|
| Kamera | Canon DSLR/mirrorless: 3000D, 4000D, 1200D, 1300D, 1500D, 2000D, 100D, 600D, 700D, 750D, 800D, M50, 60D, 70D, 80D, R100, R50, RP, R7 | Didukung |
| Printer | Epson L8050 | Didukung, sudah dites di perangkat asli |
| Printer | Epson L18050, DNP RX1HS, Canon SELPHY | Driver ada, belum dites di perangkat asli |
| Printer | Epson SureLab D530 | Belum didukung, tidak ada driver Linux |
| Kamera | Webcam USB | Belum didukung |

## Cek file ISO (opsional)

**Mac.** Buka Terminal, ketik perintah di bawah, lalu seret file ISO ke jendela Terminal dan tekan Enter.

```
shasum -a 256
```

**Windows.** Buka PowerShell, lalu jalankan perintah ini.

```
Get-FileHash mimoto-os-v2-a4995e0.iso
```

Hasilnya harus sama dengan SHA256 di tabel file di atas.
