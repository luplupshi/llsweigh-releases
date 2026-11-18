# LLS Weigh — Official Releases

Repositori ini khusus digunakan sebagai jalur distribusi resmi **installer aplikasi Windows** dan metadata pembaruan otomatis (*offline-first updater*) untuk **LLS Weigh (Load Ledger System)**.

- Halaman unduhan installer: [Releases](https://github.com/luplupshi/llsweigh-releases/releases)
- Berkas distribusi per rilis:
  - `Setup-LLSWeigh-<versi>.exe` — Installer mandiri Windows (sudah menyertakan Java Runtime).
  - `Setup-LLSWeigh-<versi>.exe.sha256` — Checksum SHA-256 resmi untuk verifikasi keaslian berkas.
  - `latest-release.json` — Manifes metadata rilis untuk fitur periksa pembaruan otomatis di aplikasi.

> **Catatan:** Data transaksi, pengaturan, cadangan database (`.sql`), serta aktivasi perangkat tidak dihapus saat melakukan pembaruan versi melalui installer maupun fitur pembaruan di dalam aplikasi.