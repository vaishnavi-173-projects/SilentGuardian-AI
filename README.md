<div align="center">

```
 ██████╗ ███╗   ██╗██╗     ██╗███╗   ██╗███████╗
██╔═══██╗████╗  ██║██║     ██║████╗  ██║██╔════╝
██║   ██║██╔██╗ ██║██║     ██║██╔██╗ ██║█████╗  
██║   ██║██║╚██╗██║██║     ██║██║╚██╗██║██╔══╝  
╚██████╔╝██║ ╚████║███████╗██║██║ ╚████║███████╗
 ╚═════╝ ╚═╝  ╚═══╝╚══════╝╚═╝╚═╝  ╚═══╝╚══════╝
      █████╗ ████████╗████████╗ █████╗  ██████╗██╗  ██╗
    ██╔══██╗╚══██╔══╝╚══██╔══╝██╔══██╗██╔════╝██║ ██╔╝
    ███████║   ██║      ██║   ███████║██║     █████╔╝ 
    ██╔══██║   ██║      ██║   ██╔══██║██║     ██╔═██╗ 
    ██║  ██║   ██║      ██║   ██║  ██║╚██████╗██║  ██╗
    ╚═╝  ╚═╝   ╚═╝      ╚═╝   ╚═╝  ╚═╝ ╚═════╝╚═╝  ╚═╝
          ██████╗ ███████╗████████╗███████╗ ██████╗████████╗ ██████╗ ██████╗ 
          ██╔══██╗██╔════╝╚══██╔══╝██╔════╝██╔════╝╚══██╔══╝██╔═══██╗██╔══██╗
          ██║  ██║█████╗     ██║   █████╗  ██║        ██║   ██║   ██║██████╔╝
          ██║  ██║██╔══╝     ██║   ██╔══╝  ██║        ██║   ██║   ██║██╔══██╗
          ██████╔╝███████╗   ██║   ███████╗╚██████╗   ██║   ╚██████╔╝██║  ██║
          ╚═════╝ ╚══════╝   ╚═╝   ╚══════╝ ╚═════╝   ╚═╝    ╚═════╝ ╚═╝  ╚═╝
```

### **Real-Time AI-Powered Network Intrusion Detection & Prevention System**

---

![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-2.x-000000?style=for-the-badge&logo=flask&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--Learn-ML_Core-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Scapy](https://img.shields.io/badge/Scapy-Packet_Engine-1572B6?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-22c55e?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-ef4444?style=for-the-badge)

> *"The best defense is a system that doesn't wait — it watches, thinks, and acts."*

</div>

---

## ⚡ What Is This?

**Online Attack Detector** is a fully autonomous, AI-powered network security system that runs on your local machine. It doesn't just *log* threats — it *stops* them.

Built for cybersecurity learners, developers, and enthusiasts, this system captures raw network traffic, transforms it into structured flows, classifies behavior with a trained machine learning model, and automatically responds — all in real time, with zero enterprise hardware required.

```
CAPTURE → ANALYZE → CLASSIFY → RESPOND
  Live      Flows     AI Model    Block + Alert
```

---

## 🗺️ System Architecture

```
┌──────────────────────────────────────────────────────────────────────┐
│                         NETWORK INTERFACE                           │
│                     (Your Machine's NIC)                            │
└─────────────────────────────┬────────────────────────────────────────┘
                              │  Raw Packets (TCP / UDP / ICMP)
                              ▼
┌─────────────────────────────────────────────────────────────────────┐
│                        PACKET SNIFFER                               │
│                    [ Scapy Engine ]                                  │
│      Captures every packet passing through the interface            │
└─────────────────────────────┬───────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────────┐
│                        FLOW PROCESSOR                               │
│          Groups packets → Structured network flows                  │
│    (IP pairs, port pairs, protocol, timing, byte count, flags)      │
└─────────────────────────────┬───────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────────┐
│                     FEATURE EXTRACTOR                               │
│    Derives statistical & behavioral features from each flow         │
│    (packet rate, byte distribution, flow duration, flag ratios)     │
└─────────────────────────────┬───────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────────┐
│                   ML CLASSIFICATION ENGINE                          │
│              [ Random Forest — Scikit-learn ]                       │
│         Served via Flask REST API (ml_api.py)                       │
│                                                                     │
│      BENIGN ────────────────────────────────────► LOG               │
│      MALICIOUS ─────────────────────────────────► RESPOND           │
└────────────────────┬──────────────────┬────────────────────────────┘
                     │                  │
          ┌──────────┘                  └──────────┐
          ▼                                        ▼
┌─────────────────────┐               ┌────────────────────────────┐
│   REAL-TIME         │               │   PREVENTION ENGINE        │
│   DASHBOARD         │               │                            │
│  [ Flask-SocketIO ] │               │  • Firewall IP Block       │
│  [ Plotly Charts ]  │               │  • Telegram Instant Alert  │
│  Live traffic feed  │               │  • SQLite Alert Storage    │
│  Threat map         │               │  • TICE Threat Intelligence│
└─────────────────────┘               └────────────────────────────┘
```

---

## 🧰 Full Tech Stack

| Layer | Technology | Purpose |
|---|---|---|
| **Packet Capture** | Scapy | Live sniffing of raw network packets |
| **Flow Engine** | Custom Python | Converts packets → structured flows |
| **ML Model** | Scikit-learn (Random Forest) | Binary/multi-class attack classification |
| **Backend API** | Flask | Serves ML predictions via REST |
| **Real-Time Comms** | Flask-SocketIO | WebSocket-based live dashboard updates |
| **Frontend** | HTML5 + CSS3 + JavaScript | Interactive dashboard UI |
| **Data Visualization** | Plotly | Live traffic charts and analytics |
| **Alert Storage** | SQLite | Persistent threat log database |
| **Notifications** | Telegram Bot API | Instant push alerts to your phone |
| **Threat Intelligence** | AbuseIPDB + VirusTotal + IPinfo | Multi-source IP reputation scoring |
| **Optional UI** | Streamlit | TICE threat intelligence console |

---

## 🛡️ Core Features

| Feature | What It Does |
|---|---|
| **Live Packet Capture** | Intercepts TCP, UDP, and ICMP traffic in real time via Scapy |
| **Flow Processing** | Aggregates raw packets into meaningful, analyzable network flows |
| **AI Classification** | Random Forest model predicts whether each flow is benign or an attack |
| **Auto IP Blocking** | Instantly pushes malicious IPs to your OS firewall — no manual action needed |
| **Live Dashboard** | Real-time traffic visualization with threat feed and flow statistics |
| **Telegram Alerts** | Sends a notification to your phone the moment a threat is detected |
| **TICE Engine** | Multi-source threat intelligence: abuse score, geolocation, reputation data |
| **Alert History** | All detections stored in SQLite for post-analysis and reporting |

---

## 🚀 Installation

### Prerequisites

- Python **3.9+**
- **Admin / root** privileges (required for packet capture)
- A Telegram Bot token (optional, for alerts)
- API keys for AbuseIPDB and VirusTotal (optional, for TICE)

### Step 1 — Clone the Repository

```bash
git clone https://github.com/your-username/online-attack-detector.git
cd online-attack-detector
```

### Step 2 — Create a Virtual Environment

```bash
# Create venv
python -m venv .venv

# Activate — Windows
.\.venv\Scripts\activate

# Activate — Linux / macOS
source .venv/bin/activate
```

### Step 3 — Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4 — Configure Environment Variables

Create a `.env` file in the project root:

```env
TELEGRAM_BOT_TOKEN=your_telegram_bot_token
TELEGRAM_CHAT_ID=your_chat_id
ABUSEIPDB_API_KEY=your_abuseipdb_key
VIRUSTOTAL_API_KEY=your_virustotal_key
IPINFO_TOKEN=your_ipinfo_token
```

> ⚠️ **Never commit your `.env` file.** It's already in `.gitignore` — keep it there.

---

## ▶️ Running the System

The system has three independent components. Run each in a **separate terminal**.

### Terminal 1 — Start the ML API

```bash
python ml_api.py
```

> Starts the Flask REST API that serves ML predictions. Must be running before the sniffer.

### Terminal 2 — Start the Dashboard

```bash
python app.py
```

> Launches the real-time web dashboard. Open your browser at `http://localhost:5000`

### Terminal 3 — Start the Packet Sniffer (Admin Required)

```bash
# Linux / macOS
sudo python flow_sniffer.py

# Windows (run terminal as Administrator)
python flow_sniffer.py
```

> Begins capturing live network traffic and feeding it to the ML engine.

### Optional — Launch the TICE Intelligence Console

```bash
streamlit run tice_app_ui.py
```

> Opens the Threat Intelligence & Contextual Engine UI at `http://localhost:8501`

---

## 🔬 End-to-End Workflow

```
 ┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐
 │ Packets  │───►│  Flows   │───►│ Features │───►│ ML Model │───►│Dashboard │───►│  Action  │
 │  (raw)   │    │(grouped) │    │(derived) │    │(predict) │    │ (live)   │    │(block/  │
 └──────────┘    └──────────┘    └──────────┘    └──────────┘    └──────────┘    │  alert) │
                                                                                  └──────────┘
```

| Step | Component | Description |
|---|---|---|
| **1. Capture** | `flow_sniffer.py` | Sniffs all packets on the network interface |
| **2. Aggregate** | Flow Processor | Groups packets into time-windowed flows |
| **3. Extract** | Feature Engine | Computes 80+ statistical features per flow |
| **4. Classify** | `ml_api.py` | Random Forest returns benign / attack label |
| **5. Display** | `app.py` | Dashboard updates via WebSocket in < 1 second |
| **6. Act** | Prevention Engine | Blocks IP via firewall + sends Telegram alert |

---

## 🔒 Security & Operational Notes

| ⚠️ | Note |
|---|---|
| 🔑 | **Never commit `.env` or API keys** to version control |
| 🛡️ | Requires **admin/root** privileges for raw packet capture |
| 🖥️ | Designed and tested for **local / lab environments** |
| 🔄 | **Rotate API keys** regularly and revoke unused ones |
| 📵 | Do **not** deploy on production networks without proper authorization |
| 📋 | Always ensure you have **legal permission** to monitor any network |

---

## 🤝 Contributing

Contributions are warmly welcome. Here are some areas to explore:

- 🧠 **Better Models** — Try XGBoost, LightGBM, or neural networks for higher accuracy
- 📊 **More Datasets** — Train on CIC-IDS2018, UNSW-NB15, or custom captures
- 🔔 **New Channels** — Add Discord, Slack, or email alert integrations
- 🗺️ **Enhanced Dashboard** — Geo-IP maps, anomaly timelines, export reports
- 🧪 **Unit Tests** — Improve test coverage across all modules
- 📦 **Docker Support** — Containerize for easier deployment

```bash
# Standard contribution flow
git checkout -b feature/your-feature-name
git commit -m "feat: describe your change clearly"
git push origin feature/your-feature-name
# → Open a Pull Request
```

---

## 📁 Project Structure

```
online-attack-detector/
│
├── app.py                  # Main Flask dashboard app
├── ml_api.py               # Flask REST API for ML predictions
├── flow_sniffer.py         # Packet capture & flow processor
├── tice_app_ui.py          # Streamlit threat intelligence console
│
├── models/
│   └── random_forest.pkl   # Trained ML model
│
├── static/                 # CSS, JS, frontend assets
├── templates/              # HTML dashboard templates
│
├── database/
│   └── alerts.db           # SQLite alert log
│
├── requirements.txt        # Python dependencies
├── .env                    # 🔒 Your secrets (never commit this)
├── .gitignore
└── README.md
```

---

## 📝 License

```
MIT License — Free to use, modify, and distribute with attribution.
See LICENSE for full terms.
```

---

<div align="center">

## 🙌 Built For

**Students · Developers · Cybersecurity Enthusiasts**

*Exploring real-time network defense using the power of AI.*

---

```
  ██████╗ ███████╗███████╗███████╗███╗   ██╗██████╗ ███████╗██████╗ 
  ██╔══██╗██╔════╝██╔════╝██╔════╝████╗  ██║██╔══██╗██╔════╝██╔══██╗
  ██║  ██║█████╗  █████╗  █████╗  ██╔██╗ ██║██║  ██║█████╗  ██║  ██║
  ██║  ██║██╔══╝  ██╔══╝  ██╔══╝  ██║╚██╗██║██║  ██║██╔══╝  ██║  ██║
  ██████╔╝███████╗██║     ███████╗██║ ╚████║██████╔╝███████╗██████╔╝
  ╚═════╝ ╚══════╝╚═╝     ╚══════╝╚═╝  ╚═══╝╚═════╝ ╚══════╝╚═════╝ 
```

*The network doesn't sleep. Neither does this.*

⭐ **Star this repo if it helped you!** ⭐

</div>
