## 🧩 Troubleshooting
- Make sure your CAC is fully inserted.
- If no certificates appear, re-run `certutil -scinfo` and check the reader connection. You may also be overdue for a new CAC, and your certificates will be expired.
- For browser-specific issues (e.g., with Chrome or Firefox), ensure the browser is configured to recognize smart card certificates.

---

## 🧠 Additional Tips

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
