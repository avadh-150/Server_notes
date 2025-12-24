Good — this is the **right level of detail**. Below is a **clean, exhaustive, copy-paste-ready table** for **NTFS FILE permissions** showing **exactly what a user can and cannot do**.  
No assumptions. No shortcuts.

---

## NTFS **FILE** Permissions — Action Matrix (Windows Server 2022)

> Applies to **files only** (not folders)

| Permission         | Read file (open) | Run / Execute file | Copy /Past file | Rename file | Modify content | Save changes | Delete file | Change permissions | Take ownership |
| ------------------ | ---------------- | ------------------ | --------------- | ----------- | -------------- | ------------ | ----------- | ------------------ | -------------- |
| **Read**           | ✅ Yes            | ✅ Yes              | ✅ Yes           | ❌ No        | ❌ No           | ❌ No         | ❌ No        | ❌ No               | ❌ No           |
| **Write**          | ❌ No             | ❌ No               | ❌ No            | ❌ No        | ✅ Yes          | ✅ Yes        | ❌ No        | ❌ No               | ❌ No           |
| **Read & Execute** | ✅ Yes            | ✅ Yes              | ✅ Yes           | ❌ No        | ❌ No           | ❌ No         | ❌ No        | ❌ No               | ❌ No           |
| **Modify**         | ✅ Yes            | ✅ Yes              | ✅ Yes           | ✅ Yes       | ✅ Yes          | ✅ Yes        | ✅ Yes       | ❌ No               | ❌ No           |
| **Full Control**   | ✅ Yes            | ✅ Yes              | ✅ Yes           | ✅ Yes       | ✅ Yes          | ✅ Yes        | ✅ Yes       | ✅ Yes              | ✅ Yes          |

---

### ⚠️ Important clarifications (read carefully)

- **Copy** requires **Read**, not Write
    
- **Rename** = Delete + Create → requires **Modify**
    
- **Save changes** requires **Write**
    
- **Delete** requires **Modify**
    
- **Change permissions / Ownership** → **ONLY Full Control or Owner**
    

* Write works **only if the app already has the file open** or permissions allow overwrite.

---

## NTFS **Special File Actions** (what really happens under the hood)

|Action|Required Permission|
|---|---|
|Open a file|Read|
|Execute `.exe`, `.ps1`, `.bat`|Read & Execute|
|Copy file to another location|Read|
|Overwrite file|Write|
|Rename file|Modify|
|Delete file|Modify|
|Change ACL|Full Control|
|Take ownership|Full Control or current Owner|

---

## Real-world examples (interview-grade)

**Scenario 1:**  
User has **Read** → Can open & copy → ❌ cannot save or delete

**Scenario 2:**  
User has **Write only** → Can overwrite file → ❌ cannot open or copy

**Scenario 3:**  
User has **Modify** → Can do everything except security changes

**Scenario 4:**  
User has **Full Control** → God mode (dangerous if misused)

---

## Common admin mistakes (don’t make these)

❌ Thinking Write allows delete  
❌ Thinking Read allows rename  
❌ Giving Full Control “just to fix quickly”  
❌ Assigning permissions directly to users

---

## One-line truths (memorize)

- **Read = see**
    
- **Write = change content**
    
- **Modify = change + delete**
    
- **Full Control = security control**
 