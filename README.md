# 📡 The Auditor: Frugal Wireless Security at the Edge

![Status-Research Prototype](https://img.shields.io/badge/Status-Research%20Prototype-blue)
![Platform-ESP32-S3](https://img.shields.io/badge/Platform-ESP32--S3-green)
![License-MIT](https://img.shields.io/badge/License-MIT-orange)

> **"Breaking the Air: Auditing Africa's Wireless Infrastructure at the Edge"**
> *Presented at the African Deep Tech Conference 2026*

---

## 📖 Overview
**The Auditor** is a low-cost, open-source hardware tool designed to audit legacy wireless protocols in resource-constrained environments. Built on the "Frugal Engineering" philosophy, it empowers local engineers to test for **Sub-GHz Replay** and **NFC Cloning** vulnerabilities without requiring expensive imported equipment (like SDRs or Proxmark3s).

This repository hosts the firmware, wiring schematics, and research data for the project.

---

## ⚡ Key Capabilities
* **Sub-GHz Interception (433MHz):** Captures and analyzes unencrypted "Fixed Code" signals from automated gates, smart sockets, and logistics trackers.
* **NFC Auditing (13.56MHz):** Reads and identifies insecure Mifare Classic sectors and UID metadata.
* **Standalone Operation:** Features an onboard OLED display for field analysis—no laptop required.
* **Frugal Design:** Total Build of Materials (BOM) cost is under **$30 USD**.

---

## 🛠️ Hardware Architecture (Bill of Materials)
The system is built on widely available, modular components:

| Component | Function | Status |
| :--- | :--- | :--- |
| **ESP32-S3** | Main Controller (Logic & UI) | ✅ Verified |
| **CC1101** | Sub-GHz Transceiver (433MHz) | ✅ Verified |
| **PN532 (V3)** | NFC/HF RFID Reader & Writer | ✅ Verified |
| **1.3" OLED** | I2C Display (SH1106/SSD1306) | ✅ Verified |

*(Detailed wiring diagrams and Pinout tables are available in the `/docs` folder).*

---

## 📸 Research Poster
You can view the full academic poster presented at the African Deep Tech Conference here:
👉 **[Download High-Res PDF](#)**

---

## ⚠️ Legal & Ethical Disclaimer
**This tool is for educational purposes and authorized security auditing only.**
The developers of this project are not responsible for any misuse of this hardware.
* Always obtain written permission before auditing any infrastructure.
* Testing on systems you do not own or have explicit authorization to test is illegal.

---

## 📅 Roadmap
- [x] Proof of Concept (POC) Hardware Build
- [x] Basic 433MHz Signal Capture
- [x] Mifare Classic UID Reading
- [ ] **Public Firmware Release (v1.0)** - *Coming March 2026*
- [ ] Bluetooth Low Energy (BLE) Scanner Module

---

## 👤 Author
**Olaoluwa Aina Joshua**
* **Role:** Independent Offensive Security Researcher
* **Twitter/X:** [@zoecyber001](https://twitter.com/zoecyber001)
* **Contact:** olaoluwaa905@gmail.com

---
*Built with ❤️ for Sovereign Security in Africa.*