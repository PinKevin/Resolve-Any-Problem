# Can't Connect to Internet

## Masalah Awal
Saat ngejalanin WSL, dapat error seperti di gambar 
![image](https://github.com/PinKevin/Resolve-Any-Problem/assets/85545297/634d704a-2e6d-437f-bda0-f2b3375cf008)

> Failed to configure network (networkingMode Nat). To disable networking, set `wsl2.networkingMode=None` in C:\Users\user\.wslconfig
Error code: Wsl/Service/CreateInstance/CreateVm/ConfigureNetworking/HNS/0xffffffff

## Solusi
### Uninstall WSL
1. Uninstall wsl dengan command unregister
   ```
   wsl --unregister Ubuntu
   ```
### --------- Penting ----------------  
### Pastikan PORT 53 free
1. Akses ke **System Tools => Resource Monitor**
2. Cek yang menggunakan **port 53** di menu **Network => Listening Port**
3. Matikan proses dengan command di bawah, dengan PID adalah PID proses dengan port 53:
   ```
   taskkill /f /pid [PID]
   ```
4. Akses `Users/[youruser]/AppData/Local/Packages/`, lalu cari `CanonicalGroupLimitedUbuntu...`. Klik kanan folder, pilih **Properties => Advanced**, lalu centang pada *compression for the folder* dimatikan
### --------- Penting ----------------  

### Install Ulang
1. Jalankan
   ```
   wsl --install
   ```
3. Masukkan username dan password baru
4. Jika berhasil, nanti masuk ke Bash

### Agar bisa connect ke internet
1. Setelah masuk ke Bash, jalankan perintah ini agar bisa connect ke internet sampai ngga bisa lagi (semoga tidak)
   ```
   sudo rm /etc/resolv.conf
   sudo bash -c 'echo "nameserver 8.8.8.8" > /etc/resolv.conf'
   sudo bash -c 'echo "[network]" > /etc/wsl.conf'
   sudo bash -c 'echo "generateResolvConf = false" >> /etc/wsl.conf'
   sudo chattr +i /etc/resolv.conf
   ```
