# Weighbridge Ledger — Official Releases

Repositori ini khusus digunakan sebagai jalur distribusi resmi **installer aplikasi Windows** dan metadata pembaruan otomatis (*offline-first updater*) untuk **Weighbridge Ledger**.

- Halaman unduhan installer: [Releases](https://github.com/luplupshi/weighing-releases/releases)
- Berkas distribusi per rilis:
  - `Setup-Weighbridge-<versi>.exe` — Installer mandiri Windows (sudah menyertakan Java Runtime).
  - `Setup-Weighbridge-<versi>.exe.sha256` — Checksum SHA-256 resmi untuk verifikasi keaslian berkas.
  - `latest-release.json` — Manifes metadata rilis untuk fitur periksa pembaruan otomatis di aplikasi.

> **Catatan:** Data transaksi, pengaturan, cadangan database (`.sql`), serta lisensi perangkat tidak dihapus saat melakukan pembaruan versi melalui installer maupun fitur pembaruan di dalam aplikasi.
