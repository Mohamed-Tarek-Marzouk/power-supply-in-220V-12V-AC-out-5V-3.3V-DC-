# ⚡ Universal Dual-Input Power Supply (5V / 3.3V)

![Project Type](https://img.shields.io/badge/Project-Power_Supply-red)
![Output](https://img.shields.io/badge/Output-5V_/_3.3V-blue)
![Input](https://img.shields.io/badge/Input-220V_AC_/_12V_AC_DC-orange)

## 📌 Overview
This project is a versatile **Universal Power Supply Circuit** designed to provide a stable DC output from various input sources. It can be powered by either high-voltage **220V AC** or low-voltage **12V (AC or DC)**, making it an ideal "all-in-one" power solution for electronics labs and embedded systems.

---

## 🧩 Key Features

* **Dual Input Support:** Accepts 220V AC (Mains) or 12V (AC/DC).
* **Selectable Output:** Regulated 5V or 3.3V DC via an output selector socket.
* **Dual-Mode Switching:** Manual toggle switch to select between AC and DC input paths.
* **Robust Protection:** Includes reverse polarity protection and bridge rectification.
* **Status Indicator:** On-board LED for power-on confirmation.

---

## 🔌 Circuit Components

| Category | Component | Description |
| :--- | :--- | :--- |
| **AC-DC Converter** | **HLK-PM12** | High-efficiency module to convert 220V AC to 12V DC. |
| **Rectification** | **Bridge Rectifier** | Converts 12V AC input into usable DC. |
| **Regulation (5V)** | **7805 IC** | Linear regulator for stable 5V output. |
| **Regulation (3.3V)** | **LM1117 / 7833** | Linear regulator for stable 3.3V output. |
| **Filtration** | **Electrolytic Caps** | Large capacitors for smoothing and ripple reduction. |
| **Protection** | **Diodes** | Prevents damage from reverse polarity on the 12V DC input. |
| **Selection** | **Jumper/Socket** | Allows user to toggle between 3.3V and 5V outputs. |



---

## ⚙️ How It Works

### 1. Input Stage
* **220V AC Mode:** The signal passes through the **HLK-PM12** isolation module, safely stepping it down to 12V DC.
* **12V Mode:**
    * **If AC:** It passes through the **Bridge Rectifier**.
    * **If DC:** It flows through protection diodes to prevent circuit failure if the leads are swapped.

### 2. Stabilization & Regulation
The raw 12V DC is filtered by electrolytic capacitors to remove noise. It then feeds into the **7805** and **7833** regulators.

### 3. Output Selection
The user can choose the desired logic level (5V for Arduino/Atmega or 3.3V for ESP8266/STM32) using the output selector socket.

---

## 🛠 Use Cases
* **Microcontrollers:** Powering Arduino, ESP8266, ESP32, or STM32 boards.
* **Breadboard Power:** A reliable source for prototyping various circuits.
* **DIY Projects:** Any application requiring a clean 5V or 3.3V rail from available wall adapters or mains.

---

## ⚠️ Safety Warnings

> [!WARNING]
> **HIGH VOLTAGE:** DO NOT touch any part of the board while it is connected to 220V AC. Ensure the AC section is properly insulated or housed in an enclosure.

* **Mode Switching:** Always verify your input source voltage before toggling the power mode switch.
* **Heat Dissipation:** If drawing high current, the linear regulators (7805/7833) will generate heat. Use a **heatsink** if necessary.

---

## 📝 Design Notes
The inclusion of the **HLK-PM12** provides a compact and isolated way to handle mains power, significantly reducing the footprint compared to traditional transformers.
