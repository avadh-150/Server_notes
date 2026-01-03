To configure a **Desktop Wallpaper Policy** on your Domain Controller (DC) for a client PC (PC1) as shown in the video tutorials, follow these exact steps:

### Step 1: Prepare and Share the Wallpaper

For a GPO to work, the client machine must be able to "reach" the image file over the network.

1. **Create a Folder:** On your DC, create a folder (e.g., `C:\Wallpaper`).
    
2. **Add the Image:** Put your wallpaper image (e.g., `wp.jpg`) inside that folder.
    
3. **Share the Folder:**
    
    - Right-click the folder > **Properties** > **Sharing** tab > **Advanced Sharing**.
        
    - Check **Share this folder**.
        
    - Click **Permissions**, ensure **Everyone** has **Read** access.
        
    - Click **OK** twice.
        
4. **Copy the Network Path:** Note the path, which should look like `\\DC-NAME\Wallpaper\wp.jpg`.
    

---

### Step 2: Create the Group Policy Object (GPO)

1. **Open Management Tool:** Open **Server Manager** > **Tools** > **Group Policy Management**.
    
2. **Create GPO:**
    
    - Expand your forest and domain.
        
    - Right-click your **Domain Name** or a specific **OU** (where PC1’s users are located).
        
    - Select **Create a GPO in this domain, and Link it here...**.
        
    - Name it `Wallpaper_Policy` and click **OK**.
        

---

### Step 3: Configure the Policy Settings

1. **Edit the GPO:** Right-click the new `Wallpaper_Policy` and click **Edit**.
    
2. **Navigate to the Setting:**
    
    - Go to: **User Configuration** > **Policies** > **Administrative Templates** > **Desktop** > **Desktop**.
        
3. **Enable Wallpaper:**
    
    - On the right side, double-click **Desktop Wallpaper**.
        
    - Select **Enabled**.
        
    - **Wallpaper Name:** Paste the **UNC Network Path** from Step 1 (e.g., `\\DC-NAME\Wallpaper\wp.jpg`).
        
    - **Wallpaper Style:** Choose **Fill** or **Center** (the video uses Center/Fill for best results).
        
    - Click **Apply** and **OK**.
        

---

### Step 4: Verify on PC1

1. Force Update: On PC1, open the Command Prompt and type:
    
    gpupdate /force
    
2. **Log Off/On:** The wallpaper usually requires a fresh login. **Sign out** of PC1 and sign back in.
    
3. **Result:** The desktop background should now be the image you chose. If you right-click the desktop to change it manually, you will see a message: _"Some settings are managed by your organization,"_ meaning the policy is working.
    

**Would you like me to show you how to also lock the screen background so users can't change that either?**