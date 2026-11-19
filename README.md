# LLS Weigh — Official Multi-OS Releases

Repositori ini merupakan jalur distribusi publik resmi **installer mandiri (Windows, macOS, Linux)** beserta metadata pembaruan otomatis (*offline-first updater*) untuk **LLS Weigh — Load Ledger System** (Aplikasi Manajemen Jembatan Timbang Multi-Usaha).

- **Unduh Rilis Terbaru:** [Latest Release](https://github.com/luplupshi/llsweigh-releases/releases/latest)
- **Daftar Semua Versi:** [All Releases](https://github.com/luplupshi/llsweigh-releases/releases)

> **Repositori Khusus Biner (Tanpa Source Code):** Repositori ini sengaja hanya berisi `README.md` dan aset installer resmi pada halaman Releases agar fitur *Cek Pembaruan* di dalam aplikasi dapat berjalan aman tanpa mempublikasikan kode sumber.

---

## Paket Installer Tersedia (`LLSWeigh-<versi>-<os>-<arch>.<ekstensi>`)

Seluruh paket sudah menyertakan **Java Runtime** bawaan sehingga tidak memerlukan instalasi Java terpisah di komputer operasional pos timbang.

| Sistem Operasi & Arsitektur | Nama Berkas | Keterangan |
| :--- | :--- | :--- |
| **Windows x64** *(+ emulasi Win11 ARM64)* | `LLSWeigh-<versi>-windows-x64.exe` | Installer Windows mandiri (Inno Setup + JRE 25) |
| **macOS Apple Silicon (M1–M4)** | `LLSWeigh-<versi>-macos-arm64.dmg` | Disk image aplikasi native `LLSWeigh.app` (ARM64) |
| **macOS Intel (x64)** | `LLSWeigh-<versi>-macos-x64.dmg` | Disk image aplikasi `LLSWeigh.app` (x64) |
| **Linux x64 (Debian / Ubuntu / Mint)** | `LLSWeigh-<versi>-linux-x64.deb` | Paket installer APT dengan shortcut menu |
| **Linux x64 (Portable)** | `LLSWeigh-<versi>-linux-x64.tar.gz` | Arsip portabel untuk seluruh distro Linux x64 |
| **Linux ARM64 (Ubuntu ARM / Raspberry Pi OS)** | `LLSWeigh-<versi>-linux-arm64.deb` | Paket installer APT ARM64 dengan shortcut menu |
| **Linux ARM64 (Portable)** | `LLSWeigh-<versi>-linux-arm64.tar.gz` | Arsip portabel untuk distro Linux ARM64 |

### Berkas Integritas & Metadata Pembaruan
- `<nama-berkas-installer>.sha256` — Checksum SHA-256 resmi untuk verifikasi keaslian unduhan tiap platform.
- `latest-release.json` — Manifes rilis Multi-OS yang dipakai fitur pembaruan otomatis di aplikasi (**Pengaturan -> Lisensi & Update**).

---

## Panduan Instalasi per Sistem Operasi

### 1. Windows (`LLSWeigh-<versi>-windows-x64.exe`)
1. Unduh dan jalankan `LLSWeigh-<versi>-windows-x64.exe`.
2. Bila muncul peringatan *Windows SmartScreen* pada pembukaan awal, klik **More info** -> **Run anyway**.
3. Ikuti wizard instalasi (*Install for me only* atau *Install for all users*).
4. Jika menggunakan konverter **USB-to-RS232** untuk indikator timbangan digital, driver dapat dipasang dari paket driver yang disertakan di folder instalasi bila port COM belum terbaca di Windows.

### 2. macOS (`LLSWeigh-<versi>-macos-arm64.dmg` / `macos-x64.dmg`)
1. Buka berkas `.dmg` yang sesuai dengan arsitektur Mac Anda, lalu seret `LLSWeigh.app` ke folder **Applications**.
2. Pada pembukaan pertama, bila macOS Gatekeeper menahan aplikasi, klik kanan `LLSWeigh.app` di `/Applications` -> pilih **Open**, atau jalankan di Terminal:
   ```bash
   xattr -cr /Applications/LLSWeigh.app
   ```

### 3. Linux (`.deb` / `.tar.gz`)
- **Debian / Ubuntu / Mint / Raspberry Pi OS (`.deb`):**
  ```bash
  sudo apt install ./LLSWeigh-<versi>-linux-x64.deb
  # atau untuk ARM64:
  sudo apt install ./LLSWeigh-<versi>-linux-arm64.deb
  ```
- **Portable (`.tar.gz`):**
  ```bash
  tar -xzf LLSWeigh-<versi>-linux-x64.tar.gz
  ./LLSWeigh/bin/LLSWeigh
  ```

---

## Verifikasi Checksum SHA-256 (Disarankan)

- **Windows (Command Prompt / PowerShell):**
  ```powershell
  Get-FileHash .\LLSWeigh-<versi>-windows-x64.exe -Algorithm SHA256
  ```
- **macOS:**
  ```bash
  shasum -a 256 -c LLSWeigh-<versi>-macos-arm64.dmg.sha256
  ```
- **Linux:**
  ```bash
  sha256sum -c LLSWeigh-<versi>-linux-x64.deb.sha256
  ```

---

## Pemakaian Pertama Kali & Keamanan Data Saat Pembaruan

- **Instalasi Baru:** Saat aplikasi dijalankan pertama kali dengan basis data kosong pengguna, layar login otomatis menampilkan formulir **Pendaftaran Administrator Awal Offline** (tidak ada akun bawaan yang ditanam tetap).
- **Pembaruan Versi (Upgrade Aman):** Data transaksi timbang, pengaturan profil usaha, master data, cadangan basis data (`.sql`), serta aktivasi lisensi perangkat **tidak akan terhapus** saat melakukan pembaruan versi—baik melalui installer terbaru maupun melalui tombol **Cek Pembaruan** (oleh Administrator, otomatis mencadangkan `.sql` terlebih dahulu dan memverifikasi SHA-256 sebelum memasang pembaruan).
