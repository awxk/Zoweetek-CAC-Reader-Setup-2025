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
