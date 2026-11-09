# CYBER_KEY // Cyberpunk License Key Manager & API Web Application

A single-file HTML/JS Cyberpunk-themed License Key Manager & REST API Web Application built with a Dark Red theme (`#ff003c` accent, dark glassmorphism cards, glowing neon elements, and sci-fi aesthetic).

---

## 🌟 Key Features

1. **MIL-SPEC LOGIN & ACCESS CONTROL**
   - Access password: `DevReal` or `real` (case-insensitive).
   - High-security lock screen overlay with digital unlock sequence, HUD status indicators, and Web Audio API synthesized sound effects.
   - Relock button in navbar and `sessionStorage` session retention.

2. **FIREBASE REALTIME DATABASE SYNC**
   - Integrated with Firebase SDK (v9 compat) for real-time global synchronization.
   - Live WebSocket sync across `/keys`, `/apps`, and `/logs`.
   - **Interactive In-Browser Configuration**: Click the status indicator or gear icon to customize `apiKey`, `authDomain`, `databaseURL`, `projectId`, `storageBucket`, and `appId`.
   - **Local Simulation Engine**: If no live Firebase credentials are provided, a built-in simulation mirror activates automatically using `localStorage`, allowing instant testing and offline demonstration without crashes.

3. **DYNAMIC ACTIVE APP REGISTRY (AUTO-DETECTION)**
   - Zero hardcoded apps!
   - Listens to `/apps` path in Firebase to automatically display only active software sending pings/heartbeats from external clients (C#, Python, Batch, etc.).
   - Live status badges (`ONLINE` / `OFFLINE` based on heartbeat timestamps), client versions, and last-seen metrics.
   - Built-in **Heartbeat Simulator** to broadcast test pings directly from the web interface.

4. **KEY GENERATOR & CUSTOMIZER**
   - Customizable Prefix (`REAL`, `AIM`, `NL3D`, or custom).
   - Configurable Segment Count (1–5) and Segment Length (4–8 characters).
   - Character Sets: Uppercase, Lowercase, Numbers, and Special Symbols.
   - Expiration Control: 1-Day Trial, 7-Day Pass, 30-Day Standard, 90-Day Quarter, 365-Day Annual, Unlimited/Lifetime, or Custom Days.
   - Hardware ID (HWID) binding enforcement toggle.
   - Single & Batch Key Generation (1 to 50 keys at once) with animated progress bar and live format preview.

5. **MASTER KEY VAULT TABLE**
   - Instant search across License Keys, App names, HWIDs, and Notes.
   - Filter by target application and status (`ACTIVE`, `EXPIRED`, `REVOKED`).
   - One-click actions: Copy key, Revoke/Reactivate, Extend lifespan (+7d, +30d, +90d, Lifetime), Reset HWID lock, and Permanent Delete.
   - Export database in **.TXT** or **.JSON** formats.

6. **CLIENT INTEGRATION SDK & DOCS TOOLKIT**
   - Copy-paste integration scripts for:
     - **C# (.NET Core / .NET Framework)**: Complete client class with HWID generation, REST validation, HWID auto-binding, and background heartbeat.
     - **Python (Requests)**: Standalone Python script with hardware fingerprinting, REST validation, and background heartbeat thread.
     - **PowerShell / Batch Script**: Windows CLI validation script with automatic HWID hashing and REST communication.
   - Dynamic parameter injection: Code snippets automatically populate with your active Firebase Database URL and selected target app.
   - Step-by-step guides for Firebase Database Rules, GitHub push, and Vercel edge deployment.

7. **CYBERPUNK AUDIO & VISUAL EFFECTS**
   - Deep pitch-black background with red neon glowing borders (`#ff003c`), translucent glassmorphic panels, and cyber grid backdrop.
   - Animated scanlines overlay (toggleable on/off).
   - Web Audio API Synthesizer with sound effects for clearance granted/denied, key generation, and clipboard copies (with mute toggle).

---

## 🚀 Quick Start Guide

### 1. Run Locally
Simply open `index.html` in any modern web browser:
```powershell
Start-Process "C:\Users\Administrator\.gemini\antigravity\scratch\cyberpunk-license-manager\index.html"
```

### 2. Enter Clearance Password
Type **`DevReal`** or **`real`** and press Enter.

### 3. Connect to Firebase Realtime Database
1. Click the status indicator in the top navbar (`CONNECTING...` or `SIMULATION MODE`).
2. Enter your Firebase project credentials (`databaseURL`, `apiKey`, `projectId`, etc.).
3. Click **Save & Connect**.
4. In your [Firebase Console](https://console.firebase.google.com), set your Realtime Database rules:
```json
{
  "rules": {
    "keys": { ".read": true, ".write": true },
    "apps": { ".read": true, ".write": true },
    "logs": { ".read": true, ".write": true }
  }
}
```

### 4. Deploy to Vercel (Edge Hosting)
1. Initialize git and commit:
```bash
git init
git add index.html
git commit -m "feat: Cyberpunk License Manager"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/cyberpunk-key-manager.git
git push -u origin main
```
2. Import repository on [Vercel.com](https://vercel.com) and deploy with zero configuration.
