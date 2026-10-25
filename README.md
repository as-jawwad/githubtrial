# AS.Portfolio Maker — Student Edition V1

**by as.jawwad** · GitHub Pages · self-hosted · no shared builder

Template portofolio untuk mahasiswa. Semua file, draft, foto, dan akun GitHub dimiliki masing-masing pengguna. Tidak ada Academic Portal, nilai, Courses & Materials, atau Digital Tools dari website pembuat.

## Tiga langkah setup (untuk mahasiswa)

1. Klik **Use this template → Create a new repository**, pilih **Public**, beri nama `portfolio`. Atau untuk menguji file ZIP tanpa template master, buat repository `portfolio` lalu upload seluruh isi folder ini ke root repository.
2. Buat repository baru bernama `portfolio-private`, pilih **Private**, dan **centang Add README** supaya branch `main` tersedia. Jangan upload file website ke repository privat.
3. Buat **fine-grained personal access token**: **Only select repositories** → pilih `portfolio` dan `portfolio-private`, izin **Contents: Read and write**. Token jangan diupload atau dikirim ke pembuat template.

Kemudian lakukan satu pengaturan GitHub Pages:

- Repository `portfolio` → **Settings → Pages → Build and deployment → Deploy from a branch → main → /(root) → Save**.
- Buka `https://USERNAME.github.io/portfolio/manager.html`, isi kedua nama repository, token, dan **password enkripsi yang unik minimal 16 karakter**. Klik **Connect GitHub**.
- Edit portofolio. **Save** (kiri) menyimpan draft terenkripsi pada repository privat. **Publish** (kanan) otomatis Save, mengunggah media publik, dan memperbarui website.
- Website publik: `https://USERNAME.github.io/portfolio/`.

Jika repository publik diberi nama `USERNAME.github.io`, website berada di root `https://USERNAME.github.io/` dan isikan nama repo `USERNAME.github.io` pada Manager.

## Yang perlu diketahui sebelum mengisi data

- `index.html` dan `manager.html` **dapat dibuka semua orang** karena GitHub Pages bersifat publik. Namun akses **baca/tulis draft dan Publish** baru diperoleh dari token GitHub yang memiliki izin. Login di GitHub.com saja **tidak** mengunci halaman statis.
- `site.json` dan gambar yang sudah dipublikasikan **dapat dilihat siapa saja**. Jangan masukkan NIM/nomor HP/alamat pribadi dalam kolom publik jika tidak ingin tersebar.
- Data pada halaman **Private CV Data** disimpan di `portfolio-private/cv.enc.json`, terenkripsi AES-256-GCM. Draft di `draft.enc.json`, media yang disimpan sebelum Publish juga dienkripsi pada `media/*.enc.json`.
- Password enkripsi digunakan untuk membuat kunci lewat PBKDF2-SHA256, 350.000 putaran. Password dan token **tidak disimpan di localStorage/cookie**, sehingga harus diisi lagi ketika membuka sesi baru. **Tidak ada reset password** jika lupa. Simpan password dan backup repository privat secara terpisah.
- Perubahan baru sementara berada di tab browser hingga Save/Publish. Refresh saat ada **Unsaved changes** akan membuang perubahan tersebut (browser menampilkan peringatan).
- Auto Translate **beta** mencoba layanan Google Translate di browser untuk *teks portofolio publik saja* atas persetujuan Anda. Fitur ini mungkin tidak tersedia ketika endpoint menolak permintaan. Isi English manual tetap dapat digunakan, dan data privat tidak pernah dikirim ke penerjemah.
- CV ATS dapat diekspor dengan **Generate CV ATS → Print → Save as PDF**, memilih apakah menyertakan data privat.
- Token hanya diminta untuk repository masing-masing pengguna. Jangan gunakan PAT dengan akses semua repository.

## Struktur file

| File | Fungsi |
|---|---|
| `index.html` | Website portofolio publik |
| `site.json` | Data yang dipublikasikan |
| `portfolio.js`, `common.js` | Render halaman publik |
| `styles.css`, `v*.css`, `student.css` | Tampilan website publik |
| `manager.html` | Editor di akun sendiri |
| `V1_manager.js`, `V1_manager.css` | Fungsi editor dan GitHub API |
| `favicon.svg` | Ikon netral |

**Jangan upload** `vault.json`, `draft.enc.json`, `cv.enc.json`, atau file `media/*.enc.json` ke repository publik. Semuanya dibuat sendiri pada repository privat setelah Connect/Save.

## Petunjuk pembuat template

Untuk membagikan kepada mahasiswa, buat repository public baru misalnya `AS-Portfolio-Maker`, upload semua file paket ini, lalu buka **Settings → General → Template repository**. Setelah aktif, mahasiswa dapat menekan **Use this template** dan repository pribadi mereka akan dibuat dengan file dasar yang sama. Mereka tetap perlu membuat repository privat, token terbatas, dan mengaktifkan Pages.

**Pengujian V1:** editor serta Publish telah diuji dengan simulasi GitHub API dan uji enkripsi AES-256-GCM nyata. Belum diuji langsung pada akun GitHub mahasiswa sungguhan. Mulai dari akun uji dan data contoh dahulu.

---

AS.Portfolio Maker · by as.jawwad · 2026
