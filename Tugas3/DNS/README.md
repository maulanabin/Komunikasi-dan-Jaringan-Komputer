# DNS (Domain Name System)

### A. Pengertian

![Telp-Book](images/telp.png)

Bayangkan kalian sedang mencari nomor telepon seseorang di buku kontak ponsel kalian. Umumnya kalian akan mencari dengan menggunakan nama orang yang dituju, bukan nomor teleponnya. Nah, DNS memiliki cara kerja yang sama. Saat kalian ingin mengakses sebuah website, kalian akan mengetik nama website tersebut (contohnya "www.youtube.com"), dan DNS akan mencari tahu nomor IP server yang menyimpan website tersebut. Setelah itu, komputer kalian akan menghubungi server yang menggunakan alamat IP tersebut.

#### Jadi, DNS adalah...

DNS (_Domain Name System_) adalah sistem penamaan untuk semua device (smartphone, computer, atau network) yang terhubung dengan internet. DNS Server berfungsi menerjemahkan nama domain menjadi alamat IP. DNS dibuat untuk menggantikan sistem penggunaan file host yang dianggap kurang efisien.

---

### B. Cara Kerja

![DNS](./images/1.jpg)

Berikut adalah cara kerja DNS:
1. Ketika kamu mengetik alamat website (seperti www.contoh.com) di browser, komputer (client) akan meminta alamat IP dari website tersebut ke server DNS. 🌐
   
2. Jika server DNS sudah tahu alamat IP dari website itu, maka server DNS akan mengirimkan alamat IP tersebut kembali ke komputer kamu. 🔄

3. Jika server DNS tidak tahu alamat IP-nya, server tersebut akan bertanya ke server DNS lain sampai menemukan alamat IP yang tepat. 🔍

4. Setelah alamat IP ditemukan, server DNS mengirimkannya ke komputer kamu, dan barulah browser dapat mengakses website tersebut. 📲

Hal ini mirip seperti saat mencari nomor telepon seseorang di buku kontak. Kalau buku kontak pertama tidak punya nomornya, kalian bisa mencari di buku kontak lainnya. 📚

---

### 1.1.C Aplikasi DNS Server

#### Apa itu DNS Server?

Bayangkan DNS server seperti penerjemah. Ketika kamu mengetik nama website di browser, komputer tidak langsung mengerti nama tersebut. Jadi, komputer bertanya ke DNS server untuk "menerjemahkan" nama website menjadi alamat IP, seperti nomor rumah di internet. 🏠

Untuk praktikum jarkom kita menggunakan aplikasi BIND9 sebagai DNS server, karena BIND (Berkley Internet Naming Daemon) adalah DNS server yang paling banyak digunakan dan juga memiliki fitur-fitur yang cukup lengkap.

---

### List DNS Record

#### Apa itu DNS Record?

DNS record adalah catatan di DNS server yang membantu menghubungkan nama website yang kalian ketik dengan alamat IP servernya. Jadi, saat kalian mengetik nama website (seperti www.youtube.com), DNS record memberitahu browser ke mana harus pergi untuk menemukan website tersebut, seperti petunjuk arah di internet. 🗺️

| Tipe          | Deskripsi                                                                                      |
| ------------- |:---------------------------------------------------------------------------------------------|
| A             | Memetakan nama domain ke alamat IP (IPv4) dari komputer hosting domain.                       |
| AAAA          | AAAA record hampir mirip A record, tapi mengarahkan domain ke alamat IPv6.                     |
| CNAME         | Alias dari satu nama ke nama lain: pencarian DNS akan dilanjutkan dengan mencoba pencarian baru.|
| NS            | Delegasikan zona DNS untuk menggunakan authoritative name servers yang diberikan.            |
| PTR           | Digunakan untuk Reverse DNS (Domain Name System) lookup.                                      |
| SOA           | Mengacu server DNS yang menyediakan otorisasi informasi tentang sebuah domain internet.        |
| TXT           | Mengijinkan administrator untuk memasukkan data acak ke dalam catatan DNS. Ini juga digunakan dalam SPF. |

---

### SOA (Start of Authority)

#### Apa itu SOA?

SOA (Start of Authority) adalah catatan penting dalam DNS yang memberikan informasi tentang pengelolaan suatu DNS zone. Kita bisa membayangkan DNS zone seperti kompleks perumahan, dan SOA record sebagai pemilik kompleks yang bertanggung jawab untuk semua rumah di dalamnya. 🏡

#### Apa itu DNS Zone?

DNS zone adalah bagian dari sistem DNS yang mengelola semua catatan untuk satu domain atau subdomain. Seperti sebuah kompleks perumahan yang memiliki banyak rumah, setiap rumah mewakili catatan DNS (seperti A record, CNAME record, dll.) dalam zone tersebut. Semua catatan ini bekerja sama untuk memastikan bahwa informasi di internet bisa diakses dengan benar. 🌍

Adalah informasi yang dimiliki oleh suatu DNS zone.

| Nama          | Deskripsi                                                                                      |
| ------------- |:---------------------------------------------------------------------------------------------|
| Serial        | Jumlah revisi dari file zona ini. Kenaikan nomor ini setiap kali file zona diubah.           |
| Refresh       | Waktu dalam detik nameserver sekunder harus menunggu untuk memeriksa salinan baru zona DNS.   |
| Retry         | Waktu dalam detik untuk mencoba refresh lagi jika upaya sebelumnya gagal.                     |
| Expire        | Waktu dalam detik bahwa nameserver sekunder akan menahan zona sebelum tidak lagi memiliki otoritas. |
| Minimum       | Waktu dalam detik bahwa catatan sumber daya domain tetap valid.                               |
| TTL           | Waktu untuk tinggal - Waktu nama domain di-cache sebelum kadaluarsa dan harus memeriksa ulang. ⏳

---

## References 📚
* [HowStuffWorks - DNS](https://computer.howstuffworks.com/dns.htm)
* [SoftLayer FAQ - Serial, Refresh, Retry, Expire, Minimum, and TTL](http://knowledgelayer.softlayer.com/faq/what-does-serial-refresh-retry-expire-minimum-and-ttl-mean)
* [Wikipedia - List of DNS Record Types](https://en.wikipedia.org/wiki/List_of_DNS_record_types)
* [IndoWebsite - Pengertian DNS Record](https://kb.indowebsite.id/knowledge-base/pengertian-catatan-dns-atau-record-dns/)
