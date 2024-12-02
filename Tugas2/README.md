
## Komunikasi dan Jaringan Komputer 
### Dosen Pengampuh: Dr. Ferry Astika Saputra, ST, M.Sc. 

<br>

# 📡 Analisis TCP Flow
## By: Maulana Bintang Irfansyah - NRP 1224800005


Tugas ini bertujuan untuk melakukan analisis mendalam terhadap alur data TCP dari sesi komunikasi jaringan. Dengan menggunakan Wireshark, kita dapat memahami lebih baik cara kerja protokol TCP, termasuk proses pengiriman data, penerimaan data, retransmisi, dan alur three-way handshake.

---

## 📋 Pendahuluan

Protokol TCP adalah salah satu protokol inti di jaringan komputer yang memastikan data dikirim dengan urutan yang benar. Proyek ini menyajikan:
- Analisis **three-way handshake**.
- Dokumentasi **sequence number** dan **acknowledgment number**.
- Identifikasi potensi retransmisi.
- Visualisasi flow graph untuk menggambarkan alur komunikasi.

---

## 📂 Struktur File

- **`wow1.png`**: Gambar flow graph pertama.
- **`wow2.png`**: Gambar flow graph kedua.
- **`README.md`**: Dokumentasi proyek ini.

---

## 🛠️ Cara Penggunaan

1. **Instal Wireshark**  
   Pastikan Wireshark sudah terinstal di komputer Anda.

2. **Buka File Capture**  
   Impor file `.cap` ke Wireshark untuk melihat alur komunikasi.

3. **Gunakan Filter TCP**  
   Filter paket menggunakan `tcp` untuk memfokuskan hanya pada protokol TCP.

4. **Visualisasi Flow Graph**  
   Gunakan fitur `Statistics > Flow Graph` di Wireshark untuk menghasilkan grafik alur seperti contoh di bawah ini.

---

## 📊 Hasil Analisis

Berikut adalah hasil analisis alur data TCP yang ditampilkan dalam tabel:

| **No.** | **Sumber** | **Seq** | **Ack** | **Deskripsi**                           |
|---------|------------|---------|---------|-----------------------------------------|
| 1       | Client     | 0       |         | SYN: Memulai koneksi TCP                |
| 2       | Server     | 0       | 1       | SYN-ACK: Merespons permintaan koneksi   |
| 3       | Client     | 1       | 1       | ACK: Mengonfirmasi koneksi              |
| 4       | Client     | 480     | 1381    | Data baru dikirim                       |
| 5       | Server     | 1381    | 480     | ACK: Konfirmasi penerimaan data         |
| ...     | ...        | ...     | ...     | ...                                     |
## 📊 Contoh Tabel Output

Berikut adalah hasil analisis alur data TCP yang dirangkum dalam tabel:

| **No.** | **Sumber** | **Seq** | **Ack** | **Deskripsi**                           |
|---------|------------|---------|---------|-----------------------------------------|
| 1       | Client     | 480     |         | Data dikirim dari Client                |
| 5       | Client     | 1       | 480     | Data dikirim ulang atau paket ACK diterima |
| 6       | Client     | 480     | 1381    | Data baru dikirim                       |
| 7       | Server     | 1381    | 480     | ACK: Server mengonfirmasi penerimaan data |
| 8       | Client     | 480     | 2761    | Data baru dikirim                       |
| 9       | Server     | 2761    | 480     | ACK: Server mengonfirmasi penerimaan data |
| 10      | Client     | 4141    | 480     | Data baru dikirim                       |
| 11      | Server     | 480     | 5521    | ACK: Server mengonfirmasi penerimaan data |
| 12      | Client     | 5521    | 480     | Data baru dikirim                       |
| 13      | Client     | 480     | 6901    | Data baru dikirim                       |
| 14      | Server     | 6901    | 480     | ACK: Server mengonfirmasi penerimaan data |
| 15      | Client     | 1       | 1       | ACK dikirim ulang                       |
| 16      | Client     | 480     | 8281    | Data baru dikirim                       |
| 17      | Server     | 8281    | 480     | ACK: Server mengonfirmasi penerimaan data |
| 18      | Client     | 480     | 9661    | Data baru dikirim                       |
| 19      | Server     | 9661    | 480     | ACK: Server mengonfirmasi penerimaan data |
| 20      | Client     | 480     | 11041   | Data baru dikirim                       |
| 21      | Server     | 11041   | 480     | ACK: Server mengonfirmasi penerimaan data |
| 22      | Client     | 1       | 722     | Data baru dikirim                       |
| 23      | Client     | 480     | 12421   | Data baru dikirim                       |
| 24      | Client     | 1       | 722     | Data baru dikirim ulang                 |
| 25      | Client     | 1431    | 722     | Data baru dikirim                       |
| 26      | Server     | 722     | 1591    | ACK: Server mengonfirmasi penerimaan data |
| 27      | Client     | 12421   | 480     | Data baru dikirim                       |
| 28      | Client     | 480     | 13801   | Data baru dikirim                       |
| 29      | Server     | 13801   | 480     | ACK: Server mengonfirmasi penerimaan data |
| 30      | Client     | 15181   | 480     | Data baru dikirim                       |
| 31      | Client     | 480     | 16561   | Data baru dikirim                       |
| 32      | Server     | 16561   | 480     | ACK: Server mengonfirmasi penerimaan data |
| 33      | Client     | 480     | 17941   | Data baru dikirim                       |
| 34      | Client     | 1       | 722     | Data baru dikirim ulang                 |
| 35      | Server     | 722     | 1591    | ACK: Server mengonfirmasi penerimaan data |
| 36      | Client     | 17941   | 480     | Data baru dikirim                       |
| 37      | Client     | 480     | 18365   | Data baru dikirim                       |
| 38      | Server     | 18365   | 480     | ACK: Server mengonfirmasi penerimaan data |
| 39      | Client     | 480     | 18366   | Data baru dikirim                       |
| 40      | Client     | 480     | 18366   | Data dikirim ulang                      |
| 41      | Server     | 18366   | 481     | ACK: Server mengonfirmasi penerimaan data |

---

## 📈 Flow Graph

Berikut adalah visualisasi flow graph yang diambil dari hasil analisis menggunakan Wireshark:

### Flow Graph 1
![Flow Graph 1](/Tugas2/wow1.PNG)

### Flow Graph 2
![Flow Graph 2](/Tugas2/wow2.PNG)


---

🌟 **Terima kasih** ⭐ 