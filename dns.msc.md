You’re looking at **`dsa.msc` (Active Directory Users and Computers)**. The **left sidebar is not decoration**—each container has a specific job. Misusing them is how people break AD. Here’s the **no-nonsense breakdown**, top to bottom.

---

## **Saved Queries**

- **What it is:** Dynamic searches (LDAP filters).
    
- **What it’s for:** Finding objects by condition (e.g., disabled users, computers not logged in for 90 days).
    
- **What it’s NOT:** A folder. Nothing is stored here.
    
- **Reality check:** Useful in real environments. In labs, people ignore it—fine.
    

---

## **Your Domain (e.g., `avadih.in`)**

- This is the **root namespace**.
    
- Everything under it is an **AD object**.
    
- You **don’t create users directly here** unless you like chaos. Use OUs.
    

---

## **Builtin**

- **What it contains:** Default AD **administrative groups** (Administrators, Backup Operators, etc.).
    
- **Rule:** **DO NOT TOUCH** unless you _know exactly_ why.
    
- **Mistake:** Adding users here “to make them admin.” That’s lazy and dangerous.
    

---

## **Computers**

- **What goes here:** Machines **automatically land here** when joined to the domain.
    
- **Problem:** No GPOs applied by default.
    
- **Correct practice:** Move computers into proper OUs after join.
    
- **Hard truth:** Leaving systems here = unmanaged environment.
    

---

## **Domain Controllers**

- **What it contains:** DC computer accounts **only**.
    
- **Special:** This OU has **critical GPOs** (security, replication).
    
- **Warning:** Mess this up and your domain dies. No exaggeration.
    

---

## **ForeignSecurityPrincipals**

- **What it is:** Objects from **trusted external domains**.
    
- **If you’re not using trusts:** Ignore it.
    
- **If it’s empty:** Normal for labs.
    

---

## **Managed Service Accounts**

- **What it’s for:** gMSA / MSA accounts used by services.
    
- **Not for human logins. Ever.**
    
- **If you don’t know it:** Don’t use it yet.
    

---

## **Users** ✅ (This is what you’re using)

- **Default container** for:
    
    - Domain Users
        
    - Built-in users (Administrator, Guest)
        
    - Security groups
        
- **Reality:** Microsoft still ships it, but **best practice = create your own OU**.
    
- **Your screenshot:** You created a user here. That’s acceptable for a lab.
    

---