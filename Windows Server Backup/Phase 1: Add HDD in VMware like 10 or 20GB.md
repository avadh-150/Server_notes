
## Phase 1: Adding the Virtual Hardware

Before adding the drive in Windows, you must first "plug in" the virtual hardware through the VMware settings.

1. **Open VM Settings:** With the virtual machine powered off, click on **Edit virtual machine settings**.

2. **Add Hardware:** Click the **Add...** button at the bottom of the Hardware tab.

   <img width="1202" height="616" alt="image" src="https://github.com/user-attachments/assets/5204e0ae-577f-44a0-9f97-acacadabf6cf" />


3. **Select Hard Disk:** Choose **Hard Disk** from the list and click **Next**.

   <img width="739" height="575" alt="image" src="https://github.com/user-attachments/assets/0991d999-da1d-42f3-9259-382c1ee10500" />

4. **Disk Type:** Select the recommended disk type (e.g., **NVMe**) and click **Next**.
 
   <img width="571" height="405" alt="image" src="https://github.com/user-attachments/assets/3e9d977c-1a52-4714-9770-59960ae62e97" />
    
5. **Create Disk:** Select **Create a new virtual disk** and click **Next**.

  <img width="532" height="421" alt="image" src="https://github.com/user-attachments/assets/a8a29db8-953c-42a2-806a-3465edc9028c" />
    
6. **Set Capacity:** * Change the "Maximum disk size (GB)" to **10.0**.
    
   <img width="533" height="547" alt="image" src="https://github.com/user-attachments/assets/426ab4de-5aee-461d-ae36-2bb374743d4f" />

7. Select **Store virtual disk as a single file**. Click **Next**.

   <img width="540" height="542" alt="image" src="https://github.com/user-attachments/assets/36c2da5e-1e5d-453c-8ff0-318c7ffbb373" />
   
8. **Disk File Name:** Keep the default file name or choose a location, then click **Finish**.

    <img width="739" height="575" alt="image" src="https://github.com/user-attachments/assets/81b469f4-3a77-4ede-995e-b9dc86f51692" />

11. **Save Changes:** Click **OK** on the Virtual Machine Settings window to confirm.

    <img width="1509" height="739" alt="image" src="https://github.com/user-attachments/assets/f0ce8b0c-afce-4e3e-989e-d8090c2e14aa" />

---

# Phase 2: Initializing the Disk in Windows Server
    Once the hardware is added, you must tell Windows how to use it.

1. **Power On:** Start the virtual machine and log in as an **Administrator**.
    
2. **Open Disk Management:** 
    
    - Right-click the **Start button** or search for "Disk Management."
        
    - Alternatively, type `diskmgmt.msc` in the search bar and press Enter.
        
3. **Initialize Disk:** A popup labeled "Initialize Disk" should appear automatically detecting the new 10GB drive (Disk 1).
    
    - Select **GPT (Guid Partition Table)** and click **OK**.

      <img width="699" height="527" alt="image" src="https://github.com/user-attachments/assets/8ae59c5e-6615-4cc9-8ca1-ee915ce830ea" />  

4. **Create New Volume:**
    
    - Find the area labeled **10.00 GB Unallocated** (marked with a black bar).
        
    - Right-click the unallocated space and select **New Simple Volume...**.

      <img width="698" height="550" alt="image" src="https://github.com/user-attachments/assets/a0029afa-637d-48da-9e5c-a4fd614da277" />
        
5. **New Simple Volume Wizard:**

      <img width="698" height="550" alt="image" src="https://github.com/user-attachments/assets/9b13a851-3282-4b68-91d9-595220e187ab" />

    - **Size:** Leave it at the maximum amount (approx. 10239 MB). Click **Next**.
        
    - **Drive Letter:** Assign a letter (the video uses **E**). Click **Next**.
        
    - **Format Settings:**
        
        - File system: **NTFS**.
            
        - Volume label: Rename this to **Back-UP Drive**.

          <img width="1024" height="509" alt="image" src="https://github.com/user-attachments/assets/e28576cb-3d93-43c7-bc61-26dc6c3b6564" />

    - Click **Next**, then **Finish**.

      <img width="648" height="497" alt="image" src="https://github.com/user-attachments/assets/6a4b967e-a554-44f7-b72e-7fe2b7f1fa2e" />

