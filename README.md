# NcryptO

> **NO Authentication · NO Access · NO Trace**

A lightweight, client-side file encryption and decryption tool that runs entirely in your browser. No servers. No uploads. No accounts. Your files never leave your machine.

---

## Features

- **AES-256-GCM** — Authenticated encryption with tamper detection (recommended)
- **AES-256-CBC** — Symmetric encryption for broader compatibility
- **PBKDF2 Key Derivation** — 310,000 iterations with a random salt, making brute-force attacks computationally expensive
- **Drag & Drop** — Drop any file directly onto the interface, or use the file picker
- **Original Filename Preserved** — The original filename is embedded in the encrypted file and automatically restored on decryption
- **Password Strength Indicator** — Live feedback as you type your passphrase
- **100% Client-Side** — All cryptographic operations use the browser's native Web Crypto API; zero network requests

---

## How It Works

### Encrypting a File

1. Open `index.html` in any modern browser
2. Drop a file onto the **Encrypt** panel, or click to browse
3. Choose an algorithm — **AES-256-GCM** (default) or **AES-256-CBC**
4. Enter a strong passphrase
5. Click **Encrypt File**
6. Download the `.enc` output file

### Decrypting a File

1. Switch to the **Decrypt** tab
2. Drop the `.enc` file onto the panel
3. Enter the same passphrase used during encryption
4. Click **Decrypt File**
5. Download the restored original file

---



## Security Notes

- **Passphrase strength is everything.** The security of your encrypted file depends entirely on the strength of your passphrase. Use a long, random passphrase.
- **AES-256-GCM is recommended** — it provides authenticated encryption, meaning any tampering with the encrypted file will be detected on decryption.
- **No password recovery.** There is no account, no reset link, and no backdoor. A lost passphrase means the file cannot be decrypted.
- **Random salt & IV** — A fresh cryptographically random salt and IV are generated for every encryption operation, so two encryptions of the same file with the same password produce different outputs.

---

## Browser Compatibility

NcryptO relies on the [Web Crypto API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API), which is supported in all modern browsers:

| Browser | Support |
|---|---|
| Chrome / Edge | ✅ v37+ |
| Firefox | ✅ v34+ |
| Safari | ✅ v11+ |
| Opera | ✅ v24+ |

---

## Usage

NcryptO is a single self-contained HTML file — no build step, no dependencies, no installation.

```bash
# Just open it
open index.html
```

Or serve it locally:

```bash
python3 -m http.server 8080
# Then visit http://localhost:8080/index.html
```

---

## Privacy

- No data is ever sent to any server
- No analytics, no telemetry, no cookies
- Works fully offline once the page is loaded
- The page can be saved locally and used without an internet connection (fonts will fall back to system fonts)
