🔐 Password Vault

A secure, lightweight, and easy-to-use password manager built with strong encryption to safely store and manage your credentials.

This project provides a personal vault where you can store website logins, app credentials, notes, and sensitive information — all encrypted and accessible only with your master key.

📌 Overview

Password Vault is designed for people who want:

Full control over their password data

A simple local vault without cloud storage

Strong encryption around sensitive information

A beginner-friendly but powerful security project

This project can also be used for academic, portfolio, or interview demonstration purposes to show your understanding of encryption, security, and full-stack development.

✨ Features

🔐 AES-256 encryption for storing passwords

🗂️ Store entries like:

Website / App name

Username / Email

Password

URL

Notes

🕵️‍♂️ Master password–based unlock

🛡️ Auto-lock after inactivity

🎨 Clean, simple UI

🔍 Search & filter passwords

📝 Secure copy-to-clipboard

💾 Local database storage

🚀 Fast, minimal, no internet needed

🧩 Modular architecture — easy to extend

🧠 How It Works (Security Design)
🔑 1. Master Password

You set a master password, which is never stored.

A key is derived using:

PBKDF2 (Master Password, Salt, 100k+ iterations)

🔒 2. Encryption

All credentials are encrypted using:

AES-256 (CBC/CFB mode)

🗄️ 3. Storage

Encrypted data is stored in a local database file (SQL/JSON depending on implementation).

Even if someone accesses the file, they can't decrypt it without the master password.

🪟 4. Decryption

When you unlock the vault, the entries are decrypted in-memory only and displayed.

No plaintext is ever saved to disk.

📂 Project Structure
Password-vault/
│── vault.py                 # Core logic (encrypt/decrypt)
│── storage.py               # Save/load encrypted data
│── master_key.py            # Key derivation (PBKDF2)
│── ui.py                    # CLI/GUI interface
│── utils.py                 # Helpers
│── data/
│   └── vault.db             # Encrypted stored data
│── requirements.txt
│── README.md

🚀 Getting Started
1️⃣ Clone the Repo
git clone https://github.com/zoro-hue/Password-vault.git
cd Password-vault

2️⃣ Install Dependencies
pip install -r requirements.txt

▶️ Running the Application
Start the vault:
python vault.py

First Run

You will be asked to set a master password.

Next Runs

Enter your master password to unlock your vault.

🧾 Features in Detail
➕ Add New Password

You can store:

Site / App name

Username

Password

URL

Notes

Each entry is encrypted and saved.

🔍 View / Search Passwords

You can:

View list of entries

Search by website/app name

Filter items

Reveal password temporarily

Copy password to clipboard securely

✏️ Edit Password

You can update any field:

New password

Changed username

Updated URL

Additional notes

Everything is re-encrypted on save.

🗑️ Delete Password

Delete an entry permanently.

To avoid accidental loss, you can add a "Confirm delete".

🔐 Encryption Details
Key Derivation
PBKDF2-HMAC-SHA256  
Iterations: 100,000+
Salt: Random per-user salt  

Encryption
AES-256  
Mode: CBC or CFB  
IV generated randomly per-entry  

Integrity

HMAC or checksum can be added (optional) to ensure no tampering.

Sensitive Data Handling

Plaintext never written to disk

Clipboard clears automatically

Auto-lock (timeout) available

Database is encrypted as a single blob

⚠️ Security Recommendations

To keep your vault secure:

Use a strong master password

Never share your vault file

Backup the encrypted file often

Enable auto-lock when possible

Avoid using public computers

Your data is only as safe as your master password.

🔧 Customization

You can extend the project to include:

🔑 2-Factor Authentication (TOTP)

☁️ Cloud backup (encrypted)

📱 Mobile/PWA app

🖥️ Desktop UI using Tkinter/PyQt

🔄 Password generator

🔔 Breach alerts (check if passwords are leaked)

🗃️ Multiple vaults

🧑‍🤝‍🧑 User accounts / shared vaults

Just ask if you need help implementing any!

🐛 Known Limitations

No sync between devices (local only)

GUI may be basic (depending on implementation)

No browser extensions

No biometric unlock yet

🌱 Future Enhancements

Browser extension (Chrome/Firefox)

Export/Import encrypted format

Password expiry reminders

Clipboard auto-wipe

Auto-fill support for websites

Mobile app using Kivy/React Native

Cloud encrypted sync (optional)

🤝 Contributing

Contributions welcome!

Fork the repo

Create a feature branch

Commit your changes

Open a pull request
