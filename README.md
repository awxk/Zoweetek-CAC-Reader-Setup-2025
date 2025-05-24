# Zoweetek CAC Reader Setup Guide (2025)

This guide will walk you through setting up your Zoweetek Common Access Card (CAC) reader on a Windows system and preparing it for access to DoD websites.

---

## 🔌 Step 1: Connect Hardware
1. **Plug in** your Zoweetek CAC reader to a USB port.
2. **Insert your CAC** into the reader.

---

## 🧰 Step 2: Install the Zoweetek Driver
1. Go to the official Zoweetek driver page:  
   👉 [https://zoweetek.cn/software-driver-download/](https://zoweetek.cn/software-driver-download/)
2. Download the latest driver that matches your specific reader model.
3. **Extract all files** from the downloaded ZIP.
4. Run the `autorun` application.
5. Follow on-screen instructions. When prompted, click **Install**.

---

## 📦 Step 3: Install DoD Certificates (InstallRoot)
1. Visit the official DoD certificate installer page:  
   👉 [https://public.cyber.mil/pki-pke/end-users/getting-started/](https://public.cyber.mil/pki-pke/end-users/getting-started/)
2. Select your **Operating System** and download the appropriate version.
   - Most Windows users should use this direct link for 64-bit systems:  
     👉 [InstallRoot_5.6x64.msi](https://dl.dod.cyber.mil/wp-content/uploads/pki-pke/msi/InstallRoot_5.6x64.msi)
3. Run the `.msi` installer and follow the prompts to install **all DoD certificates**.

---

## 🛠 Step 4: Run Certutil to Initialize Certificates
1. Open **Command Prompt as Administrator**.
2. Type the following command and press Enter:
   ```bash
   certutil -scinfo
   ```
3. You will be prompted to enter your **CAC PIN** multiple times (usually ~4 times). Enter it each time.  
     ⚠️ **WARNING:** This is your **CAC PIN**, NOT your PC's PIN. Don't get locked out! ⚠️
4. Wait for the command to fully complete.

---

## 🔐 Step 5: Install CAC Certificates
1. A certificate selection window should appear.
2. For each certificate:
   - Choose to install to **both**:
     - *Current User*
     - *Local Machine*
   - Accept the **default installation path** each time.

---

## ✅ Done!
You should now be able to access **DoD websites** that require CAC login.

---

## 🧩 Troubleshooting
- Make sure your CAC is fully inserted.
- If no certificates appear, re-run `certutil -scinfo` and check the reader connection. You may also be overdue for a new CAC, and your certificates will be expired.
- For browser-specific issues (e.g., with Chrome or Firefox), ensure the browser is configured to recognize smart card certificates.

---

## 🧠 Additional Tips & Troubleshooting

### 🔄 Browser Configuration
Some browsers, like **Firefox**, do not use the Windows Certificate Store by default.

- Go to: `Settings > Privacy & Security > Certificates > Security Devices`
- Click **Load**
- Choose `Microsoft Smart Card` from the module list

### 🛎 Smart Card Service
If `certutil -scinfo` hangs or fails:
- Press `Win + R`, type `services.msc`, and hit Enter
- Locate **Smart Card**
- Right-click and choose **Start**
- To start automatically in the future, set Startup type to **Automatic**

### 🖥 Verify Reader Detection
If nothing happens when you insert your CAC:
- Open **Device Manager**
- Expand **Smart card readers**
- Ensure your Zoweetek device is listed
- No yellow warning icons should be present

### 🔐 Avoiding PIN Block
Your CAC can become locked after too many incorrect PIN attempts:
- Typically, 3–5 failed tries will block the card
- A blocked CAC must be reset at a RAPIDS/ID card office

### ⚙️ Run as Administrator
Always run command-line steps and installer files as **Administrator** to ensure they have necessary permissions.

---

