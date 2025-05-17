## GAIL - Goals, Actions, Information Language

**Ringkasan Singkat:**  
Transkrip ini menjelaskan pentingnya menyusun instruksi (prompt) yang jelas untuk AI agen menggunakan kerangka **GAIL** (Goals/Instructions, Actions, Information, Language), mirip dengan cara kita memberi tugas ke intern baru agar tidak gagal.

---

**Poin-Poin Penting:**  

1. **Goals/Instructions (Tujuan & Aturan):**  
   - Seperti memberi tugas ke intern: Jelaskan *apa yang harus dilakukan* dan *bagaimana melakukannya*.  
   - Contoh: "Cek dulu apakah pengeluaran sudah ada di sistem sebelum menambahkan yang baru."  

2. **Actions (Aksi yang Diizinkan):**  
   - Daftar alat/tool yang bisa digunakan agen, seperti mengirim email, mengakses database, atau memanggil API.  
   - Batasi aksi sesuai kebutuhan organisasi (misal: hanya boleh mengedit data, tidak boleh menghapus).  

3. **Information (Data yang Dibutuhkan):**  
   - Informasi awal (misal: dokumen pengeluaran) dan hasil dari aksi sebelumnya (misal: respons API) yang digunakan untuk mengambil keputusan selanjutnya.  
   - Bersifat sementara dan berubah-ubah tergantung tugas.  

4. **Language (Cara Berkomunikasi):**  
   - Format output yang diinginkan, seperti laporan TPS atau respons dalam bahasa tertentu.  
   - Contoh: "Selalu akhiri dengan konfirmasi: 'Apakah Anda ingin melanjutkan?'".  

5. **Struktur Prompt (System vs User Messages):**  
   - **System Messages:** Aturan tetap (Goals, Actions, Language) yang disimpan sebagai pedoman.  
   - **User Messages:** Input sementara (Information) untuk tugas spesifik.  

6. **Analogi Intern Baru:**  
   - Jika instruksi seperti "Masukkan pengeluaran" tanpa detail, intern akan buat duplikasi. Begitu juga dengan AI: butuh prosedur jelas seperti "Cek sistem → Konfirmasi duplikasi → Simpan data".  

7. **Contoh Prompt GAIL:**  
   - **Goal:** "Bantu pengguna mengelola pengeluaran dengan memeriksa duplikasi."  
   - **Action:** Tools: `cek_pengeluaran()`, `simpan_pengeluaran()`.  
   - **Language:** Format: "Langkah 1: [hasil cek] → Langkah 2: [konfirmasi]".  

---

**Tips Praktis:**  
Bayangkan Anda memberi instruksi ke intern:  
- Jangan cuma bilang "Kerjakan ini!" → Jelaskan *tujuan*, *langkah-langkah*, *alat yang tersedia*, dan *format hasil*.  
- Uji prompt Anda: Apakah AI bisa gagal jika instruksinya ambigu? Perbaiki bagian yang tidak spesifik!


## Givin Agents Tools

**Ringkasan Singkat:**  
Agentic systems (AI agen) berinteraksi dengan dunia melalui **tools (alat)** atau **actions (aksi)** yang didefinisikan sebelumnya, mirip dengan cara manusia menggunakan alat terbatas untuk menyelesaikan tugas. Tanpa batasan ini, agen bisa memberikan solusi yang tidak realistis atau tidak sesuai dengan sistem yang tersedia.

---

**Poin-Poin Penting:**  

1. **Tools/Actions sebagai Batasan:**  
   - Agen hanya boleh menggunakan alat atau aksi yang diizinkan, seperti "penggorengan" atau "api kayu" dalam contoh memasak.  
   - Contoh: Jika agen diminta merencanakan perjalanan, batasi transportasi yang boleh digunakan (misal: mobil, kereta, bukan pesawat).  

2. **Mengapa Batasan Penting?**  
   - Dunia nyata penuh keterbatasan (misal: tidak ada akses ke superkomputer).  
   - Tanpa batasan, agen mungkin "berimajinasi" solusi yang tidak mungkin, seperti mengirim email tanpa izin mengakses akun.  

3. **Tools vs. Actions:**  
   - **Tools (Alat):** Fleksibel, cocok untuk manusia. Contoh: "Gunakan penggorengan untuk memasak." Manusia bisa memilih cara tepat.  
   - **Actions (Aksi):** Spesifik, cocok untuk sistem komputer. Contoh: "Eksekusi perintah: `simpan_data()`."  

4. **Contoh Memasak Pizza:**  
   - Agen hanya punya *skillet*, *sautee pan*, dan *wood fire*.  
   - Langkah demi langkah: Siapkan adonan → Nyalakan api → Panaskan penggorengan → Masak pizza.  
   - Agen tidak bisa meminta "oven" karena tidak termasuk tools yang diberikan.  

5. **Aplikasi di Sistem Nyata:**  
   - Saat menghubungkan agen ke CRM (manajemen hubungan pelanggan), definisikan aksi spesifik:  
     - `cari_pelanggan(nama)`  
     - `tambah_catatan(id_pelanggan, teks)`  
   - Agen tidak bisa "berkreasi" di luar aksi ini, seperti menghapus data tanpa izin.  

6. **Analogi Intern Baru:**  
   - Jika Anda bilang, "Buat laporan!" tanpa instruksi, intern mungkin menggunakan format salah.  
   - Dengan batasan: "Gunakan template X dan data dari folder Y," hasil lebih terarah.  

7. **Perbedaan Interaksi dengan Manusia vs. Mesin:**  
   - **Manusia:** Bisa fleksibel. Contoh: "Gunakan alat ini untuk membersihkan ruangan."  
   - **Mesin:** Harus spesifik. Contoh: "Jalankan perintah: `hapus_file(log.txt)`."  

---

**Tips Praktis:**  
1. **Bayangkan Sebagai Pelatih Intern:**  
   - Jelaskan *alat yang tersedia* dan *aturan main* sebelum memberi tugas.  
   - Contoh: "Kamu hanya boleh menghubungi pelanggan via email, tidak boleh menelepon."  

2. **Uji Prompt Anda:**  
   - Apakah agen bisa menyarankan sesuatu yang tidak mungkin?  
   - Contoh: Jika prompt tidak menyebutkan "cek duplikasi data," agen mungkin menambahkan data ganda.  

3. **Gunakan Contoh Konkret:**  
   - Seperti contoh memasak di atas, buat skenario sederhana untuk menguji apakah agen mengikuti batasan.  

4. **Sesuaikan dengan Sistem Target:**  
   - Untuk manusia: Gunakan bahasa alami dan tools fleksibel.  
   - Untuk mesin: Definisikan aksi spesifik (misal: API calls).  

---

**Contoh Prompt dengan Batasan:**  
```text  
**Tujuan:** Bantu pengguna mengelola pengeluaran.  
**Tools yang Diizinkan:**  
- `cek_pengeluaran(nama, tanggal)`  
- `simpan_pengeluaran(jumlah, kategori)`  
**Aturan:**  
- Selalu cek duplikasi sebelum menyimpan.  
- Jika duplikasi ditemukan, tanyakan konfirmasi.  
**Format Output:**  
- Langkah 1: [Hasil cek duplikasi]  
- Langkah 2: [Konfirmasi pengguna]  
```  

Dengan struktur ini, agen tidak akan menambahkan data ganda atau menggunakan alat di luar yang diberikan.


## Tool Descriptions and Naming

**Ringkasan Singkat:**  
Agentic AI membutuhkan **deskripsi alat (tool)** yang jelas dan **penamaan alat yang intuitif** untuk berfungsi efektif, terutama saat menghadapi sistem atau alat yang tidak dikenal (seperti alat di kapal alien atau software kustom). Tanpa konteks ini, AI bisa salah menginterpretasi tujuan alat atau menggunakan alat secara tidak tepat.

---

**Poin-Poin Penting:**  

1. **Penamaan Alat (Tool Naming):**  
   - **Nama deskriptif** (misal: `makeAlienPizza`, `openDimensionalPortal`) membantu AI memahami fungsi alat secara langsung.  
   - **Nama acak/abstrak** (misal: `X155`, `Q63`) memerlukan deskripsi tambahan agar AI tidak bingung.  
   - Contoh: Nama `mkpz` (singkatan dari "make pizza") mungkin jelas bagi manusia, tapi AI tidak punya "pengetahuan institusional" untuk menebak artinya.  

2. **Deskripsi Fungsi Alat:**  
   - **Wajib disertakan** jika nama alat tidak jelas. Contoh:  
     - `X155`: "Membuat pizza alien yang menarik perhatian makhluk luar angkasa."  
     - `Q63`: "Membuka portal multidimensi ke lokasi tujuan."  
   - Tanpa deskripsi, AI mungkin salah menggunakan alat. Misal: `mkpz` digunakan untuk membuat peta kapal alien, bukan memasak.  

3. **Konteks Penggunaan Alat:**  
   - Jelaskan **apakah semua alat harus dipakai**, atau hanya beberapa.  
   - Contoh: Dalam skenario pelarian, AI mungkin mengira alat seperti `pliers` (tang) harus digunakan untuk melepas baut, padahal tidak ada baut di deskripsi.  

4. **Perbedaan Antara Manusia dan AI:**  
   - **Manusia** bisa mengisi "celah konteks" dengan pengalaman. Misal: Melihat `pliers`, manusia tahu itu untuk memotong/mengencangkan.  
   - **AI** butuh instruksi eksplisit: "Gunakan tang untuk melepas kabel merah."  

5. **Contoh Nyata di Sistem Komputer:**  
   - Alat seperti `simpan_data()` atau `cek_duplikasi(id)` harus punya deskripsi:  
     - "Fungsi ini menyimpan data ke database dan memeriksa duplikasi berdasarkan ID."  
   - Jika tidak, AI mungkin mengira `simpan_data()` juga menghapus entri lama.  

6. **Struktur Prompt Efektif:**  
   - **Format yang baik:**  
     ```text  
     Tools:  
     - makeAlienPizza: Membuat pizza alien sebagai pengalihan.  
     - openDimensionalPortal: Membuka portal ke lokasi aman.  
     - playBeatlesMusic: Memutar musik untuk mengalihkan perhatian.  
     Tugas: Gunakan alat-alat ini untuk melarikan diri dari kapal alien.  
     ```  
   - **Tanpa struktur ini**, AI bisa kebingungan memilih alat atau langkah.  

7. **Kesalahan Umum:**  
   - **Nama alat ambigu + tanpa deskripsi**: AI akan membuat asumsi acak.  
   - **Terlalu banyak alat opsional**: AI mungkin memilih alat yang tidak relevan.  

---

**Tips Praktis:**  
1. **Beri Nama yang Jelas:**  
   - Gunakan frasa aktif seperti `generateReport()`, `sendEmail()`, bukan `tool_001`.  

2. **Sertakan Deskripsi Fungsi:**  
   - Contoh:  
     ```text  
     Tool: checkInventory(itemId)  
     Fungsi: Memeriksa ketersediaan stok barang berdasarkan ID.  
     Output: Jumlah stok tersedia atau pesan "Stok habis".  
     ```  

3. **Tentukan Aturan Penggunaan:**  
   - "Gunakan alat ini hanya jika kondisi X terpenuhi."  
   - "Jangan gabungkan alat A dan B tanpa konfirmasi."  

4. **Uji dengan Contoh:**  
   - Simulasi skenario seperti "pelarian dari kapal alien" untuk memastikan AI memahami alat dan batasannya.  

5. **Hindari Overloading Alat:**  
   - Jangan masukkan alat yang tidak relevan. Misal: Alat `playBeatlesMusic` tidak perlu dalam sistem CRM.  

---

**Analogi Kapal Alien:**  
Bayangkan Anda memberi instruksi ke intern baru yang belum pernah melihat alat di laboratorium:  
- **Tanpa deskripsi:** "Gunakan X155 untuk membuat pizza." → Intern bingung.  
- **Dengan deskripsi:** "X155 adalah oven alien yang otomatis membuat pizza saat dinyalakan." → Intern bisa bertindak.  

**Pelajaran Utama:**  
AI tidak punya "pengetahuan latar belakang" seperti manusia. Setiap alat harus dijelaskan **apa, bagaimana, dan kapan digunakan** agar tidak gagal.


## Tool Results and Agent Feedback

**Ringkasan Singkat:**  
Agentic AI membutuhkan **umpan balik setelah setiap aksi** untuk menyesuaikan langkah berikutnya, mirip dengan cara manusia belajar dari hasil tindakan. Tanpa umpan balik ini, AI tidak bisa memahami keberhasilan atau kegagalan langkahnya. Contoh penggunaan microwave menunjukkan pentingnya **deskripsi error yang jelas** dan **struktur prompt yang terorganisir** (GAIL) untuk memastikan AI berfungsi seperti sistem komputer nyata.

---

**Poin-Poin Penting:**  

1. **Umpan Balik Setelah Aksi (Feedback Loop):**  
   - AI tidak bisa mengamati hasil aksi secara langsung. Setiap kali AI memberi perintah (misal: "Naikkan waktu microwave"), sistem harus memberi tahu hasilnya (misal: "Waktu bertambah 5 detik").  
   - **Contoh:** Jika AI memerintahkan "Start microwave" tapi pintu terbuka, sistem harus merespons dengan "Error: Pintu terbuka" agar AI memperbaiki langkah (misal: "Tutup pintu").  

2. **Kualitas Pesan Error yang Kritis:**  
   - Error seperti "Error 32" tidak berguna bagi AI. Harus dijelaskan dalam bahasa yang bisa dipahami, seperti "Pintu microwave tidak tertutup."  
   - **Analogi:** Seperti memberi instruksi ke intern baru: "Jangan hanya bilang 'Gagal,' tapi jelaskan kenapa (misal: 'Data tidak ditemukan').  

3. **Struktur Prompt Berbasis GAIL:**  
   - **Goals/Instructions:** Tujuan (misal: "Panaskan quesadilla") dan prosedur (misal: "Set waktu sebelum start").  
   - **Actions:** Daftar aksi spesifik (misal: `increase_time`, `close_door`).  
   - **Information:** Hasil aksi sebelumnya (misal: "Waktu bertambah 60 detik").  
   - **Language:** Format output (misal: "Langkah 1: [aksi] → Hasil: [respons]").  

4. **Penamaan Aksi yang Jelas:**  
   - Nama aksi seperti `microwave_increase_time` lebih baik daripada `tool_001` karena menjelaskan tujuan.  
   - Jika nama ambigu, tambahkan deskripsi:  
     ```text  
     Aksi: increase_time  
     Fungsi: Menambah waktu pemanasan sebesar 5 detik per klik.  
     ```  

5. **Transisi dari Umpan Balik Manusia ke Sistem Otomatis:**  
   - Awalnya, manusia memberi respons (misal: "Pintu ditutup"). Nantinya, sistem komputer akan menggantikan peran ini dengan pesan otomatis (misal: "Status pintu: tertutup").  
   - **Contoh Nyata:** CRM sistem yang merespons "Pelanggan tidak ditemukan" alih-alih manusia mengetik pesan tersebut.  

6. **Contoh Praktis (Memasak dengan Microwave):**  
   - **Langkah 1:** AI: "Masukkan quesadilla." → Respons: "Makanan dimasukkan."  
   - **Langkah 2:** AI: "Naikkan waktu." → Respons: "Waktu bertambah 5 detik."  
   - **Langkah 3:** AI: "Start microwave." → Respons: "Error: Pintu terbuka." → AI memperbaiki: "Tutup pintu."  

7. **Kesalahan Umum & Solusi:**  
   - **Masalah:** AI mengulang aksi yang gagal tanpa memahami error.  
   - **Solusi:** Pastikan respons error menjelaskan penyebab dan solusi (misal: "Tutup pintu sebelum start").  

---

**Tips Praktis:**  
1. **Simulasikan Skenario Nyata:**  
   - Uji AI dengan tugas sederhana (misal: mengatur waktu microwave) untuk memastikan umpan balik sistem bekerja.  

2. **Gunakan Template Umpan Balik:**  
   ```text  
   Aksi: [nama aksi]  
   Hasil: [deskripsi hasil, termasuk error jika ada]  
   Status: [sukses/gagal]  
   ```  

3. **Dokumentasi Aksi:**  
   - Buat daftar aksi lengkap dengan deskripsi, contoh penggunaan, dan kemungkinan error.  

4. **Uji dengan Error yang Berbeda:**  
   - Coba beri respons error acak (misal: "Sensor rusak") untuk melihat apakah AI bisa menyesuaikan langkah.  

5. **Otomatisasi Umpan Balik:**  
   - Integrasikan AI dengan sistem nyata yang mengirimkan respons otomatis (misal: API CRM yang mereturn data pelanggan).  

---

**Pelajaran Utama:**  
Agentic AI seperti intern baru yang butuh panduan detail dan umpan balik konstan. Dengan struktur GAIL, penamaan aksi yang jelas, dan pesan error yang informatif, AI bisa menghadapi sistem kompleks seperti manusia ahli. Tanpa ini, AI akan gagal seperti intern yang diberi instruksi "Kerjakan ini!" tanpa detail.