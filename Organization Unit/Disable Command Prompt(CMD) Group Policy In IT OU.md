Based on the video provided, here are the step-by-step instructions for blocking the Command Prompt (CMD) via Group Policy and verifying the policy implementation using the `gpresult` command.

---

## Part 1: Creating and Configuring the GPO

This section covers how to create a new Group Policy Object (GPO) to restrict access to the command prompt.

1. **Open Group Policy Management:** On your Windows Server (Domain Controller), open the Group Policy Management console.
    
2. **Create a New GPO:** * Right-click on your target Organizational Unit (OU) or the Domain.
    
    - Select **"Create a GPO in this domain, and Link it here..."**.
        
    - Name the GPO (e.g., `CMD Block Policy`).
        
3. **Edit the GPO:**
    
    - Right-click the newly created GPO and select **Edit**.
        
    - Navigate to: `User Configuration` > `Policies` > `Administrative Templates` > `System`.
        
4. **Enable the Restriction:**
    
    - In the right-hand pane, find and double-click **"Prevent access to the command prompt"**.
        
    - Select the **Enabled** radio button.
        
    - Under the Options section, you can choose "Yes" or "No" for **"Disable the command prompt script processing also?"** (Selecting "No" allows logon scripts to still run).
        
    - Click **Apply** and then **OK**.
        

---

## Part 2: Forcing a Policy Update

To ensure the changes take effect immediately on the client machine:

1. **Log in to the Client Machine:** Switch to the target PC (e.g., PC1) and log in as a domain user.
    
2. **Update Policies:** * Open the Run dialog (**Win + R**), type `cmd`, and press Enter.
    
    - In the command prompt, type: `gpupdate /force` and hit Enter.
        
    - _Note: If the policy has already applied, you may receive a message stating CMD is disabled immediately upon opening it._
        

---

## Part 3: Verifying the Policy (Verification Steps)

There are two primary ways to verify that the policy is active.

### Method A: Direct Testing

1. Try to open the **Command Prompt** from the Start menu or the Run dialog.
    
2. If successful, the window should open with the message:
    
    > **"The command prompt has been disabled by your administrator. Press any key to continue..."**
    
3. Pressing a key will automatically close the window, confirming the block is active.
    
