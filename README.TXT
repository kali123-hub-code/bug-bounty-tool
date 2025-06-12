# 🔍 Vulnyx

**Vulnyx** is a blazing-fast, automated vulnerability scanner designed for ethical hackers, bug bounty hunters, and security researchers. It detects critical web application vulnerabilities like:

* ✅ Subdomain Takeover
* ✅ SSRF (Server-Side Request Forgery)
* ✅ SQL Injection (SQLi)
* ✅ NoSQL Injection
* ✅ Cross-Site Scripting (XSS)
* ✅ Open Redirects
* ✅ Security Misconfigurations
* ✅ And many more...

Vulnyx generates a single, clean GUI-style report for fast review of discovered bugs.

---

## 🚀 Features

* ⚡ **Ultra-fast** scanning engine
* 🎯 **Automated** detection of multiple vulnerability types
* 📈 **Single-page GUI Report** output
* 🧠 Smart scanning logic with reduced false positives
* 🔒 Focused on **ethical use only**

---

## 📦 Installation

```bash
git clone https://github.com/yourusername/vulnyx.git
cd vulnyx
chmod +x vulnyx.sh
```

> Ensure you have basic tools installed: `curl`, `dig`, `jq`, `nuclei`, `subfinder`, etc.

---

## 🛠️ Usage

### Scan a target domain:

```bash
./vulnyx.sh -d example.com
```

### Use a list of subdomains:

```bash
./vulnyx.sh -l live_subdomains.txt
```

---

## 📁 Output

* Generates `report.html` in the current directory
* Shows categorized vulnerabilities in a user-friendly format

---

## 🧪 Example

---

## 🧠 Disclaimer

> This tool is intended **only** for **authorized testing**, research, and educational purposes. Unauthorized use of Vulnyx on systems you don't own is illegal and unethical.

---

## 🡩‍💻 Author

* **Your Name** – [@yourhandle](https://github.com/yourusername)
* Contributions welcome!

---

## ⭐ Star the Repo

If you like this project, don't forget to ⭐ star it on GitHub to support more development!
