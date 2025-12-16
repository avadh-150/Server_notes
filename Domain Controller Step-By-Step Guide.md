# 🖥️ Windows Server 2022: From Workgroup to Domain Controller (AD DS + DNS)

## Step 1: Initial Setup
1. Log in to your Windows Server 2022 machine using **Administrator** privileges.
2. Assign a **static IP address**:
   - Go to **Settings → Network & Internet → Ethernet → Edit IP assignment → Manual**.
   - Enable **IPv4** and set:
     ```
     IP Address: 192.168.1.10
     Subnet Mask: 255.255.255.0
     Default Gateway: 192.168.1.1
     Preferred DNS: 127.0.0.1 (or your DNS server)
     ```
3. Click **Save**.

---

## Step 2: Rename Computer (Optional but Recommended)
1. Open **Server Manager → Local Server**.
2. Click **Computer name** (shows `Workgroup` by default).
3. Click **Change** → enter a new **Computer name** (e.g., `DC01`).
4. Keep **Member of: Workgroup** selected.
5. Click **OK** → Restart when prompted.

---

## Step 3: Install Active Directory Domain Services (AD DS)
1. Open **Server Manager**.
2. Click **Manage → Add Roles and Features**.
3. Click **Next** until you reach **Server Roles**.
4. Select **Active Directory Domain Services**.
5. When prompted, click **Add Features**.
6. Click **Next → Next → Install**.
7. Wait for the installation to complete (no reboot yet).

---

## Step 4: Promote the Server to a Domain Controller
1. In **Server Manager**, click the **Notification Flag (⚠️)** → choose **Promote this server to a domain controller**.
2. Select **Add a new forest**.
3. Enter your **Root domain name** (example: `example.local`).
4. Click **Next**.

---

### Step 4a: Domain Controller Options
1. **Forest Functional Level:** Windows Server 2022  
2. **Domain Functional Level:** Windows Server 2022  
3. **Select the following options:**
   - ✅ DNS Server  
   - ✅ Global Catalog (GC)  
   - ☐ Read-only domain controller (RODC)
4. Set a **Directory Services Restore Mode (DSRM)** password.
5. Click **Next**.

---

### Step 4b: DNS Options
- You may see a warning:  
  “A delegation for this DNS server cannot be created...”  
  → Ignore it and click **Next**.

---

### Step 4c: Additional Options
- Confirm the **NetBIOS name** (default is fine).  
- Click **Next**.

---

### Step 4d: Paths
- Keep default:

`Database folder: C:\Windows\NTDS`
`Log files folder: C:\Windows\NTDS`
`SYSVOL folder: C:\Windows\SYSVOL`

- Click **Next**.

---

### Step 4e: Review and Install
1. Review all settings.
2. Click **Install**.
3. The server will automatically **reboot** after installation.

---

## Step 5: Post-Installation Verification
1. Log in using your new **Domain Administrator** account:
	`DomainName\Administrator`
2. Open:
- **Server Manager → Tools → Active Directory Users and Computers**  
  → Confirm your new domain structure.
- **Server Manager → Tools → DNS**  
  → Verify your forward lookup zone is created.

---

## Step 6: Testing AD DS and DNS
Open **Command Prompt (cmd)** and run:
```cmd
nslookup
ping example.local
```
- If you get valid responses, your AD and DNS setup is working correctly.

## ✅ Result

🎉 Your Windows Server 2022 is now successfully configured as a **Domain Controller** with:

- Active Directory Domain Services (AD DS)
- DNS Server
- A new Forest and Domain (`example.local`)
- Static IP and fully functional authentication services

######  **Purpose:** _Windows Server 2022 AD DS + DNS Setup Guide
---

