# 🌿 Multi-Account Grass Bot

Grass Bot ini dikembangkan untuk **multi akun paralel** menggunakan **WebSocket** dan **proxy**.  
Bot ini otomatis melakukan **PING**/**PONG** ke server Grass, menjaga koneksi tetap aktif untuk banyak akun sekaligus.

---

## ✨ Fitur Utama
- 🔥 **Multi-account**: Support banyak akun sekaligus (konfigurasi di `config.json`).
- 🚀 **Multi-threaded**: Masing-masing akun berjalan paralel.
- 🛡️ **Proxy support**: Setiap akun bisa menggunakan proxy masing-masing.
- 📋 **Logging lengkap**: Log `PING`, `PONG`, error, koneksi, semua ditandai `user_id`.
- 🔒 **Auto-reconnect**: Koneksi bot akan retry otomatis jika disconnect.

---

## 📦 Instalasi

1. **Clone repository**:
   ```bash
   git clone https://github.com/username/grassbot-multi.git
   cd grassbot-multi
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Buat file `config.json`** (contoh format):
   ```json
   [
     {
       "user_ids": ["your_user_id_1"],
       "base_proxy": "http://your-proxy-1:port"
     },
     {
       "user_ids": ["your_user_id_2"],
       "base_proxy": "http://your-proxy-2:port"
     }
   ]
   ```

4. **Jalankan bot**:
   ```bash
   python bot.py
   ```

---

## 🛠️ Konfigurasi
- **config.json** harus berisi list akun, tiap akun bisa satu atau lebih `user_ids`.
- **base_proxy** harus format `http://user:pass@proxyserver:port` atau bisa `http://ip:port` biasa.

---

## 📋 Cara Kerja
- Saat bot jalan, Anda akan diminta input **jumlah thread** per akun.
- Setiap akun akan dijalankan dalam beberapa thread sesuai input Anda (maksimal 10).
- Bot akan:
  - Melakukan check-in ke server Grass.
  - Membuka koneksi WebSocket melalui proxy.
  - Otomatis mengirim **PING** dan menerima **PONG**.
  - Jika koneksi error, bot akan otomatis retry.

---

## 🔥 Logging
Semua aktivitas bot akan dicatat ke:
- `bot.log` (file log harian)
- Terminal console real-time

Format log:
```
[HH:MM:SS] | INFO | [UID:user_id] 💬 PING dikirim (id: xxx)
[HH:MM:SS] | INFO | [UID:user_id] 💬 PONG diterima (id: yyy)
```

---

## 📜 License
This project is licensed under the MIT License.

---

**Made with ❤️ for Grass.io community.**

