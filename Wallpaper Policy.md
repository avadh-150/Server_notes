# 📘 **How to Set a Desktop Wallpaper Using Group Policy (Windows Server 2022)**

This guide explains how to configure a **desktop wallpaper policy** using **Local Group Policy Editor** on Windows Server 2022.

---

## **1. Create Wallpaper Folder**

1. Open *_C:*_
    
2. Create a new folder named:
    
    ```
    Wallpaper
    ```
    
3. Place your wallpaper image inside this folder  
    (example: `wallpaper.jpg`)
    

---

## **2. Share the Folder**

1. Right-click the **Wallpaper** folder
    
2. Select **Properties**
    
3. Go to **Sharing → Advanced Sharing**
    
4. Enable **Share this folder**
    
5. Click **Permissions**
    
6. Make sure **Users** have **Read** permission
    

> Your network path will look like:

```
\\SERVERNAME\Wallpaper\wallpaper.jpg
```

---

## **3. Open Group Policy Editor**

Press **Win + R** → type:

```
gpedit.msc
```

Then navigate to:

```
User Configuration
  → Administrative Templates
    → Desktop
      → Desktop
        → Desktop Wallpaper
```

---

## **4. Configure Wallpaper Policy**

Double-click **Desktop Wallpaper** → set:

- **Enabled**
    
- **Wallpaper Name:**
    
    ```
    \\SERVERNAME\Wallpaper\wallpaper.jpg
    ```
    
- **Wallpaper Style:**  
    Choose one of:
    
    - Fill
        
    - Fit
        
    - Stretch
        
    - Center
        

Click **Apply → OK**

---

## **5. Update Group Policy**

On the client system, run:

```
gpupdate /force
```

or simply reboot.

---

## ✔ Notes

- Users **must** have read access to the wallpaper path.
    
- Use a shared UNC path — **local paths will not work for multiple clients**.
    
- For domain environments, apply this using **GPMC** instead of `gpedit.msc`.
    

---
