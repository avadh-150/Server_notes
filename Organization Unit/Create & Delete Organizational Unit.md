Based on the video provided, here are the step-by-step instructions for creating and properly deleting an **Organizational Unit (OU)** in Active Directory on Windows Server 2022.

---

## Part 1: How to Create an OU

1. Open **Active Directory Users and Computers**.
    
2. **Right-click** on the domain name or the container where you want to place the new OU.
    
3. Navigate to **New** > **Organizational Unit**.
    
4. In the "New Object – Organizational Unit" dialog box:
    
    - **Name:** Type the name for your OU (e.g., "IT" or "HR").
        
    - **Protection:** Ensure the box **"Protect container from accidental deletion"** is checked (this is enabled by default to prevent mistakes).
        
5. Click **OK**. Your new OU will now appear in the list.
    

---

## Part 2: How to Delete an OU

If you try to delete an OU immediately by right-clicking it and selecting **Delete**, you will likely receive an error message: _"You do not have sufficient privileges to delete it, or this object is protected from accidental deletion."_

To delete it, you must first disable that protection:

1. Click on the **View** menu at the top of the Active Directory window.
    
2. Select **Advanced Features**. (The screen will refresh and show more hidden containers).
    
3. **Right-click** the OU you want to delete and select **Properties**.
    
4. Click on the **Object** tab.
    
5. **Uncheck** the box that says **"Protect object from accidental deletion"**.
    
6. Click **Apply** and then **OK**.
    
7. Now, **right-click** the OU again, select **Delete**, and click **Yes** to confirm. The OU will now be successfully removed.
    

---

### Pro-Tip

After deleting the OU, it is a good idea to go back to the **View** menu and uncheck **Advanced Features** to simplify your workspace and prevent accidental changes to system containers.

Would you like me to explain how to move users into your new OU?