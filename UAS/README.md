# 📡 TCP Segment Analysis
## By: Maulana Bintang I - 1224800005

### 📋 Overview
Dokumen ini menjelaskan analisis segmen TCP berdasarkan pertanyaan terkait transfer file antara client dan server *gaia.cs.umass.edu*. Analisis dilakukan menggunakan Wireshark untuk mengamati rincian koneksi TCP, termasuk **IP Address**, **port number**, **sequence number**, **round trip time (RTT)**, dan **panjang segmen**.

---

## 1️⃣ Pertanyaan dan Jawaban

### 1. **What is the IP address and TCP port number used by your client computer (source) to transfer the file to gaia.cs.umass.edu?**  
**Answer:**  
Figure 1 menunjukkan detail koneksi sisi klien:  
- **IP Address:** 192.168.1.102  
- **Port:** 1161  
Ini adalah alamat sumber dan port ephemeral yang digunakan oleh komputer klien.  

![Figure 1: Client-Side Connection Details](./images/Gbr1.png)

---

### 2. **What does gaia.cs.umass.edu use the IP address and port number to receive the file?**  
**Answer:**  
Figure 2 menunjukkan detail koneksi sisi server:  
- **IP Address:** 128.119.245.12  
- **Port:** 80  
Port 80 adalah port standar untuk komunikasi HTTP selama transfer file.  

![Figure 2: Server-Side Connection Details](./images/Gbr2.png)

---

### 3. **What is the sequence number of the TCP SYN segment that is used to initiate the TCP connection between the client computer and gaia.cs.umass.edu? What is it in the segment that identifies the segment as a SYN segment?**  
**Answer:**  
- **Sequence number:** 0  
- **Identifikasi SYN:** SYN flag disetel ke 1, menandakan inisiasi koneksi TCP.  

![Figure 3: TCP SYN Segment Details](./images/Gbr3.png)

---

### 4. **What is the sequence number of the SYNACK segment sent by gaia.cs.umass.edu to the client computer in reply to the SYN? What is the value of the ACKnowledgement field in the SYNACK segment? How did gaia.cs.umass.edu determine that value?**  
**Answer:**  
- **Sequence number SYNACK:** 0  
- **ACK field:** 1 (dihitung dengan menambahkan 1 ke sequence number SYN dari klien).  
- **Identifikasi SYNACK:** SYN dan ACK flags disetel ke 1.  

![Figure 4: SYNACK Segment Details](./images/Gbr4.png)

---

### 5. **What is the sequence number of the TCP segment containing the HTTP POST command?**  
**Answer:**  
- **Sequence number:** 1  
Untuk menemukan perintah POST, perlu mengecek field data paket di Wireshark dan mencari string "POST".  

![Figure 5: HTTP POST Command](./images/Gbr5.png)

---

### 6. **What are the sequence numbers, RTT, and Estimated RTT values for the first six TCP connection segments?**  
**Answer:**  
Tabel 1 menjelaskan waktu pengiriman, waktu penerimaan ACK, RTT, dan Estimated RTT berdasarkan persamaan:  
**EstimatedRTT = 0.875 × Previous EstimatedRTT + 0.125 × SampleRTT**

| **Segment** | **Seq. Number** | **Sent Time** | **ACK Received** | **RTT (s)** | **Estimated RTT (s)** |
|-------------|-----------------|---------------|------------------|-------------|------------------------|
| 1           | 1               | 0.026477      | 0.053937         | 0.02746     | 0.02746               |
| 2           | 566             | 0.041737      | 0.077294         | 0.035557    | 0.0285                |
| 3           | 2026            | 0.054026      | 0.124085         | 0.070059    | 0.0337                |
| 4           | 3486            | 0.054690      | 0.169118         | 0.11443     | 0.0438                |
| 5           | 4946            | 0.077405      | 0.217299         | 0.13989     | 0.0558                |
| 6           | 6406            | 0.078157      | 0.267802         | 0.18964     | 0.0725                |

![Figure 6: RTT Graph](./images/Gbr6.png)

---

### 7. **What is the length of each of the first six TCP segments?**  
**Answer:**  
- **Segment 1 Length:** 565 bytes  
- **Segment 2–6 Length:** 1460 bytes  

Panjang segmen pertama lebih kecil karena memuat perintah HTTP POST, sementara segmen berikutnya memaksimalkan payload hingga batas MTU (1460 bytes).  

![Figure 7: TCP Segment Lengths](./images/Gbr7.png)

---

### 📈 Kesimpulan
Analisis ini memberikan wawasan tentang alur kerja TCP, termasuk inisiasi koneksi, pengelolaan segmen data, dan penghitungan RTT. Observasi ini berguna untuk mempelajari performa jaringan dan optimisasi alur TCP di lingkungan nyata.

