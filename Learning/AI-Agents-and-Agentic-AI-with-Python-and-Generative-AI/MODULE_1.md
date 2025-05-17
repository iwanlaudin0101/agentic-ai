## Introduction

**Ringkasan Singkat:**  
Agentic AI adalah sistem AI yang bisa bertindak secara otonom, membuat keputusan, dan beradaptasi berdasarkan umpan balik lingkungan atau manusia. Contohnya terlihat dalam simulasi memasak di mana AI memberi instruksi langkah-langkah memasak, lalu menyesuaikan rencana ketika ada masalah (seperti daging yang hampir gosong atau sayuran yang tidak tersedia).

---

**Poin-Poin Penting:**  

1. **Autonomi & Agency**  
   - AI bisa "bertindak" dengan membuat keputusan sendiri (misal: memilih langkah memasak selanjutnya) tanpa perlu manusia mengarahkan setiap detail.  
   - Contoh: AI memerintahkan "tumis daging" tanpa ditanya lagi "apa yang harus dilakukan setelah ini?".

2. **Adaptabilitas**  
   - AI bisa menyesuaikan rencana jika ada hambatan atau perubahan kondisi.  
   - Contoh: Saat daging hampir gosong, AI mengubah instruksi menjadi "turunkan suhu api" atau saat tidak ada sayur, AI beralih ke buah durian sebagai alternatif.

3. **Interaksi dengan Lingkungan**  
   - AI tidak hanya menghasilkan teks, tetapi juga "merasakan" hasil tindakannya melalui umpan balik (feedback loop).  
   - Contoh: Setelah manusia melaporkan "daging sudah matang", AI melanjutkan ke langkah berikutnya.

4. **Kolaborasi Manusia-AI (Human-in-the-Loop)**  
   - AI merancang langkah-langkah, tapi manusia yang mengeksekusi tindakan fisik (seperti mengaduk atau memotong).  
   - Contoh: AI menyusun resep, manusia yang benar-benar memasak sesuai instruksi.

5. **Tantangan Integrasi dengan Sistem Lama**  
   - AI generatif cenderung fleksibel dan "berbicara alami", sedangkan sistem komputer tradisional (seperti spreadsheet) membutuhkan input struktural kaku.  
   - Contoh: AI mungkin bilang "buat resep enak", tapi spreadsheet butuh angka dan format spesifik untuk bekerja.

---

**Penjelasan Tambahan:**  
Bayangkan Agentic AI seperti asisten virtual yang bukan hanya menjawab pertanyaan, tapi juga bisa "menggerakkan" dunia nyata. Jika AI sebelumnya seperti pemandu suara di GPS (hanya memberi arah), Agentic AI lebih mirip sopir otonom yang bisa memutuskan rute baru saat ada kemacetan—meski dalam contoh ini, manusia masih yang mengemudikan mobilnya.

## Flipped Interaction Pattern

**Ringkasan Singkat:**  
Agentic AI bekerja dengan pola interaksi terbalik (flipped interaction): bukan manusia yang mengarahkan AI, tapi AI yang mengambil inisiatif untuk bertanya, memerintah, atau mengumpulkan informasi demi mencapai tujuan. Contohnya terlihat saat AI merekomendasikan restoran di Nashville dengan bertanya satu per satu tentang preferensi pengguna, lalu menyesuaikan jawaban berdasarkan respons yang diberikan.

---

**Poin-Poin Penting:**  

1. **Pola Flipped Interaction**  
   - AI tidak hanya menjawab pertanyaan, tapi **mengambil alih peran aktif** untuk bertanya atau memberi instruksi.  
   - Contoh: AI bertanya, *"Apa jenis masakan yang kamu inginkan?"* alih-alih menunggu manusia berkata, *"Cari restoran Meksiko."*  

2. **Langkah Demi Langkah (Step-by-Step)**  
   - AI bekerja per langkah, menghindari instruksi kompleks sekaligus.  
   - Contoh: Dalam rekomendasi restoran, AI bertanya satu per satu (jenis masakan → preferensi lokasi → durasi perjalanan) alih-alih meminta semua data sekaligus.  

3. **Adaptasi Berbasis Umpan Balik**  
   - AI menyesuaikan langkah berikutnya berdasarkan respons manusia atau hasil tindakan.  
   - Contoh: Saat pengguna bilang, *"Restoran yang kamu rekomendasikan jauh,"* AI langsung beralih ke opsi lain di lokasi lebih dekat.  

4. **Komunikasi Fleksibel dengan Manusia & Sistem**  
   - AI bisa berbicara dalam bahasa manusia (contoh: *"Kamu ingin suasana santai atau mewah?"*) dan menerjemahkan ke bahasa sistem komputer (misalnya, query database restoran).  
   - Analogi: Seperti droid protokol di *Star Wars* yang bisa berbicara dengan robot, manusia, dan alien—AI menjadi penghubung antara manusia dan sistem teknologi.  

5. **Tantangan: Menghubungkan Dunia Fleksibel & Kaku**  
   - AI generatif suka bicara panjang, tapi sistem komputer tradisional butuh input struktural (angka, format spesifik).  
   - Contoh: Jika AI bilang *"Cari restoran dengan suasana ramah anak,"* sistem database mungkin butuh query seperti `SELECT * FROM restaurants WHERE kid_friendly = TRUE`.  

6. **Kemampuan Terjemahan (Translation Power)**  
   - AI unggul dalam menerjemahkan bahasa manusia ke bahasa sistem teknis, seperti mengubah *"Saya mau makan di tempat yang tidak terlalu jauh"* menjadi parameter jarak dalam aplikasi.  

---

**Penjelasan Tambahan:**  
Bayangkan Agentic AI seperti kepala tim proyek yang tidak hanya menerima instruksi, tapi juga merancang langkah-langkah kerja, membagi tugas, dan menyesuaikan rencana saat ada hambatan. Jika tim manusia bisa menghadapi perubahan mendadak (misal: anggota sakit), AI juga harus bisa mengganti strategi—seperti beralih ke durian saat sayur tidak tersedia atau mencari restoran alternatif saat jarak terlalu jauh.  

**Contoh Analogi:**  
Jika AI adalah pemandu wisata, pola flipped interaction mirip dengan pemandu yang bertanya, *"Kamu suka museum atau gunung?"*, lalu merancang itinerary lengkap berdasarkan jawabanmu. Jika kamu bilang, *"Cuaca buruk, ganti ke tempat indoor,"*, ia langsung menyesuaikan rencana tanpa perlu kamu memerintah detailnya.


## The Agent Loop

**Ringkasan Singkat:**  
Untuk mengubah percakapan manual dengan AI menjadi agen otonom, kita membangun **agent loop** — siklus otomatis yang memungkinkan AI memutuskan langkah-langkah tindakan, mengeksekusi mereka pada sistem komputer, dan menyesuaikan rencana berdasarkan umpan balik. Proses ini terdiri dari enam tahap: membuat prompt, mengirim ke model AI, mem-parsing respons, mengeksekusi aksi, mendapatkan hasil, dan mengulang hingga tujuan tercapai.

---

**Poin-Poin Penting:**  

1. **Agent Loop: Struktur Dasar**  
   - **Tahapan Siklus:**  
     1. **Buat Prompt:** Beri AI tujuan (misal: *"Tambahkan pengeluaran perjalanan"*).  
     2. **Kirim ke Model Bahasa Besar (LLM):** AI menghasilkan respons dengan rencana aksi.  
     3. **Parsing Respons:** Ubah respons AI ke format yang bisa diproses komputer (misal: JSON atau kode API).  
     4. **Eksekusi Aksi:** Jalankan perintah di sistem target (misal: tambahkan baris ke spreadsheet).  
     5. **Dapatkan Umpan Balik:** Simpan hasil eksekusi (sukses/gagal, error message, dll.).  
     6. **Ulangi:** Gabungkan umpan balik ke prompt baru dan lanjutkan siklus hingga tugas selesai.  

2. **Contoh Praktis: Menambah Pengeluaran Perjalanan**  
   - **Prompt Awal:** *"Bantu saya tambahkan pengeluaran perjalanan berikut: Jakarta ke Bali, Rp5.000.000, 15-20 November 2023."*  
   - **Respons AI:**  
     ```json  
     {  
       "action": "check_expense_exists",  
       "params": {"destination": "Bali", "date": "2023-11-15"}  
     }  
     ```  
   - **Parsing & Eksekusi:** Sistem memeriksa spreadsheet untuk mencari entri serupa.  
   - **Umpan Balik:** *"Pengeluaran untuk Bali belum ada."*  
   - **Loop Lanjutan:** AI memerintahkan menambahkan baris baru dengan data yang diminta.  

3. **Peran Kunci dari Prompt Engineering**  
   - **Struktur Prompt:**  
     - Jelas dan spesifik (misal: *"Gunakan format JSON untuk semua respons"*).  
     - Beri contoh respons sukses/gagal untuk membimbing AI.  
   - **Contoh Prompt Efektif:**  
     *"Anda adalah agen manajemen pengeluaran. Untuk setiap langkah, hasilkan respons dalam format JSON dengan kunci 'action' dan 'params'. Jangan tambahkan teks lain."*  

4. **Parsing Respons dengan Format Terstruktur**  
   - **Tantangan:** AI cenderung menghasilkan teks bebas, sedangkan sistem komputer butuh struktur (misal: API calls, SQL queries).  
   - **Solusi:**  
     - Minta AI menghasilkan respons dalam format tertentu (JSON, XML).  
     - Gunakan ekstraksi pola (regex) atau parser khusus untuk memetakan respons ke aksi.  

5. **Integrasi dengan Sistem Komputer**  
   - **API Calls:** AI bisa memerintahkan sistem untuk memanggil fungsi tertentu (misal: `add_expense()`).  
   - **Contoh:**  
     ```python  
     if action == "add_expense":  
         spreadsheet.add_row(params["destination"], params["amount"], params["date"])  
     ```  
   - **Penanganan Kesalahan:** Jika API gagal, umpan balik kesalahan dikembalikan ke AI untuk penyesuaian.  

6. **Kontrol Loop dan Terminasi**  
   - **Kapan Berhenti?**  
     - Tujuan tercapai (misal: pengeluaran berhasil ditambahkan).  
     - Kesalahan kritis (misal: data tidak valid).  
     - Batas iterasi (untuk mencegah infinite loop).  
   - **Contoh:**  
     ```python  
     while not task_complete and iterations < 10:  
         response = generate_response(prompt)  
         action, params = parse(response)  
         result = execute_action(action, params)  
         prompt += f"\nFeedback: {result}"  
         iterations += 1  
     ```  

---

**Penjelasan Tambahan:**  
Bayangkan agent loop seperti robot pembersih ruangan:  
1. **Prompt:** *"Bersihkan ruangan."*  
2. **AI Memutuskan:** *"Mulai dari sudut kiri, gunakan vakum."*  
3. **Eksekusi:** Robot bergerak dan vakum.  
4. **Umpan Balik:** Sensor mendeteksi debu tersisa.  
5. **Loop Ulang:** AI memerintahkan *"Ulangi di area dekat meja."*  
6. **Selesai:** Saat sensor tidak mendeteksi debu lagi.  

**Tantangan Utama:**  
- **Konsistensi Respons AI:** Jika AI menghasilkan format berbeda-beda, parsing akan gagal.  
- **Error Handling:** Sistem harus bisa menangani kesalahan eksekusi (misal: API down) tanpa crash.  
- **Efisiensi:** Minimalkan jumlah iterasi untuk menghemat sumber daya.  

**Tools & Framework:**  
- **LangChain, AutoGPT, atau CrewAI:** Framework yang menyederhanakan pembuatan agent loop.  
- **Custom Code:** Jika ingin kontrol penuh, buat loop dasar dengan Python dan API model (seperti OpenAI).  

Dengan agent loop, AI tidak hanya menjawab pertanyaan, tapi menjadi asisten aktif yang bisa mengubah tujuan manusia menjadi aksi nyata di sistem komputer.

## Adding Structure to AI Agent Outputs

**Ringkasan Singkat:**  
Untuk membuat AI agen yang bisa memutuskan dan mengeksekusi tindakan, kita perlu **memaksa model menghasilkan respons dalam format yang konsisten dan bisa diproses oleh komputer**. Ada dua pendekatan utama:  
1. **Prompt Engineering + Parsing** (cocok untuk semua model): Membuat prompt yang memandu AI menghasilkan format tertentu (misal: `aksi:objek`), lalu mem-parsingnya dengan kode.  
2. **Function Calling** (hanya untuk model yang mendukung): AI langsung menghasilkan JSON dengan nama fungsi dan parameter, tanpa perlu parsing manual.  

---

**Poin-Poin Penting:**  

1. **Masalah Utama: AI "Chatty" & Tidak Konsisten**  
   - Model generatif cenderung menghasilkan teks panjang dan berbeda-beda setiap kali dijalankan.  
   - Contoh: Jika diminta perintah Bash untuk cek IP, AI mungkin menghasilkan respons dengan format berbeda (misal: ada markdown, penjelasan tambahan, atau variasi struktur).  

2. **Solusi #1: Prompt Engineering + Parsing**  
   - **Tujuan:** Membuat template respons yang bisa diproses komputer.  
   - **Contoh Prompt:**  
     *"Anda adalah agen dapur. Setiap langkah, hasilkan respons dalam format: AKSI:OBJEK. Pilihan aksi: pickup, use, discard. Objek: pan, butter, green bean, dll."*  
   - **Parsing:**  
     - AI menghasilkan `pickup:pan`, sistem membaca `aksi = "pickup"` dan `objek = "pan"`.  
     - Jika AI menghasilkan `PICKUP:PAN` (kapital) atau `pick up:pan` (spasi), parsing harus fleksibel (misal: lowercase semua atau regex).  

3. **Simulasi Agent Loop Manual**  
   - **Contoh Interaksi:**  
     1. **User:** *"Cook savory green beans."*  
     2. **AI:** `pickup:pan`  
     3. **Sistem:** *"Handle breaks off pan."*  
     4. **AI:** `discard:pan`  
   - **Cara Kerja:** Setiap respons AI ditambahkan ke prompt sebagai riwayat (history), sehingga model "ingat" konteks sebelumnya.  

4. **Strategi untuk Konsistensi**  
   - **Template Detail:**  
     - Beri placeholder untuk penjelasan AI (supaya tidak acak-acakan di luar format).  
     - Contoh:  
       ```  
       Reasoning: [Penjelasan AI]  
       Action: [Nama Fungsi]  
       Args: {"param1": "nilai"}  
       ```  
   - **Contoh Praktis:**  
     - **Prompt:** *"Gunakan fungsi `fetch_webpage(url)` untuk mengambil halaman Vanderbilt. Output dalam format: Action: fetch_webpage, Args: {url: 'https://vanderbilt.edu'}."*  
     - **Respons AI:**  
       ```  
       Action: fetch_webpage  
       Args: {"url": "https://vanderbilt.edu"}  
       ```  

5. **Solusi #2: Function Calling (Jika Model Mendukung)**  
   - **Cara Kerja:**  
     - Developer memberikan daftar fungsi yang tersedia (misal: `add_expense()`, `search_database()`).  
     - AI langsung menghasilkan JSON dengan nama fungsi dan parameter.  
   - **Contoh Output:**  
     ```json  
     {  
       "name": "fetch_webpage",  
       "arguments": {"url": "https://vanderbilt.edu"}  
     }  
     ```  
   - **Keuntungan:**  
     - Tidak perlu parsing manual.  
     - Format konsisten, lebih aman untuk eksekusi otomatis.  

6. **Tantangan & Pertimbangan**  
   - **Error Handling:**  
     - Jika AI menghasilkan format salah, sistem perlu mekanisme retry atau fallback.  
     - Contoh: Jika AI menghasilkan `aksi:salah`, sistem bisa mengabaikan atau meminta ulang.  
   - **Keamanan:**  
     - Jangan langsung eksekusi perintah Bash/Python tanpa validasi (risiko keamanan tinggi).  
   - **Kompatibilitas Model:**  
     - Function calling hanya tersedia di model tertentu (misal: OpenAI GPT-3.5/4, Anthropic Claude 2).  

---

**Penjelasan Tambahan:**  
Bayangkan AI agen seperti asisten virtual yang bisa "berbicara" dengan komputer menggunakan bahasa yang bisa dimengerti kedua belah pihak.  

- **Prompt Engineering + Parsing** mirip dengan melatih anak kecil menggunakan buku latihan:  
  - Anda tunjukkan contoh format respons (`pickup:pan`), lalu ajari sistem untuk "membaca" pola tersebut.  
  - Jika AI menghasilkan respons di luar format (misal: `PICKUP PAN` tanpa titik dua), parsing harus bisa menyesuaikan.  

- **Function Calling** seperti memberi asisten virtual sebuah kamus fungsi bawaan:  
  - Anda bilang, *"Gunakan fungsi `fetch_webpage()`,"* AI langsung tahu harus menghasilkan JSON dengan parameter URL.  
  - Ini lebih efisien, tapi membutuhkan model yang mendukung.  

**Contoh Analogi:**  
Jika AI adalah robot pelayan restoran:  
- **Prompt Engineering:** Anda mengajarnya dengan kata-kata, *"Bawa makanan ke meja 5 menggunakan format: BAWA:MEJA5:NASIGORENG."*  
- **Function Calling:** Robot sudah terinstal aplikasi *TakeOrder()* dan *DeliverFood()*, tinggal memanggil fungsi tersebut.  

**Kapan Menggunakan Masing-Masing Pendekatan?**  
- **Pilih Prompt Engineering:**  
  - Model tidak mendukung function calling.  
  - Butuh kontrol penuh atas format respons.  
- **Pilih Function Calling:**  
  - Model mendukung (misal: OpenAI API).  
  - Ingin meminimalkan kesalahan parsing.  

Dengan kedua pendekatan ini, AI agen bisa bertransformasi dari "penjawab pertanyaan" menjadi "pelaku tindakan" yang bisa mengubah tujuan manusia menjadi aksi nyata di sistem komputer.