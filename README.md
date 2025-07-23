
# 🚀 Flask-Minimal

**Flask-Minimal** adalah proyek starter sederhana dan efisien berbasis [Flask](https://flask.palletsprojects.com/) yang dirancang untuk memudahkan pengembangan aplikasi web kecil dan prototipe. Seluruh aplikasi hanya terdiri dari **satu file Python (`app.py`)**, menjadikannya ideal untuk pembelajaran, eksperimen, dan produktivitas tinggi tanpa kompleksitas berlebihan.

---

## 🌟 Fitur Utama

* ✅ **Single-file app**: Seluruh logika Flask dalam satu file (`app.py`).
* 🎨 **Template HTML dasar**: Sudah disertakan struktur HTML, CSS, dan JS minimal.
* 🧱 **Struktur proyek ringan**: Tidak membingungkan, mudah dipahami siapa saja.
* ⚡ **Cepat disesuaikan**: Cocok untuk prototipe, demo, atau proyek kecil.
* 🖥️ **Dapat dijalankan otomatis di server (systemd ready)**.

---

## 🛠️ Persiapan

Jalankan perintah berikut untuk memastikan semua dependensi dasar tersedia:

```bash
sudo apt update
sudo apt install python3 python3-venv python3-pip -y
```

---

## 📦 Instalasi

1. **Clone repository**:

```bash
git clone https://github.com/yourusername/flask-minimal.git
cd flask-minimal
```

2. **Buat virtual environment (opsional tapi disarankan)**:

```bash
python3 -m venv venv
source venv/bin/activate
```

3. **Install dependensi**:

```bash
pip install -r requirements.txt
```

4. **Jalankan aplikasi**:

```bash
python app.py
```

Buka di browser: [http://localhost:5000](http://localhost:5000)

---

## 🔄 Menjalankan Otomatis di Server (Contoh: EC2)

### 1. Buat file service systemd:

```ini
[Unit]
Description=Flask Minimal App
After=network.target

[Service]
Type=simple
User=ubuntu
WorkingDirectory=/home/ubuntu/flask-minimal
Environment=PATH=/home/ubuntu/flask-minimal/venv/bin
ExecStart=/home/ubuntu/flask-minimal/venv/bin/python app.py
Restart=always
RestartSec=10

[Install]
WantedBy=multi-user.target
```

### 2. Simpan & aktifkan:

```bash
sudo nano /etc/systemd/system/flask-app.service
```

> Tempel isi file di atas dan simpan (`Ctrl+O`, `Enter`, lalu `Ctrl+X`)

```bash
sudo systemctl daemon-reload
sudo systemctl enable flask-app.service
sudo systemctl start flask-app.service
sudo systemctl status flask-app.service
```

---

## ✏️ Penggunaan

Struktur proyek dibuat seminimal mungkin agar mudah dikembangkan:

```
flask-minimal/
├── app.py
├── templates/
│   └── index.html
├── static/
│   ├── style.css
│   └── script.js
├── venv/ (opsional)
└── requirements.txt
```

---

## 🎨 Kostumisasi

Modifikasi proyek sesuai kebutuhan Anda:

* 🧾 HTML: `templates/index.html`
* 🎨 CSS: `static/style.css`
* ⚙️ JS: `static/script.js`
* 🧠 Logika Flask: `app.py`

---

## 📜 Lisensi

Proyek ini menggunakan [Lisensi MIT](LICENSE). Silakan digunakan, disesuaikan, dan disebarluaskan!

---

## 🤝 Kontribusi

Ingin menyumbang ide, memperbaiki bug, atau menambahkan fitur?

* Fork repo ini
* Buat pull request
* Atau buka **issue** untuk berdiskusi!
