# Adhan Clock (Raspberry Pi)

A low-cost, open-source **Adhan Clock** built with a Raspberry Pi.  
It automatically fetches daily prayer times, plays the Adhan through a speaker, and exposes a local web dashboard (React) for configuration and control.

---

## Features

- Automatic daily prayer time fetching
- Accurate Adhan scheduling (Fajr–Isha)
- Local Adhan audio playback
- Web-based control panel (mobile friendly)
- Configurable location, calculation method, and madhab
- Enable/disable individual prayers
- Volume control and test playback
- Offline support via cached prayer times
- Runs automatically on boot (systemd)
- Designed to be inexpensive and easy to replicate

---

## Hardware Requirements

Minimum recommended setup:

- Raspberry Pi Zero 2 W (or Pi 3 / Pi 4)
- 16–32GB microSD card
- USB speaker (plug-and-play)
- Internet connection (Wi-Fi)

Optional:
- RTC module (DS3231)
- Small OLED/LCD display

---

## Tech Stack

**Backend**
- Python
- FastAPI
- systemd

**Frontend**
- React (TypeScript)
- Local web dashboard

**Audio**
- Local MP3/WAV Adhan files

---

## Project Structure
adhan-clock/
├── backend/
│ ├── app/
│ │ ├── main.py # API server
│ │ ├── prayer_times.py # Prayer time fetching & caching
│ │ ├── scheduler.py # Adhan scheduling logic
│ │ ├── audio.py # Audio playback
│ │ └── config.py # Configuration handling
│ ├── requirements.txt
│ └── systemd/
│ ├── adhan-backend.service
│ └── adhan-scheduler.service
├── frontend/
├── audio/
├── scripts/
├── docs/
└── README.md

---

## Installation

Detailed setup instructions will be provided in `docs/setup.md`.

Planned installation flow:

```bash
git clone https://github.com/yourusername/adhan-clock.git
cd adhan-clock
./scripts/install.sh
Web Dashboard

After installation, access the dashboard from any device on the same network:

http://adhanclock.local


(or via the Raspberry Pi’s local IP address)

Dashboard Features

View today’s prayer times

Next prayer countdown

Change location and calculation method

Enable/disable prayers

Adjust volume

Test Adhan playback

Configuration

Supported configuration options:

City or latitude/longitude

Calculation method (MWL, ISNA, Egypt, Umm al-Qura, etc.)

Madhab (Hanafi / Shafi)

Adhan audio selection

Volume level

Prayer toggles

Configuration is stored locally in a JSON file.

Roadmap

 Physical display support

 Offline prayer time calculation

 Multiple Adhan profiles

 Docker support

 Mobile app wrapper (React Native / Capacitor)

Contributing

Contributions are welcome.

Please open an issue or submit a pull request for:

Bug fixes

Feature additions

Documentation improvements

License

MIT License

Purpose

This project aims to provide an open, affordable, and customizable Adhan Clock that anyone can build, modify, and improve without relying on proprietary hardware.

