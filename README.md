# 🧠 Akira IOC Scanner

## Overview  
The **Akira IOC Scanner** is a Python-based utility designed to scan directories for **Indicators of Compromise (IOCs)** related to the **Akira ransomware group**.  

It detects:  
- ✅ **Matching MD5 hashes** of known malicious files  
- ✅ **Matching SHA256 hashes** of known malicious files  
- ✅ **Presence of known Akira Bitcoin (BTC) addresses** in text-like files (`.txt`, `.log`, `.html`, `.json`, `.xml`, etc.)

IOCs are hardcoded based on intelligence from trusted threat-tracking sources such as **Ransomware.live** and **GitHub repositories** documenting threat actor behaviors.  

> ⚠️ **Note:** This tool is for **educational and defensive use only**. It does not prevent ransomware infection but aids in **post-incident analysis** or **threat hunting**. Always use it in a **safe, isolated environment**.

---

## ✨ Features  
- 🔍 Recursively scans specified directories and subdirectories  
- 🔢 Computes **MD5** and **SHA256** hashes for all files  
- 🧾 Searches for **BTC addresses** using regex (case-insensitive)  
- 💬 Displays all matches and findings in the console  

---

## ⚙️ Requirements  
- **Python 3.x** (tested on Python 3.12)  
- Uses only Python’s **standard libraries**:  
  - `os`, `hashlib`, `sys`, `re`  
- ✅ No external dependencies required  

---

## 🧩 Installation  
1. Save the script as:  
   ```
   akira_ioc_scanner.py
   ```
2. Ensure Python is installed on your system (`python --version`).  
3. No additional setup or modules are needed.  

---

## 🚀 Usage  
Run the script from the command line, providing the target directory as an argument:  
```bash
python akira_ioc_scanner.py /path/to/directory
```

### Example  
```bash
python akira_ioc_scanner.py /home/user/suspicious_files
```

If no directory is specified, usage instructions will be displayed automatically.  

During the scan, progress and findings are printed to the console, including any IOC matches.  

---

## 🧠 IOC Data  

| IOC Type | Count | Description |
|-----------|--------|-------------|
| **BTC Addresses** | 7 | Known ransom payment wallets |
| **MD5 Hashes** | 321 | Known Akira-related file samples |
| **SHA256 Hashes** | 37 | Known Akira-related file samples |

> 🗂️ Sources:  
> - [Ransomware.live](https://ransomware.live)  
> - [crocodyli/ThreatActors-TTPs on GitHub](https://github.com/crocodyli/ThreatActors-TTPs)

🔄 **Tip:** The hash and BTC address lists in the script may be **truncated** for readability. Update or expand them as new IOCs become available.

---

## ⚠️ Limitations  
- Scans only for **exact hash matches** and BTC patterns  
- Does **not** analyze encrypted or compressed files  
- Text search is limited to predefined file extensions (modifiable in script)  
- May run slower on **large file sets** due to per-file hashing  
- Possible **false positives**, e.g., benign files sharing hashes or random BTC-like strings  

---

## 🤝 Contributing  
Contributions are welcome!  
If you’d like to:  
- Add new IOC sources  
- Improve scanning efficiency  
- Enhance output formatting  

Fork the repo and submit a pull request.  

---

## 📜 License  
This project is licensed under the **MIT License**.  
Use at your own risk and in accordance with applicable laws.  

---

## ⚖️ Disclaimer  
This tool is **not affiliated** with any cybersecurity vendor or the Akira group.  
It is provided **“as is,” without warranty of any kind**.  
Users are responsible for ensuring legal and ethical use in their environment.  
