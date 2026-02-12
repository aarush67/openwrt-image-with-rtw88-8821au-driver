# 📦 OpenWrt Image with rtw88-8821au Driver for Raspberry Pi 5

Prebuilt **OpenWrt firmware images** for **Raspberry Pi 5** with built-in support for the **Realtek rtw88 / RTL8821AU USB Wi-Fi driver**.

This repository exists to make compatible USB Wi-Fi adapters work **out of the box**, without requiring manual driver compilation.

---

## 📌 Overview

This repository provides:

- ✅ Prebuilt OpenWrt images for Raspberry Pi 5  
- ✅ Included kernel modules for **rtw88-8821au**  
- ✅ Package manifest & build metadata  
- ✅ Ready-to-flash firmware  

Perfect for experimentation, learning, portable routers, or custom network projects.

---

## 🗂️ Repository Contents

| File | Description |
|------|-------------|
| `*-factory.img.gz` | Flash this onto a blank SD card |
| `*-sysupgrade.img.gz` | Upgrade an existing OpenWrt installation |
| `*.manifest` | List of installed packages |
| `profiles.json` | Build profile metadata |
| `feeds.buildinfo` | Feed versions used |
| `config.buildinfo` | Build configuration |

---

## 🚀 Quick Start

### 1️⃣ Download Image
Grab the latest **factory image** from the releases or repository files.

### 2️⃣ Flash to SD Card
Use one of:

- balenaEtcher
- Raspberry Pi Imager
- dd (advanced users)

### 3️⃣ Boot Raspberry Pi 5
Insert the SD card and power on.

### 4️⃣ Connect
After boot:

- Open browser → http://192.168.1.1
- Default login → root
- No password (set immediately!)

---

## 📡 Wi-Fi Driver Support

This image includes kernel modules for:

Realtek RTL8821AU USB Wi-Fi adapters using the rtw88 driver stack

To verify driver loading:

lsmod | grep rtw

Check USB detection:

lsusb
dmesg | grep -i wifi

---

## 🛠️ If Wi-Fi Doesn’t Appear

Try:

opkg update
opkg install kmod-rtw88-8821au
wifi reload

Or reboot:

reboot

---

## ⚠️ Notes & Limitations

- Not all Realtek adapters are RTL8821AU — verify chipset first  
- Snapshot builds may behave differently  
- In-kernel drivers (when available) are typically more stable  

---

## 🧠 Intended Use Cases

✔ Portable travel router  
✔ Learning OpenWrt  
✔ USB Wi-Fi experimentation  
✔ Custom networking labs  
✔ Raspberry Pi router projects  

---

## 🔧 Rebuilding the Image (Advanced)

1. Clone OpenWrt source  
2. Update feeds  
3. Select target:

Target → bcm27xx  
Subtarget → bcm2712 (Raspberry Pi 5)

4. Enable:

Kernel modules → Wireless Drivers → kmod-rtw88-8821au

5. Build:

make -j$(nproc)

---

## 🤝 Contributing

Contributions are welcome:

- Driver improvements  
- Build scripts  
- Hardware compatibility reports  
- Documentation updates  

When reporting issues, include:

- Adapter model  
- lsusb output  
- OpenWrt version  
- Logs (dmesg)

---

## 📄 License

Unless otherwise specified:

MIT License

(OpenWrt & kernel modules retain their respective licenses.)

---

## ⭐ Support the Project

If this helped you:

⭐ Star the repo  
🐛 Report issues  
🔧 Submit improvements  
