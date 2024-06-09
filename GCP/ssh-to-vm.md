# SSH to VM

Pastikan punya Remote-SSH Extension di VS Code

1. Buka Command Palette, pilih Open SSH Configuraton File
2. Buat dengan format
   ```
   Host 'name'
     HostName 'external ip'
     User 'username'
     IdentityFile 'path'
   ```
4. Setelah itu, buat key dengan command
   ```
   ssh-keygen -t rsa -f 'name' -C 'username' -b 2048
   ```
6. Akan dibuat private-key dan public-key.pub
7. Copy public key, lalu pilih Edit VM -> SSH Keys -> Add Item
8. Tinggal Connect to Host sesuai 'name', pilih Linux.
