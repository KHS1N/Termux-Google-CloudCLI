# Termux-Google-CloudCLI
Cara menginstall Google Cloud Cli dalam termux

Cara menginstall Google Cloud Shell atau Google Cloud Cli dalam termux yaitu :
sebelum menjalankan perintah di bawah ini, teman-teman perlu mendaftar terlebih dahulu di cloud.google.com secara gratis, jika sudah silahkan ikuti perintah dibawah ini.

1. **Memperbarui dan Menginstal Dependensi:**
   Pertama, jalankan perintah berikut untuk memperbarui paket dan menginstal dependensi yang diperlukan:
   
   - apt update -y && apt upgrade -y
   - pkg up -y openssl curl python openssh
  
2. **Unduh Google Cloud CLI:**
   Selanjutnya, unduh Google Cloud CLI dengan perintah ini:
   
   - curl -O https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-cli-439.0.0-linux-arm.tar.gz
  
3. **Ekstrak Google Cloud CLI:**
   Ekstrak arsip Google Cloud CLI yang telah diunduh:
  
   - tar -xf google-cloud-cli-439.0.0-linux-arm.tar.gz

4. **Instal Google Cloud CLI:**
   Instal Google Cloud CLI dengan menjalankan skrip instalasi:
   
   ./google-cloud-sdk/install.sh
   - Pilih Y
   - Pilih Y
   - Tekan Enter

5. **Inisialisasi Google Cloud CLI:**
   Inisialisasi Google Cloud CLI dengan perintah berikut:
   
   ./google-cloud-sdk/bin/gcloud init
   - Pilih Y
   - Pilih Y
   - Pilih N
   
6. **Akses Google Cloud Shell:**
   Gunakan perintah ini untuk mengakses Google Cloud Shell:
   
   gcloud alpha cloud-shell ssh
   
   - Pilih Y
   - Tekan Enter

7. **Solusi jika Perintah 6 Gagal:**
   Jika perintah pada langkah 6 tidak berhasil, gunakan perintah berikut untuk mengotorisasi sesi:
   Perintah shell untuk dijalankan sebelum menggunakan perintah no. 8
   
   gcloud alpha cloud-shell ssh --authorize-session
   
8. **Login Tanpa Sandi dan Password:**
   Terakhir perintah, untuk login tanpa memasukkan sandi dan password, jalankan perintah berikut:
   
   gcloud auth login --no-launch-browser

   jika semuanya sudah terinstall, silahkan buatkan bash shell dengan perintah :

   nano shell.sh

paste kode di bawah ini :
   
   #!/bin/bash
   gcloud alpha cloud-shell ssh --authorize-session
   
jika sudah silakan keluar dan simpan dengan ctrl + -X, jalankan dalam termux kalian :
   ./shell.sh
