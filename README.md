## Python Keylogger for Windows

### Uses
Some uses of a keylogger are:
- Security Testing: improving the protection against hidden key loggers;
- Business Administration: Monitor what employees are doing (with their consent);
- School/Institutions: Track keystrokes and log banned words in a file;
- Personal Control and File Backup: Make sure no one is using your computer when you are away;
- Parental Control: Track what your children are doing;
- Self-analysis and assessment.

### Features
- Global event hook on all (incl. On-Screen) keyboards using cross-platform library [Keyboard](https://github.com/boppreh/keyboard). The program makes no attempt to hide itself.
- Pure Python, no C modules to be compiled.
- 2 logging modes:
  - Storing logs locally and once a day sending logs to your onion hidden service (via Tor, stealthily installing it);
  - Debug mode (printing to console).
- Persistence:
  - Adding to Windows Startup.
- Human-readable logs:
  - Logging keys as they actually are in your layout;
  - Logging window titles and current time where appropriate;
  - Backspace support (until the active window is changed);
  - Full upper-/ lowercase detection (capslock + shift keys).
- Privacy protection:
  - RSA public-key encryption of logs on the fly using [PyCryptoDome](https://pycryptodome.readthedocs.io/en/latest/).

### Security Concerns
- Privacy Concerns: 
  - Keyloggers can be used to record sensitive information such as passwords, credit card numbers, and other personally identifiable information.
  - This information can then be used for malicious purposes.
- Data Theft: 
  - Keyloggers can be used to steal data from a computer. 
  - This data can then be used for malicious purposes such as identity theft, fraud, or other criminal activities.
- Malware: 
  - Keyloggers are a type of malware and can be used to infect a computer with malicious software such as viruses, worms, and other malicious code.
- Denial of Service Attacks: 
  - Keyloggers can be used to launch denial of service attacks. 
  - These attacks can cause a computer to crash or become unresponsive.
- Unauthorized Access:
  - Keyloggers can be used to gain unauthorized access to a computer system.
  - This can be used to gain access to restricted areas of the system or to steal information.

### Getting started

#### System requirements
- MS Windows (tested on 10).
- [Python 3](https://www.python.org/downloads/) (tested on v. 3.10.1).

#### Usage

##### **Quick start**
1. `git clone https://github.com/nitish-0211/python-keylogger.git`
2. `cd python-keylogger`
3. Customize parameters in Start.py: url_server_upload, hidden_service_check_connection.
###### **Run as a Python script**
3. `pip install requirements.txt` (alternatively `python -m pip ...`)
4. `python Start.py`
###### **Run as an executable (7 MB)**
3. `pip install pyinstaller`
4. `pyinstaller --onefile --noconsole --icon=icon.ico Start.py`
5. `dist\Start.exe`
###### **To use RSA log encryption/decryption (optional)**
1. Generate RSA key pair (optional): `python rsa_key_generator.py`.
1. Change the public key filename / paste the key in Start.py.
1. To decrypt logs type `python log_decryptor.py`, and then follow the instructions given by the script.

##### System arguments
`Start.py mode [encrypt]`
- **modes**:
  - **local:** store the logs in a local txt file. Filename is a MD5 hash of the current date (YYYY-Mon-DD).
  - **debug:** write to the console.
- **[optional]**
  - **encrypt:** enable the encryption of logs with a public key provided in Start.py.


### Known issues
- Does not capture passwords auto-typed by KeePass, however, it captures KeePass DB passwords.
- See [Keyboard: Known limitations](https://github.com/boppreh/keyboard#known-limitations). 

(Feel free to contribute to fix any problems, or to submit an issue!)
