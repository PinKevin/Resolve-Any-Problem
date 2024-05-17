# Can't Deploy on Cloud Run
# Tidak bisa deploy di Cloud Run

## Node.js
1. (Jika menggunakan Tensorflow.js) Pastikan menggunakan versi Ubuntu, misal 18.20.2
  ```FROM node:18.20.2```
2. Pastikan .env ada
3. Pastikan host 0.0.0.0 dan bukan localhost
4. Pastikan expose port
