<div align="center">

# 🥷 AI Ninja Challenge

### *Train Your AI, Become the Ninja!*

**A webcam-powered ninja reflex game** — your body is the controller. React to on-screen challenges by striking ⚔️ attack, raising 🛡️ defense, or dodging 💨 with real-time pose recognition. Built with **Machine Learning** on the browser — no downloads, no installs, just you, your webcam, and your reflexes.

[![Version](https://img.shields.io/badge/version-1.0.0-green?style=for-the-badge&logo=github)](https://github.com/KiandrAHD/ai-ninja-challenge)
[![License](https://img.shields.io/github/license/KiandrAHD/ai-ninja-challenge?style=for-the-badge&logo=open-source-initiative)](LICENSE)
[![GitHub Issues](https://img.shields.io/github/issues/KiandrAHD/ai-ninja-challenge?style=for-the-badge&logo=github)](https://github.com/KiandrAHD/ai-ninja-challenge/issues)
[![GitHub Stars](https://img.shields.io/github/stars/KiandrAHD/ai-ninja-challenge?style=for-the-badge&logo=github&logoColor=gold&color=gold)](https://github.com/KiandrAHD/ai-ninja-challenge/stargazers)
[![Made with](https://img.shields.io/badge/Made%20with-TensorFlow.js-orange?style=for-the-badge&logo=tensorflow)](https://www.tensorflow.org/js)

[🌐 EN](#-english) ・ 🇮🇩 [ID](#-bahasa-indonesia)

---

</div>
## 🌐 English

> *Switch Language: ・ 🌐 English ・ 🇮🇩 [Bahasa Indonesia](#-bahasa-indonesia)*

---

### 🎯 Overview

🎮 **AI Ninja Challenge** is a browser game where **Machine Learning turns your webcam into a controller**. A custom-trained **Teachable Machine pose model** (running on **TensorFlow.js + PoseNet**) watches your body in real time and detects 4 poses: **STAND, ATTACK, DEFEND, DODGE**.

The screen throws rapid ninja challenges at you — strike ⚔️, block 🛡️, or roll 💨. Beat the timer, climb from **Rookie** to **Master Ninja**, and take down the **Final Boss** 👹 to claim victory.

**The motivation?** No controllers, no keyboards, no mice — just your body moving as the interface. It's a fun blend of **machine learning**, **reaction-speed training**, and old-school **arcade challenge**.

---

### ✨ Key Features

- 🤖 **Real-Time AI Pose Recognition** — pose detection & classification in the browser via Teachable Machine Pose + PoseNet.
- 🧠 **Confidence Threshold System** — a pose only counts if the AI is at least **70% confident**.
- 🏮 **3 Progression Levels** — Rookie → Apprentice → Master Ninja, each with a shorter timer.
- 👹 **Final Boss Phase** — survive a 5-pose gauntlet to unlock the victory screen.
- 🏆 **Score, Combo & HP System** — combo bonuses every 3rd correct hit; hearts are lost on failure.
- 🖥️ **Responsive Visual Interface** — dark ninja-themed UI that adapts to mobile & desktop.
- 🎯 **No Installation** — everything runs from a modern web browser with a webcam.

---

### 🧰 Tech Stack & Prerequisites

| Layer | Technology |
|-------|------------|
| Language | Vanilla **JavaScript (ES6)** + HTML5 + CSS3 |
| ML Runtime | **[TensorFlow.js 1.3.1]** (CDN) |
| Pose Model | **[Teachable Machine Pose 0.8.6]** (CDN) with PoseNet / MobileNetV1 backend |
| Model Files | Custom trained `my-pose-model` (`model.json`, `metadata.json`, `weights.bin`) |
| Dev Server | VS Code **Live Server** (port 5501) or any static server |
| Model Classes | `STAND`, `ATTACK`, `DEFEND`, `DODGE` |

**Prerequisites:**

- 🖥️ A modern browser with **webcam access** (Chrome, Edge, or Firefox).
- 🐍 (Optional) Python 3 for the alternative static-server command.
- 📦 No `npm` packages required — dependencies load via CDN.

---

### 🕹️ How to Play / Controls

| In-Game Element | What It Does | Your Move |
|----------------|--------------|-----------|
| ⚔️ **ATTACK!** | Your ninja must strike | Throw a fast punch / striking pose |
| 🛡️ **DEFEND!** | Block the incoming blow | Raise your arms into a guard/block pose |
| 💨 **DODGE!** | Evade the attack | Perform a rolling / dodging motion |
| 🕒 **Timer** | Counts down per challenge | Act quickly before time runs out |
| 💗 **HP** | 3 hearts — lose to failure | Don't let them hit 0 |
| 🔥 **COMBO** | Bonus on every 3rd hit | Chain correct poses in a row |
| 👹 **Boss Message** | Final Boss sequence | Complete the boss choreography in order |
| 🥷 **START Button** | Begin / restart the game | Click to start, or restart after game over |

**Scoring Table**

| Action | Points |
|--------|--------|
| Correct pose (Level 1–2 / ROOKIE & APPRENTICE) | +10 |
| Correct pose (Level 3 / Master & Boss) | +20 |
| Combo bonus (every 3rd correct) | +10 |

```
Game Flow: 3-2-1 FIGHT! → Random Pose Challenge → Match Your Pose → Score / Combo / Level Up → Final Boss Level → Victory 🏆 (or Game Over 💀)
```

---

### 🚀 Installation & Getting Started

Clone the repository:

```bash
git clone https://github.com/KiandrAHD/ai-ninja-challenge.git
cd ai-ninja-challenge
```

**Option A — VS Code Live Server (recommended, port 5501):**

```bash
# 1. Open the folder in VS Code
code .

# 2. Right-click index.html → "Open with Live Server" (bundled to port 5501)
# 3. Allow camera / webcam access when prompted
# 4. Click 🥷 START CHALLENGE
```

**Option B — any static server** (e.g., Python):

```bash
# From the project root:
python -m http.server 5500

# Then open in your browser:
# http://localhost:5500
```

> ⚠️ **Note:** Do **not** open `index.html` directly (as a `file://` path). The model and webcam need an HTTP server to run correctly.

**Customize the model:** Train your own pose classes in [Teachable Machine](https://teachablemachine.withgoogle.com/), and drop the exported `model.json`, `weights.bin` & `metadata.json` into `my-pose-model/`.

---

### 📂 Project Structure

```
ai-ninja-challenge/
│
├── index.html                # Main game page & UI layout (status bar, arena, webcam)
├── style.css                 # Dark ninja theme, responsive styling & animations
├── script.js                 # Game logic: pose detection, timer, score, combo, boss
│
├── my-pose-model/            # Custom-trained Teachable Machine Pose model
│   ├── model.json            # Model architecture (PoseNet / MobileNetV1 config)
│   ├── weights.bin           # Trained model weights
│   └── metadata.json         # Classes & settings (STAND / ATTACK / DEFEND / DODGE)
│
└── .vscode/
    └── settings.json         # Live Server port config (5501)
```

---

### 🤝 Contributing & 📋 License

Contributions are welcome! Fork the repo → create a branch → open a Pull Request to `main`.

Please give ⭐️ if you find this fun! 

**License:** Distributed under the **MIT License**. See the [LICENSE](LICENSE) file for full details — or the Bahasa Indonesia section below for the summary.

**Author** 👤 **KiandrAHD** — [https://github.com/KiandrAHD](https://github.com/KiandrAHD)

---

> Made with ❤️, ☕ and 🤖 by [KiandrAHD](https://github.com/KiandrAHD)

---

# 🇮🇩 Bahasa Indonesia

> *Ganti Bahasa: ・ 🌐 [English](#-english) ・ 🇮🇩 Bahasa Indonesia*

---

### 🎯 Ringkasan / Konsep

🎮 **AI Ninja Challenge** adalah sebuah game berbasis **web browser** di mana **Machine Learning mengubah webcam kamu menjadi kontroler**. Model pose **Teachable Machine** hasil latihan kamu (berjalan di atas **TensorFlow.js + PoseNet**) mengamati tubuh kamu secara langsung dan mendeteksi 4 pose: **STAND, ATTACK, DEFEND, DODGE**.

Layar akan terus-menerus memberi tantangan ninja — serang ⚔️, bertahan 🛡️, atau menghindar 💨. Kalahkan timer, naik dari level **Rookie** sampai **Master Ninja**, lalu kalahkan **Final Boss** 👹 untuk meraih kemenangan.

**Motivasinya?** Tanpa joystick, tanpa keyboard, tanpa mouse — hanya tubuh kamu yang bergerak sebagai pengontrolnya. Ini perpaduan seru antara **machine learning**, **latihan kecepatan refleks**, dan **tantangan arcade** klasik.

---

### ✨ Fitur Utama

- 🤖 **Deteksi Pose AI Real-Time** — deteksi & klasifikasi gerakan di browser via Teachable Machine Pose + PoseNet.
- 🧠 **Sistem Ambang Confidence** — sebuah pose hanya dihitung jika AI yakin minimal **70%**.
- 🏮 **3 Level Progresi** — Rookie → Apprentice → Master Ninja, setiap level mengeluarkan waktu geng yang semakin cepat.
- 👹 **Fase Final Boss** — bertahan dari 5 tantangan beruntun untuk membuka layar kemenangan.
- 🏆 **Sistem Skor, Combo & HP** — bonus combo setiap hit benar ke-3; nyawa (❤️) berkurang bila gagal.
- 🖥️ **Tampilan Visual Responsif** — tema ninja gelap yang menyesuaikan untuk ponsel & desktop.
- 🎯 **Tanpa Instalasi** — semua berjalan dari browser modern + webcam.

---

### 🧰 Tech Stack & Prasyarat

| Lapisan | Teknologi |
|---------|-----------|
| Bahasa | **JavaScript (ES6) vanilla** + HTML5 + CSS3 |
| Runtime ML | **[TensorFlow.js 1.3.1]** (via CDN) |
| Model Pose | **[Teachable Machine Pose 0.8.6]** (via CDN) dengan backend PoseNet / MobileNetV1 |
| File Model | Model latihan khusus `my-pose-model` (`model.json`, `metadata.json`, `weights.bin`) |
| Server Dev | VS Code **Live Server** (port 5501) atau server statis lain |
| Kelas Model | `STAND`, `ATTACK`, `DEFEND`, `DODGE` |

**Prasyarat:**

- 🖥️ Browser modern dengan **akses webcam** (Chrome, Edge, atau Firefox).
- 🐍 (Opsional) Python 3 untuk perintah server statis alternatif.
- 📦 Tidak ada paket `npm` yang diperlukan — dependensi dimuat dari CDN.

---

### 🕹️ Cara Bermain / Kontrol

| Elemen | Apa yang Terjadi | Gerakan Kamu |
|--------|------------------|--------------|
| ⚔️ **ATTACK!** | Ninja kamu harus menyerang | Lakukan gerakan pukulan / serangan cepat |
| 🛡️ **DEFEND!** | Blokir serangan yang datang | Angkat tangan ke posisi bertahan / menangkis |
| 💨 **DODGE!** | Hindari serangan | Lakukan gerakan mengelak / berguling |
| 🕒 **Timer** | Waktu berjalan mundur per tantangan | Bergerak cepat sebelum waktu habis |
| 💗 **HP** | 3 nyawa — hilang bila gagal | Jangan sampai nyawa habis |
| 🔥 **COMBO** | Bonus setiap hit benar ke-3 | Rantai pose benar secara berurutan |
| 👹 **Pesan Boss** | Sinyal urutan Final Boss | Ikuti urutan tantangan boss dengan benar |
| 🥷 **Tombol MULAI** | Mulai / mulai ulang permainan | Klik untuk mulai, atau mulai ulang setelah game over |

**Tabel Skor**

| Aksi | Poin |
|------|------|
| Pose benar (Level 1–2 / ROOKIE & APPRENTICE) | +10 |
| Pose benar (Level 3 / MASTER & BOSS) | +20 |
| Bonus combo (setiap jawaban benar ke-3) | +10 |

```
Alur Game: Hitung mundur 3-2-1 FIGHT! → Tantangan Pose Acak → Cocokkan Posenya → Skor / Combo / Naik Level → Level Final Boss → Menang 🏆 (atau Game Over 💀)
```

---

### 🚀 Instalasi & Cara Menjalankan

Clone repositori:

```bash
git clone https://github.com/KiandrAHD/ai-ninja-challenge.git
cd ai-ninja-challenge
```

**Opsi A — VS Code Live Server (disarankan, port 5501):**

```bash
# 1. Buka folder di VS Code
code .

# 2. Klik kanan index.html → "Open with Live Server" (otomatis port 5501)
# 3. Izinkan akses webcam / kamera saat diminta
# 4. Klik 🥷 MULAI TANTANGAN
```

**Opsi B — server statis apa pun** (contoh menggunakan Python)

```bash
# Di root folder project:
python -m http.server 5500

# Kemudian buka dalam browser:
# http://localhost:5500
```

> ⚠️ **Catatan penting:** Jangan membuka langsung `index.html` (`file://`). Model dan webcam butuh sarana web (HTTP server) agar berfungsi dengan benar.

**Kustomisasi model:** Latih pose kamu sendiri di [Teachable Machine](https://teachablemachine.withgoogle.com/), lalu letakkan `model.json`, `weights.bin` dan `metadata.json` yang diekspor ke dalam `my-pose-model/`.

---

### 📂 Struktur Projek

```
ai-ninja-challenge/
│
├── index.html                # Halaman utama game & tata letak UI (status bar, arena, kamera)
├── style.css                 # Tema ninja gelap, styling responsif & animasi
├── script.js                 # Logika game: deteksi pose, timer, skor, combo, boss
│
├── my-pose-model/            # Model Teachable Machine (hasil latihan khusus)
│   ├── model.json            # Arsitektur model (konfigurasi PoseNet / MobileNetV1)
│   ├── weights.bin           # Bobot model yang telah dilatih
│   └── metadata.json         # Kelas & pengaturan (STAND / ATTACK / DEFEND / DODGE)
│
└── .vscode/
    └── settings.json         # Konfigurasi port Live Server (5501)
```

---

### 🤝 Kontribusi & 📋 Ketentuan

Kontribusi sangat kami terbuka lebar-luasnya! Fork repositori → buat branch → kirim Pull Request ke branch `main`.

Jangan lupa memberi ⭐️ jika kamu menyukai project ini!

**Lisensi:** Didistribusikan di bawah **Lisensi MIT**. Silakan lihat berkas [LICENSE](LICENSE) untuk syarat-syarat selengkapnya.

**Penulis** 👤 **KiandrAHD** — [https://github.com/KiandrAHD](https://github.com/KiandrAHD)

---

> Dibuat dengan senyum, kopi, dan 🤖 oleh [KiandrAHD](https://github.com/KiandrAHD)