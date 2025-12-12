
📘 README — How to Create a User in Windows Server 2022
Overview
This guide explains how to create a local user account in Windows Server 2022 using two methods:
    • Local Users and Groups (lusrmgr.msc)
    • Server Manager → Computer Management
Both methods achieve the same result; choose whichever you prefer.

✅ METHOD 1 — Using lusrmgr.msc
    1. Press Win + R to open Run
    2. Type:
       lusrmgr.msc
       and press Enter
    3. In the left pane, select Users
    4. Right-click anywhere in the right pane and select New User
    5. Enter:
        ◦ Username
        ◦ Full Name
        ◦ Password
    6. Set any required options (e.g., User must change password at next logon)
    7. Click Create → Close

✅ METHOD 2 — Using Server Manager (Computer Management)
    1. Open Server Manager
    2. Go to the top-right: Tools
    3. Select Computer Management
    4. Navigate to:
       System Tools
       → Local Users and Groups
       → Users
    5. Right-click Users → New User
    6. Fill in username, password, and settings
    7. Click Create

✔️ Notes
    • These methods create a local user, not a domain user.
    • For domain users, use Active Directory Users and Computers (ADUC).

