# Sekilas Tentang
**Sonar** adalah sebuah *Private Video Recorder* (PVR) untuk konten-konten video dan acara TV yang gratis dan *open source*. Sonarr mampu memonitor RSS Feeds untuk acara-acara TV yang baru saja rilis, dan mampu melakukan pengunduhan, *sorting*, dan modifikasi secara otomatis. Selain itu, Sonarr juga dapat dikonfigurasi untuk melakukan *upgrade* secara otomatis terhadap kualitas *files* yang diunduh apabila kualitas terbaru sudah tersedia 

# Instalasi

#### Kebutuhan Sistem

- Unix, Linux atau Windows
- .NET Core (Linux atau MacOS)
- Mono (Linux/MacOS) untuk menjalankan program dengan framework .NET
- RAM dengan kapasitas minimial 1 GB
- Penyimpanan memori dengan kapasitas minimal 1 GB
- Cloudflared agar website bisa diakses secara publik
- Visual Studio Code

#### Proses Instalasi:

1. Pastikan seluruh sistem kita *up-to-date*, dan install seluruh kebutuhan sistem yang diperlukan, seperi `dotnet `, `mono`, dan `cloudflared`  
   ```
   sudo apt update
   sudo apt upgrade
   sudo apt install mono-complete
   sudo apt-get install -y dotnet-sdk-6.0
   ```

2. Unduh **Sonarr** ke dalam direktori kita
   ```
   wget "https://services.sonarr.tv/v1/download/main/latest?version=4&os=linux&arch=x64" -O sonarr.tar.gz
   ```

3.  Ekstrak file yang telah diunduh ke dalam direktori yang kita inginkan, disini saya langsung mengekstrak file di direktori home/username 
   ```
   tar -xvzf sonarr.tar.gz
   ```

5. Unduh package `cloudflared` sesuai dengan jenis Linux yang anda gunakan. Karena saya menggunakan Kali Linux, maka saya menggunakan Cloudflared dengan versi `amd64`
   ```
   wget https://path-to-cloudflared/cloudflared-linux-amd64.deb
   ```

6. Install package `cloudflared` 
   ```
   wget https://path-to-cloudflared/cloudflared-linux-amd64.deb
   ```

7. Pastikan package `Cloudflared` berada pada direktori yang sama dengan `Sonarr`
   ```
   mv cloudflared-linux-amd64.deb ~/Sonarr/
   ```

8. Buka code editor yang anda gunakan dan jalankan kode berikut. Ganti alamat localhost sesuai dengan komputer yang anda gunakan
   ```
   cloudflared tunnel -url http://localhost:8989
   ```

9. Apabila `Cloudflared` berhasil dijalankan, maka akan mengembalikan output sebaagi berikut. Klik link untuk mengakses Sonarr dan bagikan link tersebut agar bisa dibagikan kepada orang lain.
   ```
   2024-10-12T02:49:42Z INF +--------------------------------------------------------------------------------------------+
   2024-10-12T02:49:42Z INF |  Your quick Tunnel has been created! Visit it at (it may take some time to be reachable):  |
   2024-10-12T02:49:42Z INF |  https://campaign-ins-solutions-pierre.trycloudflare.com                                   |
   2024-10-12T02:49:42Z INF +--------------------------------------------------------------------------------------------+
   ```

