Alright. I’ll give this **clean, step-by-step**, exactly how it’s done in **Windows Server 2022**, and I’ll also call out **what most people do wrong**.

You asked two things:

1. **How to share a folder**
    
2. **How to give proper permissions on shared resources**
    

This is the **correct enterprise way**.

---

## PART 1: How to SHARE a folder (network access)


![Image](https://learn-attachment.microsoft.com/api/attachments/19067-ff2.png?platform=QnA)

![Image](https://learn-attachment.microsoft.com/api/attachments/e2d47942-b1bb-4f73-9a81-d9429e07868d?platform=QnA)

### Step-by-step (GUI – correct method)

1. Right-click the folder (example: `D:\data`)
    
2. Click **Properties**
    
3. Go to **Sharing** tab
    
4. Click **Advanced Sharing**
    
5. ✅ Check **Share this folder**
    
6. Give a **Share name** (example: `data`)
    
7. Click **Permissions**
    

---

## PART 2: Share Permissions (KEEP THIS SIMPLE)

This is where people mess up.

### ✅ Correct Share Permission setup (BEST PRACTICE)

|Setting|Value|
|---|---|
|Group|`Everyone` **or** `IT Team`|
|Permission|✅ **Full Control**|
|Deny|❌ NEVER|

**Why?**  
Because **Share permissions are coarse**.  
You control real access using **NTFS permissions**, not here.

👉 Click **Apply → OK**

---

## PART 3: NTFS Permissions (REAL SECURITY)

![Image](https://www.ntfs.com/images/screenshots/ntfs-permissions.jpg)

![Image](https://www.vyapinsoftware.com/blog/wp-content/uploads/2010/09/ntfs_working_img1-1.png)

![Image](https://winaero.com/blog/wp-content/uploads/2019/01/Windows-10-Disable-Inherited-Permissions-1.png)

Now the important part.

### Step-by-step (NTFS)

1. Right-click folder → **Properties**
    
2. Go to **Security** tab
    
3. Click **Advanced**
    
4. Click **Disable inheritance**
    
5. Choose **Convert inherited permissions**
    
6. Remove unnecessary users/groups
    
7. Click **Add**
    

---

## PART 4: Give PROPER permissions (group-based)

❌ **Never assign permissions to users directly**  
✅ **Always use groups**

### Example (correct design)

|Group|Permission|Use case|
|---|---|---|
|`IT_RW`|Modify|IT team (work with files)|
|`IT_RO`|Read|View only|
|`Administrators`|Full Control|Admin|

### How to add:

1. **Add → Select a principal**
    
2. Choose the **group**
    
3. Select permission:
    
    - Read → view only
        
    - Modify → work with files
        
    - Full Control → admins only
        
4. Apply → OK
    

---

## PART 5: Final Access Rule (MEMORIZE THIS)

> **Final access = MOST RESTRICTIVE of (Share + NTFS)**

### Example:

- Share = Full Control
    
- NTFS = Read
    

➡️ User gets **Read only**

This is **by design**, not a bug.

---

## PART 6: Test the share (don’t skip)

From a client PC:

```
Run
\\ServerName\data
```

Test as a normal user:

- Open file
    
- Save file
    
- Rename file
    
- Delete file
    

If something fails:  
👉 Check **NTFS**, not Share

---

## COMMON MISTAKES (be honest with yourself)

❌ Using Deny in Share  
❌ Giving Full Control to users  
❌ Mixing random permissions in Share + NTFS  
❌ Not disabling inheritance  
❌ Assigning permissions user-by-user

If you do these, troubleshooting becomes hell.

---

## ONE-SCREEN SUMMARY (ADMIN RULES)

- Share permissions → **Simple**
    
- NTFS permissions → **Strict**
    
- Groups > Users
    
- Modify ≠ Full Control
    
- Always test with a normal user
    