# Laporan Analisis Version Control System dan Praktik Commit Message
**(Tugas 2 — Standarisasi Coding)**

## IDENTITAS
- **Nama:** Yusuf M. Daffa Asfiyan
- **NIM:** E41252204
- **Kelas:** Golongan F
- **Mata Kuliah:** Standarisasi Coding

---

## 1. PENDAHULUAN
Version Control System (VCS) merupakan infrastruktur krusial dalam pengembangan perangkat lunak modern yang berfungsi mengelola riwayat perubahan kode sumber, memfasilitasi kolaborasi antarpengembang, serta memastikan integritas basis kode. Penggunaan VCS yang tepat mencegah konflik kode, mempermudah pelacakan kutu (*bug*), dan meningkatkan efisiensi alur kerja proyek.

---

## 2. PERBANDINGAN CVCS DAN DVCS

### 2.1 Definisi & Arsitektur
- **Centralized Version Control System (CVCS):** Berbasis server tunggal terpusat. Repository utama tersimpan di server, dan klien hanya menyimpan salinan kerja (*working copy*) tanpa riwayat perubahan penuh.
- **Distributed Version Control System (DVCS):** Berstruktur terdistribusi (*peer-to-peer*). Setiap klien mengkloning repository secara utuh, mencakup seluruh riwayat commit dan log perubahan di mesin lokal masing-masing.

### 2.2 Kelebihan & Kekurangan
- **CVCS:**
  - *Kelebihan:* Kontrol akses mudah diatur di satu server terpusat.
  - *Kekurangan:* *Single point of failure* (jika server mati, pengembangan terhenti); membutuhkan koneksi internet untuk setiap commit.
- **DVCS:**
  - *Kelebihan:* Dapat bekerja offline, operasi lokal sangat cepat, riwayat aman karena ada salinan di setiap mesin.
  - *Kekurangan:* Membutuhkan ruang penyimpanan lokal lebih besar untuk menyimpan seluruh riwayat proyek.

### 2.3 Tabel Perbandingan

| Aspek | CVCS (Centralized) | DVCS (Distributed) |
| :--- | :--- | :--- |
| **Penyimpanan** | Satu server pusat | Setiap klien memiliki salinan lengkap (*full mirror*) |
| **Kerja Offline** | Tidak bisa (harus terhubung ke server) | Bisa (commit, log, branch dilakukan di lokal) |
| **Single Point of Failure** | Ya (server down = seluruh operasi terhenti) | Tidak (server down = proyek tetap berjalan lokal) |
| **Kecepatan Operasi** | Lambat (tergantung latensi jaringan) | Sangat Cepat (operasi berbasis berkas lokal) |
| **Alur Branching** | Berat dan lambat | Ringan, cepat, dan terisolasi |
| **Contoh Tools** | Subversion (SVN), CVS, Perforce | Git, Mercurial, Bazaar |

### 2.4 Kesimpulan Penggunaan
CVCS cocok untuk organisasi dengan kebijakan privasi ketat yang membutuhkan kendali terpusat dan akses bertingkat. DVCS ideal untuk tim modern, proyek sumber terbuka (*open source*), serta lingkungan kerja terdistribusi yang membutuhkan fleksibilitas tinggi.

---

## 3. MENGAPA GIT LEBIH POPULER DIBANDING SVN

Git mendominasi lanskap version control dibandingkan SVN karena keunggulan arsitektural dan ekosistemnya:

1. **Arsitektur Terdistribusi:** Pengembang dapat melakukan commit, branching, dan peninjauan riwayat tanpa koneksi jaringan.
2. **Branching & Merging Murah dan Cepat:** Git memperlakukan branch sebagai penunjuk (*pointer*) ringan ke commit tertentu, berbeda dari SVN yang membuat salinan folder fisik secara penuh.
3. **Performa Operasi Lokal:** Karena riwayat tersedia di mesin lokal, perintah seperti `git log` dan `git diff` berjalan hampir instan.
4. **Integritas Data Kriptografik:** Git menggunakan enkripsi hash SHA-1 (atau SHA-256) untuk menjamin isi file dan commit tidak dapat diubah tanpa terdeteksi.
5. **Ekosistem & Komunitas Luas:** Dukungan platform seperti GitHub, GitLab, dan Bitbucket memperkuat posisi Git sebagai standar industri.

---

## 4. CONTOH COMMIT MESSAGE YANG BAIK

Penulisan pesan commit mengikuti standar **Conventional Commits** dengan format:  
`<type>(<scope>): <description>`

### 4.1 Tabel Contoh Commit Message

| No | Commit Message | Alasan / Analisis |
| :-: | :--- | :--- |
| 1 | `feat(auth): add Google OAuth login` | Menggunakan tipe `feat` yang jelas, scope `auth` spesifik, serta deskripsi dalam *imperative mood* yang ringkas. |
| 2 | `fix(api): handle null response on /users` | Menggunakan tipe `fix` untuk mempublikasikan perbaikan bug pada endpoint API tertentu secara tepat. |
| 3 | `docs(readme): update installation steps` | Menggunakan tipe `docs` untuk perubahan dokumentasi tanpa memengaruhi kode sumber aplikasi. |
| 4 | `refactor(utils): simplify email validator` | Menggunakan tipe `refactor` untuk penyederhanaan struktur kode tanpa mengubah fungsionalitas luar. |
| 5 | `test(auth): add unit test for login service` | Menggunakan tipe `test` yang secara eksplisit menandai penambahan pengujian unit baru. |

### 4.2 Aturan Penulisan Commit Message
- Menggunakan *imperative mood* (misal: `add`, bukan `added` atau `adds`).
- Panjang subjek tidak melebihi 50 karakter.
- Huruf pertama subjek menggunakan huruf kecil (kecuali nama diri/konstanta).
- Tidak diakhiri dengan tanda titik.

---

## 5. KESIMPULAN
Penggunaan Git sebagai sistem kontrol versi terdistribusi memberikan fleksibilitas, performa, dan keamanan riwayat kode yang tinggi dibanding sistem terpusat seperti SVN. Penerapan standar *Conventional Commits* melengkapi praktik ini dengan menciptakan riwayat perubahan yang rapi, terstruktur, dan mudah ditelusuri oleh tim pengembang.

---

## REFERENSI
- Chacon, S., & Straub, B. (2014). *Pro Git*. Apress.
- Git Documentation. (2024). *Git Reference Manual*. Diakses dari https://git-scm.com/docs
- Conventional Commits Specification. (2023). *Conventional Commits v1.0.0*. Diakses dari https://www.conventionalcommits.org/
