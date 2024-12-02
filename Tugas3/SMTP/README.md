## By: Maulana Bintang Irfansyah - 1224800005

## Pendahuluan

Sebelum kita melakukan setup seperti instalasi dan konfigursai sesuatu hal, dalam hal ini adalah mail server. Alangkah baiknya kita mengetahui
terlebih dahulu cara kerja, kegunaan, kelebihan dan kekurangan disetiap protokol yang akan digunakan.

Dalam hal ini terdapat beberapa protokol yang sering digunakan di mail server, yaitu:

- SMTP
- POP3
- IMAP

## SMTP

SMTP atau `Simple Mail Transfer Protocol` merupakan protokol email yang digunakan untuk mengirim sebuah email. Protokol ini memiliki satu set perintah yang meng-autentikasi dan mengarahkan transfer email.

Sebagai contoh, jika Anda mengirimkan sebuah email menggunakan email client, seperti Microsoft Outlook, dan ketika Anda menekan tombol kirim, email akan melakukan perjalanan atau terkirim dari komputer Anda ke mail server menggunakan protokol SMTP ini. Maka dari itu, mail server ini juga dapat disebut atau merupakan sebuah SMTP Server.

Sebagai contoh, jika Anda menggunakan Gmail untuk SMTP Server-nya, maka alamat yang harus diisi adalah `smtp.gmail.com`, dan SMTP Server akan mengirimkan pesan ke penerima atau tujuan menggunakan SMTP.

![Mail](/Tugas3/SMTP/Gbr1.png)

Kemudian, email akan bertahan di mail server penerima hingga user login menggunakan email dan men-download email menggunakan POP3 atau IMAP, atau mereka juga dapat melihat email secara langsung di server menggunakan webmail.

Untuk jenis protokol jaringan yang digunakan, SMTP ini adalah TCP.

Kesimpulannya adalah pada dasarnya SMTP ini seperti mailman atau pengantar pos. Mailman membawa email dari mailbox Anda di rumah, kemudian menemukan jalur yang tepat dan mengirimkan ke destinasi mailbox.

### Cara Kerja SMTP

1. **Pengiriman Email**: Ketika Anda mengirim email, email client Anda menghubungi SMTP server untuk memulai proses pengiriman.
2. **Proses Autentikasi**: SMTP server melakukan autentikasi untuk memastikan bahwa pengirim memiliki izin untuk mengirim email.
3. **Pengiriman ke Mail Server Tujuan**: Setelah autentikasi, SMTP server mengirimkan email ke mail server penerima menggunakan alamat email tujuan.
4. **Penyimpanan di Mail Server Penerima**: Email akan disimpan di mail server penerima hingga penerima mengaksesnya melalui POP3 atau IMAP.

### Kelebihan dan Kekurangan SMTP

- **Kelebihan**:
  - Protokol yang sederhana dan mudah digunakan.
  - Mendukung pengiriman email ke banyak penerima sekaligus.
  - Dapat digunakan dengan berbagai jenis email client.

- **Kekurangan**:
  - Tidak mendukung enkripsi secara default, meskipun dapat diimplementasikan dengan TLS/SSL.
  - Rentan terhadap spam dan penyalahgunaan jika tidak dilindungi dengan baik.

Dengan memahami cara kerja dan fungsi SMTP, Anda akan lebih siap untuk melakukan konfigurasi dan troubleshooting pada mail server yang Anda kelola.


## POP3 dan IMAP

2 protokol tersebut merupakan protokol yang digunakan untuk menerima sebuah email dari mail server, sebagai contoh jika Anda menggunakan email client seperti microsoft outlook, Anda harus melakukan konfigurasi outlook menggunakan POP3 atau IMAP untuk menerima sebuah email pada komputer Anda.

Anda juga dapat menggunakan protokol ini pada tablet atau smartphone untuk menerima email. Anda dapat menggunakan salah satu dari protokol tersebut. Pilihannya ada di tangan Anda.

Namun terdapat pertanyaan, "_Protokol mana yang harus Saya gunakan? apakah salah satunya lebih baik dari yang lain?_"

### POP3

POP3 merupakan akronim atau singkatan dari `Post Office Protocol 3`. POP3 adalah protokol yang simpel dari kedua hal tersebut (POP3 dan IMAP) karena POP3 akan melakukan download email ke dalam device atau perangkat Anda dari sebuah mail server.

Dan hal tersebut hanya akan mendownload apa yang ada di folder inbox, yang dimana itu adalah email Anda dan itu cukup bagus bukan? karena tidak akan mendownload folder lain atau konten lain. Jadi tidak akan mendownload folder seperti `Sent`, `Items`, `Drafts`, `Deleted Email` Anda.

Karena hanya mendownload apa yang ada di folder inbox maka dari itu POP3 tidak akan melakukan segala jenis sinkronisasi.

### IMAP

IMAP merupakan akronim atau singkatan dari `Internet Message Access Protocol`. IMAP juga sama halnya dengan POP3 yaitu protokol yang berfungsi untuk menerima email namun IMAP sedikit berbeda dengan POP3.

IMAP menginzinkan Anda melihat email dari server untuk multiple device atau perangkat dan email tersebut disimpan di server dan juga disimpan di _local cache_ untuk copy email di semua device atau perangkat. Tentu dengan sinkronisasi semua folder Anda dan semua hal didalamnya.
