# Cara mencoba Student Edition V1 di akun Anda (aman untuk website utama)

**JANGAN upload paket ini ke repository `asjwd.github.io` yang sedang dipakai oleh portofolio utama Anda.** Untuk percobaan, gunakan dua repository **baru** yang tidak mengganggu proyek aktif.

### A. Buat dua repository uji

1. Buka https://github.com/new → repository **`portfolio-student-test`**, visibility **Public**, centang **Add a README** → Create.
2. Extract ZIP `V1_AS_Portfolio_Maker_Student.zip` di komputer. **Upload seluruh file dari dalam folder `V1_AS_Portfolio_Maker_Student` ke root** repository `portfolio-student-test` melalui **Add file → Upload files → Commit changes**. Jangan upload ZIP sebagai satu file dan jangan upload folder berisi file ke subfolder.
3. Buat satu repository lagi bernama **`portfolio-private-student-test`**, visibility **Private**, centang **Add a README** → Create.
4. Pada repository **Public**, buka **Settings → Pages → Source: Deploy from a branch → main → /(root) → Save**.

### B. Buat token dengan izin terbatas

1. Kunjungi https://github.com/settings/personal-access-tokens/new.
2. Name: `AS-Portfolio-Student-Test`. Expiration: disarankan 30–90 hari untuk percobaan.
3. Repository access: **Only select repositories**, dan pilih **tepat dua** repository `portfolio-student-test` dan `portfolio-private-student-test`.
4. Repository permissions: **Contents → Read and write**. Pengaturan lain biarkan seminimal mungkin.
5. Generate, lalu simpan token pada password manager. Jangan memasukkan token ke chat ini, README, commit, atau screenshot.

### C. Login & uji editor

1. Buka **https://asjwd.github.io/portfolio-student-test/manager.html** (situs project Pages berbeda dari `https://asjwd.github.io/`).
2. Isi:
   - Public repo: `portfolio-student-test`
   - Private repo: `portfolio-private-student-test`
   - Token: dari langkah B
   - Password enkripsi: minimal 16 karakter unik (catat di password manager)
3. Klik **Connect GitHub**. Pertama kali sistem membuat `vault.json` hanya di repo privat.
4. Pilih Profile → ganti `Your Name` dengan nama percobaan `Student Test`, lalu unggah foto uji. Klik **Save** (kiri).
5. Buka kedua repo di GitHub: `portfolio-private-student-test` seharusnya memuat `vault.json`, `draft.enc.json`, `cv.enc.json` dan foto terenkripsi; `portfolio-student-test/site.json` **seharusnya belum berubah**.
6. Tambah satu Experience, drag untuk mengurutkan, lalu klik **Publish** (kanan) **tanpa Save terlebih dahulu**.
7. Periksa `site.json` repo publik: nama/experience terbaru tampil, dan foto yang memang dipilih diterbitkan ke `assets/media`. Buka **https://asjwd.github.io/portfolio-student-test/** untuk melihat hasilnya.
8. Isi Private CV Data dengan **data palsu** (misalnya email `demo@example.com`), Publish lagi, kemudian periksa isi `site.json`: email palsu tadi **tidak boleh muncul**.

### D. Penggunaan dan batas keamanan

- Situs publik `index.html` dan alamat editor `manager.html` tetap bisa dibuka siapa saja. **Hanya token pemilik yang berizin yang boleh membaca/menulis draft dan memublikasikan.** Sesi login GitHub.com **bukan** pengganti token di GitHub Pages statis.
- File private adalah data terenkripsi, bukan JSON plaintext. Password tidak pernah dikirim ke GitHub. Namun jangan gunakan token di komputer yang tidak tepercaya.
- Jika lupa password enkripsi, **tidak ada cara reset** untuk data yang sudah dienkripsi. Simpan password dan backup private repo.
- Semua yang telah di-Publish ke GitHub bisa menjadi publik **termasuk sejarah commit**. Jangan pernah mengetes dengan informasi pribadi asli.
- Auto Translate beta bersifat opsional, bergantung pada layanan eksternal dari browser, dan bisa gagal. Gunakan English manual bila perlu.

### E. Setelah uji berhasil, bagikan kepada mahasiswa

Buat repository public master `AS-Portfolio-Maker`, upload paket yang sama, buka **Settings → General → Template repository**, kemudian bagikan tautan master. Mahasiswa klik **Use this template** dan membuat repo `portfolio` sendiri, repository privat `portfolio-private` sendiri, serta token dan password masing-masing. **Tidak ada akun atau Builder bersama**.

**Catatan fitur V1:** halaman portofolio mempertahankan gaya umum website lama, editor menyediakan Profile, Education, Certifications, Experience, Projects, Publications, Activities, Gallery, Contacts, bilingual manual, Auto Translate beta, pilihan warna, upload foto, dan CV ATS print/PDF. Fitur Mail Me berbasis Apps Script, Academic Portal, Grades, Courses, dan Tools pribadi **tidak disertakan**.
