# DriveHub — Downloads & Installation Guide

Official release repository for the **Artslab DriveHub Desktop Application** for Windows and macOS.

The DriveHub desktop app gives you DriveHub in its own window, with downloads that land straight in your Downloads folder, taskbar progress while files transfer, a tray icon that keeps transfers running when the window is closed, and automatic updates.

---

## 📥 Download the Latest Version

Go to the [**Latest Releases Page**](https://github.com/artslabcreatives/drivehub-desktop-releases/releases/latest) and download the installer for your operating system:

| Operating System | Architecture | Installer File |
|---|---|---|
| **Windows 10 / 11** | 64-bit (x64) | `DriveHub-Setup-x.y.z.exe` |
| **macOS (Apple Silicon)** | M1 / M2 / M3 / M4 (`arm64`) | `DriveHub-x.y.z-arm64.dmg` |
| **macOS (Intel)** | Intel Core i5/i7/i9 (`x64`) | `DriveHub-x.y.z-x64.dmg` |

> *Tip: If you are unsure which Mac you have, click the **Apple logo () → About This Mac**. Look at the **Chip** (Apple Silicon: M1/M2/M3/M4) or **Processor** (Intel).*

---

## 🪟 Windows Installation Guide

### Step 1: Download & Run Installer
1. Download **`DriveHub-Setup-x.y.z.exe`**.
2. Double-click the downloaded `.exe` file to begin installation.

### Step 2: Windows Defender SmartScreen Prompt
Because this application is distributed directly by Artslab, Windows SmartScreen may display a blue warning screen stating:

> *"Windows protected your PC — Microsoft Defender SmartScreen prevented an unrecognized app from starting."*

This is normal for newly released desktop apps. To proceed:
1. Click **More info** (underlined text below the message).
2. Click the **Run anyway** button that appears in the bottom right corner.

### Step 3: Complete Setup
1. Follow the setup wizard to choose your install location (or accept the default).
2. The installer adds **Desktop** and **Start Menu** shortcuts.
3. Click **Finish**. DriveHub launches — sign in with your DriveHub account.

---

## 🍏 macOS Installation Guide

### Step 1: Download & Mount Disk Image
1. Download the correct `.dmg` file for your Mac:
   - For Apple Silicon (M1/M2/M3/M4): `DriveHub-x.y.z-arm64.dmg`
   - For Intel Macs: `DriveHub-x.y.z-x64.dmg`
2. Double-click the downloaded `.dmg` file to open it.
3. Drag the **DriveHub** icon into your **Applications** folder.

---

### Step 2: First-Time Launch (macOS Security & Gatekeeper)
Because the app is ad-hoc signed, macOS Gatekeeper may show a security dialog when you first open it:

> *"DriveHub cannot be opened because Apple cannot check it for malicious software"* or *"cannot be opened because the developer cannot be verified"*.

To allow DriveHub to run, follow these quick steps:

#### Method A: Via System Settings (Recommended)
1. Try opening **DriveHub** from your **Applications** folder once (click **OK** or **Cancel** on the prompt).
2. Open your Mac's **System Settings** (or **System Preferences**).
3. In the left sidebar, click **Privacy & Security**.
4. Scroll down to the **Security** section.
5. You will see a note:
   > *"DriveHub" was blocked from use because it is not from an identified developer.*
6. Click the **Open Anyway** button next to it.
7. Enter your Mac user password or use Touch ID when prompted.
8. Click **Open** on the confirmation dialog.

*(You only have to do this once. DriveHub will open normally on all future launches!)*

#### Method B: Fast Terminal Command (For Power Users)
Alternatively, open your Mac **Terminal** and run:
```bash
xattr -cr "/Applications/DriveHub.app"
```
Then double-click **DriveHub** in Applications to launch immediately.

---

## 💡 How the App Works (Tips & Tricks)

### 1. Downloads
- Files you download from DriveHub are saved straight to your **Downloads** folder. If a file with the same name already exists, the new one is saved as `name (1).ext` rather than overwriting it.
- While files are transferring, progress shows on the **taskbar** (Windows) or **Dock** (macOS) icon.
- When a file finishes, a notification appears — click it to show the file in Explorer / Finder.
- Prefer to choose the folder each time? Right-click the tray icon and check **Ask where to save each file**.
- The tray menu also lists your **Recent downloads** (click one to reveal it) and has **Open downloads folder**.

### 2. Runs in Background / System Tray
- When you click the **Close (X)** button, the app does not shut down. It moves to the **System Tray** (Windows, bottom-right near the clock) or the **Menu Bar** (macOS, top-right), so downloads in progress keep going.
- To fully quit: right-click the DriveHub tray icon and select **Quit DriveHub**. If downloads are still running, DriveHub asks before quitting, since quitting cancels them.

### 3. Launch at Startup
- Right-click the tray icon and check **Launch at startup** so DriveHub starts automatically, quietly in the tray, whenever you sign in to your computer.

### 4. Automatic Updates
- **Windows**: The app checks for updates every 4 hours. Updates download silently in the background and install when you quit the app — or click the "update ready" notification to restart and install straight away.
- **macOS**: When a new version is released, you will receive a desktop notification with a link to download it.

### 5. Offline
- If your connection drops, DriveHub shows a reconnecting screen and reloads automatically as soon as you're back online.

---

## ❓ Frequently Asked Questions (FAQ)

<details>
<summary><b>Why does Windows show "Windows protected your PC"?</b></summary>
Artslab distributes this app independently. Windows flags any app that does not yet have an established reputation or a commercial EV Authenticode certificate. Clicking <b>More info → Run anyway</b> is safe and expected.
</details>

<details>
<summary><b>Why does macOS block opening the app on the first run?</b></summary>
macOS Gatekeeper blocks apps from outside the Mac App Store that haven't been notarized through an Apple Developer account. Following the <b>System Settings → Privacy & Security → Open Anyway</b> step authorizes the app on your computer.
</details>

<details>
<summary><b>Where did my download go?</b></summary>
Your <b>Downloads</b> folder, unless you turned on <b>Ask where to save each file</b>. Right-click the tray icon → <b>Recent downloads</b> and click the file to reveal it.
</details>

<details>
<summary><b>How do I check for updates manually?</b></summary>
Right-click the DriveHub icon in your Windows System Tray or Mac Menu Bar and select <b>Check for updates…</b>.
</details>

---

## 🔒 Security & Privacy

DriveHub is built with a sandboxed Electron architecture:
- Only DriveHub itself opens inside the app; links to other sites open in your default web browser.
- The app is granted only the permissions it needs (notifications, clipboard, fullscreen) — no camera or microphone access.
- Communication with Artslab servers is secured over encrypted HTTPS.
