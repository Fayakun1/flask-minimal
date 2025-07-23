# flask-minimal

Proyek starter Flask minimal yang dirancang untuk membantu Anda dengan cepat mengatur aplikasi web yang bersih, sederhana, dan efisien. Proyek ini terstruktur agar ringan dan berfokus pada produktivitas, dengan semua kode berada dalam satu file (`app.py`), serta templat dan aset statis dasar.

## Fitur
- Aplikasi Flask satu file (`app.py`) untuk produktivitas dan kesederhanaan maksimal.
- Struktur HTML dasar dengan sedikit gaya dan JavaScript.
- Penyiapan proyek yang sederhana dan intuitif tanpa kompleksitas yang tidak perlu.
- Mudah dikustomisasi untuk pengembangan aplikasi web yang cepat.

---

## Persiapan

Jalankan perintah berikut untuk menginstal dependensi Python:

```bash
sudo apt update
sudo apt install python3 python3-venv python3-pip -y
````

---

## Instalasi

1. **Clone repositori:**

   ```bash
   git clone https://github.com/Fayakun1/flask-minimal.git
   cd flask-minimal
   ```

2. **Buat virtual environment (disarankan):**

   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Install dependensi yang diperlukan:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Jalankan aplikasi:**

   ```bash
   python app.py
   ```

   Aplikasi Flask akan berjalan di [http://localhost:5000](http://localhost:5000)

---

## Menjalankan Flask Otomatis Setelah Reboot (Linux/Ubuntu)

Agar aplikasi Flask tetap berjalan otomatis setelah instance/server di-reboot, ikuti langkah berikut:

1. **Pastikan semua sudah berjalan:**

   Jalankan perintah berikut dari direktori `flask-minimal`:

   ```bash
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```

2. **Buat file service systemd:**

   Jalankan:

   ```bash
   sudo nano /etc/systemd/system/flask-minimal.service
   ```

   Isi dengan konfigurasi berikut (ganti `/home/ubuntu` jika username atau path kamu berbeda):

   ```ini
   [Unit]
   Description=Aplikasi Flask Minimal
   After=network.target

   [Service]
   User=ubuntu
   WorkingDirectory=/home/ubuntu/flask-minimal
   ExecStart=/home/ubuntu/flask-minimal/venv/bin/python app.py
   Restart=always

   [Install]
   WantedBy=multi-user.target
   ```

3. **Aktifkan dan jalankan servicenya:**

   ```bash
   sudo systemctl daemon-reload
   sudo systemctl enable flask-minimal.service
   sudo systemctl start flask-minimal.service
   ```

4. **Cek status service:**

   ```bash
   sudo systemctl status flask-minimal.service
   ```

   Jika sukses, statusnya akan `active (running)`.

---

## Penggunaan

Proyek ini siap digunakan sebagai dasar untuk membangun aplikasi web. File `app.py` berisi semua rute dan logika Flask, sehingga mudah untuk dikembangkan dan dikustomisasi.

Anda bisa menambahkan:

* Template tambahan di folder `templates/`
* File CSS atau JS tambahan di folder `static/`
* Rute baru langsung di `app.py`

---

## Kustomisasi

Anda dapat memodifikasi:

* Struktur HTML di `templates/index.html`
* Gaya tampilan di `static/style.css`
* Interaktivitas di `static/script.js`
* Tambahkan rute dan logika lain di `app.py`

---

## Lisensi

Proyek ini menggunakan lisensi [MIT License](LICENSE).

---

## Kontribusi

Silakan fork repositori ini dan buat *pull request* jika memiliki perbaikan atau penambahan fitur. Jika ada saran atau masukan, buka issue untuk kita diskusikan bersama.

Proyek ini dibangun dengan kesederhanaan dan efisiensi sebagai prioritas utama — sempurna untuk memulai aplikasi kecil atau prototipe dengan cepat.

```

---
