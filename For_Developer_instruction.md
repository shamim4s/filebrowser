# 🧑‍💻 Developer Setup Guide — FileBrowser

This document helps you set up and build the FileBrowser project with both **frontend** and **backend** components.

---

## ✅ Prerequisites

### 1. Install Golang
Download and install Go from the official site:  
➡️ https://go.dev/doc/install

> ⚠️ Ensure `go` is in your system's PATH by running `go version` in your terminal.

---

### 2. Install Node.js (LTS Recommended)
Download and install Node.js and npm from:  
➡️ https://nodejs.org/en/download/

> ⚠️ Run `node -v` and `npm -v` to confirm installation.

---

---

## 🧱 Project Setup

### 1. Clone the repository

```bash
git clone https://github.com/shamim4s/filebrowser.git
cd filebrowser
```

---

### 2. Build the Frontend (Vue + TypeScript)

Navigate to the frontend folder and build assets:

```bash
cd frontend
npm install
npm run build
```

This will output the compiled static files in `frontend/dist/`.


### 3. PowerShell Execution Policy Fix (Windows)

If you encounter this error while running `npm install`:
```
npm : File ...\npm.ps1 cannot be loaded because running scripts is disabled on this system.
```

Run the following command **in PowerShell (Run as Administrator)**:
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process
```

> This change is **temporary** and applies only to the current session.


---

### 3. Build the Backend (Go)

From the **project root**, run:

```bash
cd ..
go build -o filebrowser.exe .
```

This compiles the backend and generates the `filebrowser` binary in the root directory.

---

## 🚀 Run FileBrowser with Custom Configuration

Once build is complete, run the following setup in **Command Prompt** or **PowerShell**:

```powershell
cd "C:\filebrowser"

del filebrowser.db

.\filebrowser.exe config init

.\filebrowser.exe users add admin password123 --perm.admin


filebrowser config set -r "C:\Users" -p "8080" --address "192.168.1.117" --branding.name "my name" --database "e:\filebrowser\filebrowser.db" --log "e:\filebrowser\filebrowser.log" --disable-thumbnails --branding.files "e:\filebrowser" --disable-preview-resize --cache-dir="" | filebrowser.exe

```

### 💡 Notes:
- `-r` is the root directory to serve
- `--address` is the network bind IP (can be `0.0.0.0` for all interfaces)
- Adjust paths as needed for your system

---

## 🏁 You're all set!

You should now be able to access FileBrowser in your browser at:
```
http://192.168.10.70:8080
```

Login using:
- **Username:** `admin`
- **Password:** `password123`

#Create a bat/cmd file to run this without write command everytime
```
@echo off

REM Define path variables
set FILEBROWSER_PATH=C:\windows\filebrowser
set DATA_PATH=c:\users\public
set ADDRESS=192.168.10.65
set PORT=8080
set BRANDING_NAME=Shamim4s file browser

cd /d "%FILEBROWSER_PATH%"

REM Execute the command with variables
"%FILEBROWSER_PATH%\filebrowser.exe" config set -r "%DATA_PATH%" -p "%PORT%" --address "%ADDRESS%" --branding.name "%BRANDING_NAME%" --database "%FILEBROWSER_PATH%\filebrowser.db" --log "%FILEBROWSER_PATH%\filebrowser.log" --disable-thumbnails --branding.files "%FILEBROWSER_PATH%" --disable-preview-resize --cache-dir="" | "%FILEBROWSER_PATH%\filebrowser.exe"

```



Happy Life!
