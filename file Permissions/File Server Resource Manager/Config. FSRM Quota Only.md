## How FSRM is installed (quick)

1. **Server Manager**
2. Add Roles and Features
3. **File and Storage Services**
4. **File Server Resource Manager**

![Image](https://redmondmag.com/articles/2014/09/25/~/media/ECG/redmondmag/Images/2014/09/FSRM_Fig1.ashx)
5. Install → Tools → FSRM
    
# 0️⃣ Ground rules (read this or stop)

- **Do NOT apply this on C:** or app/data volumes
    
- **This is for user file shares only**
    
- **Quota = Hard OR Soft**
    
- **Screening = Active OR Passive**
    
- **Admins are exempt**(legally free)
# 1️⃣ Folder structure (clean and predictable)

Example:

```
C:\My_Quota 
	├── Some File 
	├── Some Folder
	└── etc.. 
```
You apply FSRM at **`C\My_Quota`**, not on random subfolders.
# 2️⃣ Create an enterprise-grade QUOTA TEMPLATE

**Why template first?**  
Because enterprise admins don’t configure quotas folder-by-folder like amateurs.
### Steps

1. Open **FSRM**
    
2. Go to **Quota Management → Quota Templates**
    
3. **Create Quota Template**
### Notifications (mandatory)

Configure **ALL** of these:(use Event Viewer tool)

- **85%** → Warning email to user + IT
    
- **95%** → Critical warning
    
- **100%** → Final alert (writes blocked)
# 3️⃣ Apply quota to `My_Quota`

1. **Quota Management → Quotas**
    
2. **Create Quota**
    
3. Path:
    
    `C:\My_Quota`
    
4. Choose **Auto apply template and create quotas on existing and new subfolders**
    
5. Select template: `MYQ_Hard_50GB`
    

✅ Now every subfolder inherits control  
