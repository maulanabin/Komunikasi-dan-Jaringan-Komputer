
## Komunikasi dan Jaringan Komputer 
### Dosen Pengampuh: Dr. Ferry Astika Saputra, ST, M.Sc. 

<br>

# C Socket Programming: Simple Server and Client
## By: Maulana Bintang Irfansyah - NRP 1224800005
Tugas ini merupakan implementasi socket programming menggunakan bahasa C. Program ini mencakup server dan client sederhana, serta mendukung koneksi multi-klien menggunakan multithreading atau multiprocessing. Proyek ini dirancang untuk memperkenalkan konsep dasar komunikasi jaringan berbasis socket.

---

## 📂 File Proyek
1. **server.c**: Server multithreaded yang mendukung beberapa klien secara bersamaan.
2. **server_single.c**: Server singlethreaded yang hanya menangani satu klien pada satu waktu.
3. **client.c**: Program client untuk berkomunikasi dengan server.

---

## ✨ Fitur Utama
1. **Echo Server dan Client**
   - Server menerima pesan dari client dan mengembalikan pesan yang sama (echo).
   - Ketika client mengirimkan pesan "quit", koneksi akan dihentikan.

2. **Server Multi-User**
   - Mendukung koneksi dari beberapa klien secara bersamaan.

---

## 🚀 Langkah Penggunaan

1. **Kompilasi Proyek**
   - Jalankan perintah berikut di direktori proyek untuk mengompilasi:
     ```bash
     make
     ```

2. **Menjalankan Program**
   - Gunakan dua terminal untuk menjalankan server dan client:
     ```bash
     ./server
     ./client
     ```

3. **Cara Menggunakan**
   - Ketikkan teks pada client untuk mengirimkan pesan ke server.
   - Server akan mengembalikan (echo) pesan tersebut.
   - Ketik "quit" untuk menghentikan koneksi.

---
## 📋 Contoh Output

1. **Client Output (Satu Client):**
<br>
   ![image](assets/images/client1.JPG)

2. **Client Output (Dua Client - Terminal 1):**
<br>
   ![image](assets/images/client21.png)

3. **Client Output (Dua Client - Terminal 2):**
<br>
   ![image](assets/images/client22.png)

4. **Server Output:**
<br>
   ![image](assets/images/server.png)

5. **Data Captured in Wireshark:**
<br>
   ![image](assets/images/data_wireshark.png)
---

## 🔧 Catatan
- Jalankan **server** sebelum **client**.
- Koneksi akan otomatis ditutup jika tidak ada aktivitas selama 5 detik (timeout).
- Pastikan koneksi jaringan atau loopback berjalan dengan baik.

---

## 💡 Tips
- Gunakan kode ini untuk mempelajari dasar komunikasi jaringan menggunakan socket.
- Modifikasi untuk menambahkan fitur baru, seperti enkripsi atau logging aktivitas.
