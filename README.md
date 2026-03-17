# portscanner
Developed a custom Python-based port scanning tool capable of performing automated TCP scans and service banner extraction. The tool enhances reconnaissance workflows by identifying open ports, resolving hostnames, and exposing service-level information critical for penetration testing and vulnerability assessment.
# 🔎 Python Port Scanner with Banner Grabbing

A lightweight Python-based **port scanner and banner grabber** designed for **network reconnaissance and security testing**. This tool allows ethical hackers and cybersecurity learners to identify open ports and retrieve service banners from target systems.

---

## 🚀 Features

* 🔍 Scan ports from **1 to 1500**
* 🌐 Supports **IP addresses and domain names**
* 🧠 Automatic **DNS resolution**
* 📡 **Banner grabbing** for service identification
* ⚡ Fast scanning with configurable timeout
* 🧪 Supports **multiple targets**

---

## ⚠️ Disclaimer

> This tool is intended for **educational purposes and authorized security testing only**.
> Unauthorized scanning of systems without permission is illegal and may lead to legal consequences.

---

## 🧰 Requirements

* Python 3.x
* Required modules:

  * `socket` (built-in)
  * `IPy`

### Install dependencies:

```bash
pip install IPy
```

---

## 📂 Project Structure

```
port-scanner/
│── scanner.py
│── README.md
```

---

## 🧠 How It Works

1. User inputs a target (IP or domain)
2. Tool validates and converts domain → IP
3. Iterates through ports **1–1500**
4. Attempts TCP connection
5. If open:

   * Retrieves banner (if available)
   * Displays service info

---

## ▶️ Usage

### Run the script:

```bash
python3 scanner.py
```

### Input examples:

#### Single target:

```
[+] Enter Target/s To Scan: example.com
```

#### Multiple targets:

```
[+] Enter Target/s To Scan: example.com, 192.168.1.1
```

---

## 📌 Example Output

```
[-_0 Scanning Target] example.com
[+] Open Port 80 : HTTP/1.1 200 OK
[+] Open Port 22 : SSH-2.0-OpenSSH_8.2p1
[+] Open Port 443
```

---

## 🔍 Code Breakdown

### `scan(target)`

* Handles scanning logic for each target
* Loops through port range

### `check_ip(ip)`

* Validates IP address
* Resolves domain names to IP

### `scan_port(ipaddress, port)`

* Attempts connection to port
* Identifies open ports
* Performs banner grabbing

### `get_banner(socket)`

* Retrieves service response (if available)

---

## ⚡ Performance Notes

* Timeout set to **1 second** per port
* Scanning large ranges may take time
* Can be optimized using:

  * Multithreading
  * Async scanning

---

## 🛡️ Security Insights

* Open ports expose **attack surface**
* Banner data may reveal:

  * Service versions
  * Potential vulnerabilities
* Common targets:

  * Port 21 → FTP
  * Port 22 → SSH
  * Port 80 → HTTP
  * Port 443 → HTTPS

---

## 🚧 Limitations

* No UDP scanning
* No service fingerprinting beyond banners
* No stealth scanning (e.g., SYN scan)
* Sequential scanning (slower)

---

## 🔥 Future Improvements

* ✅ Multithreading for speed
* ✅ Custom port ranges
* ✅ Service detection database
* ✅ Output to file (JSON/CSV)
* ✅ Integration with vulnerability scanners

---

## 👨‍💻 Author

**kijanawaeast**
Cybersecurity Enthusiast & Developer
Focused on **ethical hacking, network security, and penetration testing tools**

---

## ⭐ Contribution

Feel free to fork, improve, and contribute to this project.

---

## 📜 License

This project is open-source and available under the MIT License.
