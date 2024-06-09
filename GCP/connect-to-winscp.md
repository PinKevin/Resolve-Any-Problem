# Connect to WinSCP for File Transfer

1. Di tab yang terbuka, pilih Tools -> PuTTY Gen
2. Pilih generate key
3. Ganti key comment dengan username
4. Isi passphrase
5. Generate public key dan private key, lalu simpan
6. Nilai dari generate key kemudian simpan ke VM, dengan cara Edit VM -> Add SSH Key
7. Buat connection baru.
8. Isi Host Name dengan External IP
9. Isi username dengan Gmail.
10. Pilih Advanced -> Authentication -> Private key file. Pilih file private key dari nomor 5
11. Save, lalu Login
12. Berhasil
