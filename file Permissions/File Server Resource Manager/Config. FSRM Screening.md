# 1️⃣ Create FILE SCREENING TEMPLATES (this matters)
---
## 🚫 Template 1: Block media & junk (users abuse this)

**Name:** `MYQ_Block_Media`

**Block these extensions:**

`*.mp4 *.mkv *.avi *.mov *.mp3 *.iso *.zip *.rar`

**Type:** Active screening  
**Notification:** **Event Viewer** tool

**Why:**  
Media files destroy storage faster than anything else.

---
## 🚫 Template 2: Block executables (security control)

**Name:** `MYQ_Block_Executables`

**Block extensions:**

`*.exe *.msi *.bat *.cmd *.ps1 *.vbs *.js`

**This is NOT optional.**  
Allowing executables on user shares is how ransomware spreads laterally.

---

# 2️⃣ Apply file screening to `My_Quota`

1. **File Screening Management → File Screens**
    
2. **Create File Screen**
    
3. Path:
    
    `C:\My_Quota`
    
4. Apply **both templates**
    
    - `MYQ_Block_Media`
        
    - `MYQ_Block_Executables`
        
5. Mode: **Active**
    

Result:

- Files blocked instantly
    
- Event logged

---

# 3️⃣ Storage Reports (weekly, automated)

Enable:

- **Largest files**
    
- **Files by type**
    
- **Quota usage**
    

Schedule: **Weekly**  
Export: Email PDF to IT

Admins who don’t review reports are blind.

---

# 4️⃣ Testing checklist (DO THIS)

From a normal user account:

- ✅ Create normal files
    
- ❌ Copy `.mp4` → should fail
    
- ❌ Copy `.exe` → should fail
    
- ❌ Exceed quota → write blocked
    
- ✅ Admin folder allows scripts
    

If any test fails → **policy is wrong**

---

# 5️⃣ What interviewers REALLY want to hear

> “I used hard quotas with Custom templates, active file screening to block media and executables, **Event Viewer** alerts at 85/95/100 percent, and admin exceptions. This prevented disk exhaustion and reduced malware risk.”

Anything less = lab knowledge, not enterprise readiness.