Based on the video provided, here is the step-by-step guide to adding a 10GB backup drive to a Windows Server 2022 virtual machine using VMware Workstation.

---
To install **Windows Server Backup** on Windows Server 2022, follow these step-by-step instructions based on the provided video:

### **Step 1: Open the Add Roles and Features Wizard**

- Open the **Server Manager** dashboard.
    
- Click on **Manage** in the top-right corner and select **Add Roles and Features**.
    
- On the **Before you begin** screen, review the prerequisites and click **Next**.
    

### **Step 2: Select Installation and Server**

- **Installation Type**: Select **Role-based or feature-based installation** and click **Next**.
    
- **Server Selection**: Ensure your local server is selected from the server pool and click **Next**.
    
- **Server Roles**: You do not need to add any roles for this task; simply click **Next** to proceed to the features section.
    

### **Step 3: Enable Windows Server Backup Feature**

- In the **Features** list, scroll down to find **Windows Server Backup**.
    
- Check the box next to **Windows Server Backup**.
    
- Click **Next**.
    

### **Step 4: Confirm and Install**

- On the **Confirmation** screen, verify that "Windows Server Backup" is listed.
    
- Click **Install**.
    
- Wait for the installation to complete. Once finished, click **Close**.
    

### **Step 5: Verify the Installation**

- In **Server Manager**, click on **Tools** in the top-right corner.
    
- Select **Windows Server Backup** from the dropdown menu to open the application.
    
- The application will load, and you can now see the "Local Backup" console where you can manage your backup schedules and tasks.
    

Based on the video provided, here is a step-by-step guide on how to configure a **Scheduled Backup** and perform an **On-Demand Backup** using **Windows Server Backup (WSB)** on Windows Server 2022.

---

## Part 1: Configuring a Backup Schedule

This process sets up an automatic, recurring backup of specific data.

1. **Open Windows Server Backup:** Navigate to **Tools** > **Windows Server Backup** in Server Manager.
    
2. **Start the Wizard:** In the right-hand **Actions** pane, click on **Backup Schedule...** and click **Next** on the Getting Started page.
    
3. **Select Backup Configuration:** Choose **Custom** (to select specific files or folders) and click **Next**.
    
4. **Select Items for Backup:**
    
    - Click **Add Items**.
        
    - Expand the drive (e.g., Local Disk C:) and check the box for the specific folder you want to back up (in the video, the user selects the **"C data"** folder).
        
    - Click **OK**, then click **Next**.
        
5. **Specify Backup Time:** Choose how often and at what time the backup should run (e.g., Once a day at 9:00 PM). Click **Next**.
    
6. **Select Destination Type:** Select **Back up to a hard disk that is dedicated for backups (recommended)**. Click **Next**.
    
7. **Select Destination Disk:**
    
    - Click **Show All Available Disks...**.
        
    - Select your target backup disk (e.g., VMware Virtual Disk).
        
    - Click **OK**, then select the disk in the main list and click **Next**.
        
    - A warning will appear stating the disk will be formatted. Click **Yes**.
        
8. **Confirmation:** Review your settings and click **Finish**. Once the summary shows success, click **Close**.
    

---

## Part 2: Performing an On-Demand Backup

This allows you to run a backup immediately using the settings you just created.

1. **Start Backup:** In the right-hand **Actions** pane, click **Backup Once...**.
    
2. **Backup Options:** Choose **Scheduled backup options** (this uses the items and settings you configured in Part 1). Click **Next**.
    
3. **Confirmation:** Review the backup details and click **Backup**.
    
4. **Monitor Progress:** A window will show the status (e.g., "Creating shadow copy of volumes").
    
5. **Complete:** Once the status changes to **Completed**, click **Close**. You will now see the successful backup listed in the **Messages** and **Status** sections of the main dashboard.
    

---
