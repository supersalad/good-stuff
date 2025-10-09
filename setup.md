# 🧰 New Windows Developer Laptop Setup Checklist

## 🪟 Base System Setup

* [ ] Fully update Windows (Windows Update, drivers, optional updates)
* [ ] Enable **Developer Mode**

  * Settings → Privacy & Security → For Developers → Enable Developer Mode
  * ✅ Verify in PowerShell:

    ```powershell
    reg query "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModelUnlock" /v AllowDevelopmentWithoutDevLicense
    ```
* [ ] Install **Windows Terminal**
* [ ] Install **PowerShell 7+**
* [ ] [Chocolatey](https://chocolatey.org/install)

---

## 🌐 Browsers & Utilities

* [ ] **Google Chrome**
* [ ] **Ditto** (clipboard manager)
* [ ] **KeePass** (password vault)
* [ ] **Notepad++**
* [ ] **7-Zip** 

---

## 🧑‍💻 Developer Core

* [ ] **VS Code** 
* [ ] Install VS Code extensions:

  * [ ] C# / .NET Tools / C# Dev Kit
  * [ ] Docker

---

## 🧱 .NET Development

* [ ] Install **.NET SDK (x64)** versions:

  * [ ] .NET 6 (LTS)
  * [ ] .NET 8 (LTS)
  * [ ] .NET 9 (STS, optional for testing)
* [ ] Verify installation:

  ```bash
  dotnet --list-sdks
  ```
* [ ] (Optional) Install .NET 10 preview for experimentation
* [ ] Configure global.json in your repos as needed

---

## 🧩 Git Setup

* [ ] Install **Git for Windows**

  * HTTPS transport → **OpenSSL**
  * Line endings → **Checkout as-is, commit Unix-style (LF)**
  * Terminal → **Use Windows default console window**
  * Default pull behavior → **Rebase**
  * Credential helper → **Git Credential Manager (GCM)**
  * File system caching → **Enable**
  * Symbolic links → **Enable** (Developer Mode required)
* [ ] Configure Git globals:

  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "you@example.com"
  git config --global core.autocrlf input
  git config --global pull.rebase true
  git config --global credential.helper manager
  git config --global core.fscache true
  ```
* [ ] Verify configuration:

  ```bash
  git config --list
  ```

---

## 🐧 Linux & Docker

* [ ] Enable **WSL** (Windows Subsystem for Linux) and **Virtual Machine Platform**

  ```powershell
  wsl --install
  wsl --update
  ```
* [ ] Install a Linux distro (Ubuntu recommended)
* [ ] Update and install basic packages in WSL:

  ```bash
  sudo apt update && sudo apt install -y build-essential git curl unzip
  ```
* [ ] Install **Docker Desktop for Windows**

  * Enable **WSL2 backend**
  * Test:

    ```bash
    docker run hello-world
    ```
* [ ] (Optional) Install **Kubernetes / kubectl** if needed

---

## 🟢 Node.js & Frontend Tools

* [ ] Install **Node.js (LTS)** (x64) from [nodejs.org](https://nodejs.org/)
* [ ] Verify installation:

  ```bash
  node -v
  npm -v
  ```
* [ ] (Optional) Install **nvm for Windows** for managing Node versions:

  * [nvm-windows on GitHub](https://github.com/coreybutler/nvm-windows)
  * Example:

    ```bash
    nvm install 20
    nvm use 20
    ```

## 🧮 Databases & Tools

* [ ] Install database engines as needed:

  * [ ] PostgreSQL / SQL Server / SQLite
* [ ] Install database clients:

  * [ ] DBeaver / HeidiSQL / Azure Data Studio
* [ ] Install **Postman** or **Insomnia** (API testing)
* [ ] (Optional) Install **Redis**, **RabbitMQ**, etc. if your projects use them

---

## 🔐 Security & Backups

* [ ] Enable **BitLocker** (if supported)
* [ ] Verify antivirus / Windows Defender status
* [ ] Backup SSH keys and personal config files securely


