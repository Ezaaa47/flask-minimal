# Flask-Minimal

**Flask-Minimal** adalah proyek starter ringan berbasis [Flask](https://flask.palletsprojects.com/) yang dirancang untuk mempermudah pembuatan aplikasi web sederhana. Seluruh kode berada dalam satu file utama (`app.py`), membuatnya cocok untuk pembelajaran, prototipe cepat, atau proyek kecil.

---

## Fitur

* Aplikasi Flask dalam satu file (`app.py`)
* Struktur HTML, CSS, dan JavaScript dasar
* Setup sederhana dan mudah dipahami
* Siap dikembangkan atau dimodifikasi sesuai kebutuhan
* Dapat dijalankan otomatis saat boot (menggunakan `systemd`)

---

## Persiapan

Pastikan dependensi dasar sudah terpasang:

```bash
sudo apt update
sudo apt install python3 python3-venv python3-pip -y
```

---

## Instalasi

1. Clone repository:

```bash
git clone https://github.com/yourusername/flask-minimal.git
cd flask-minimal
```

2. Buat dan aktifkan virtual environment:

```bash
python3 -m venv venv
source venv/bin/activate
```

3. Install dependensi:

```bash
pip install -r requirements.txt
```

4. Jalankan aplikasi:

```bash
python app.py
```

Aplikasi dapat diakses melalui: [http://localhost:5000](http://localhost:5000)

---

## Menjalankan Otomatis dengan Systemd

### 1. Buat file service

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

### 2. Simpan dan aktifkan service:

```bash
sudo nano /etc/systemd/system/flask-app.service
```

Lalu:

```bash
sudo systemctl daemon-reload
sudo systemctl enable flask-app.service
sudo systemctl start flask-app.service
sudo systemctl status flask-app.service
```

---

## Struktur Proyek

```
flask-minimal/
├── app.py
├── templates/
│   └── index.html
├── static/
│   ├── style.css
│   └── script.js
├── requirements.txt
└── venv/ (opsional)
```

---

## Kustomisasi

Anda bisa mulai mengembangkan proyek ini dengan mengubah:

* HTML → `templates/index.html`
* CSS → `static/style.css`
* JavaScript → `static/script.js`
* Logika aplikasi → `app.py`
