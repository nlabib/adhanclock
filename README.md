🕌 Adhan Clock (Raspberry Pi)

A cost-friendly, open-source Adhan Clock built with a Raspberry Pi.
It automatically fetches daily prayer times from the internet, plays the Adhan through a speaker, and provides a web-based control panel (mobile-friendly) built with React.

Designed to be:

Simple to build

Easy to customize

Well-documented

Reproducible for anyone

✨ Features

📡 Automatically fetches daily prayer times from the internet

🕰️ Accurate scheduling for all five daily prayers

🔊 Plays Adhan audio through a speaker

🌍 Configurable location, calculation method, and madhab

🌐 Local web dashboard (works on phone, tablet, or PC)

🎚️ Volume control and test playback

📴 Works offline using cached prayer times

🔁 Runs automatically on boot (systemd)

💸 Designed to be low-cost

🧱 Hardware Requirements (Cost-Friendly)

Minimum recommended setup:

Raspberry Pi Zero 2 W (or Pi 3 / Pi 4)

16–32GB microSD card

USB speaker (simplest option)

Power supply

Internet connection (Wi-Fi)

Optional upgrades:

RTC module (DS3231) for better offline accuracy

Small OLED/LCD screen for a physical clock display

🧠 How It Works (High Level)

The Raspberry Pi fetches daily prayer times based on your location

Prayer times are cached locally

A background scheduler monitors the current time

When a prayer time is reached:

The Adhan audio is played through the speaker

A local web server exposes a control panel to:

Change settings

View prayer times

Test audio

Enable/disable prayers

🧩 Tech Stack
Backend

Python

FastAPI (REST API)

systemd (background services)

Local JSON configuration

Frontend

React (TypeScript)

Mobile-friendly web UI

Served locally from the Raspberry Pi

Audio

Local MP3/WAV Adhan files

Played using system audio utilities

📁 Project Structure
adhan-clock/
├── backend/
│   ├── app/
│   │   ├── main.py           # FastAPI server
│   │   ├── prayer_times.py   # Fetch & cache prayer times
│   │   ├── scheduler.py      # Adhan scheduling logic
│   │   ├── audio.py          # Audio playback helpers
│   │   └── config.py         # Load/save configuration
│   ├── requirements.txt
│   └── systemd/
│       ├── adhan-backend.service
│       └── adhan-scheduler.service
│
├── frontend/
│   ├── src/
│   ├── package.json
│   └── vite.config.ts
│
├── audio/
│   ├── adhan1.mp3
│   └── adhan2.mp3
│
├── scripts/
│   ├── install.sh
│   └── enable_services.sh
│
├── docs/
│   ├── setup.md
│   └── troubleshooting.md
│
├── README.md
└── LICENSE

⚙️ Installation (Planned)

Full step-by-step instructions will be provided in docs/setup.md

High-level steps:

Flash Raspberry Pi OS (Lite recommended)

Clone this repository

Run the install script

Configure location and prayer settings

Access the dashboard from your phone or browser

git clone https://github.com/yourusername/adhan-clock.git
cd adhan-clock
./scripts/install.sh

🌐 Web Dashboard

Once running, the dashboard will be available at:

http://adhanclock.local


(or via the Pi’s local IP address)

Dashboard Features

View today’s prayer times

See next prayer countdown

Change location and calculation method

Enable/disable individual prayers

Adjust volume

Play test Adhan

📍 Configuration Options

City or latitude/longitude

Calculation method (MWL, ISNA, Egypt, Umm al-Qura, etc.)

Madhab (Hanafi / Shafi)

Adhan audio selection

Volume level

Prayer enable/disable toggles

All settings are stored in a local JSON config file.

🔒 Security

Designed for local network use

No external exposure by default

Authentication can be added if remote access is needed

🛠️ Roadmap

 Physical display support

 Multiple Adhan profiles

 Offline calculation fallback

 React Native / mobile wrapper

 Docker support

 Multi-device sync

🤝 Contributing

Contributions are welcome.

You can help by:

Improving documentation

Adding features

Testing on different Raspberry Pi models

Submitting bug reports

Please open an issue or submit a pull request.

📜 License

This project is open-source under the MIT License.
You are free to use, modify, and distribute it.

🕌 Purpose

This project is built to make Adhan accessible, affordable, and customizable for homes, mosques, and communities—without relying on proprietary hardware or expensive solutions.
