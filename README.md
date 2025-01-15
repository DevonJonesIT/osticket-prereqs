# osTicket - Prerequisites and Installation Guide

This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.

---

## **Video Demonstration**

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com/results?search_query=how+to+install+osticket+with+prerequisites)

---

## **Environments and Technologies Used**

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

---

## **Operating Systems Used**

- Windows 10 (21H2)

---

## **Prerequisites**

Before beginning, ensure you have the following:
1. **Internet Information Services (IIS)** enabled
2. **Web Platform Installer** (or manual PHP, MySQL installation)
3. **MySQL Database Server** installed and configured
4. **Microsoft Visual C++ Redistributable** installed
5. The latest version of **osTicket** downloaded

---

## **Installation Steps**

### **Step 1: Enable IIS (Internet Information Services)**

1. Open **Control Panel** -> **Programs** -> **Turn Windows Features On or Off**.
2. Scroll down and check **Internet Information Services (IIS)**.
3. Expand **IIS** and enable the following sub-components:
   - **CGI** (Common Gateway Interface)
   - **Static Content**
   - **Default Document**
4. Click **OK** and wait for Windows to apply the changes.
5. Verify IIS is working by opening a browser and navigating to `http://localhost/`. You should see the IIS welcome page.

---

### **Step 2: Install Web Platform Installer**

1. Download the **Web Platform Installer** from [Microsoft](https://www.microsoft.com/web/downloads/platform.aspx).
2. Open the Web Platform Installer and search for:
   - **PHP 7.4+**
   - **MySQL Windows Driver**
   - **Recommended IIS Components** (if not already installed)
3. Click **Install** and wait for the components to install.
4. Restart your machine if prompted.

**Note:** If you prefer, you can manually install PHP by downloading it from [php.net](https://www.php.net/).

---

### **Step 3: Install MySQL (Database Server)**

1. Download **MySQL Community Server** from [MySQL's Official Site](https://dev.mysql.com/downloads/mysql/).
2. Run the installer and choose **Developer Default** for the setup type.
3. During the setup, create a **new user** and set a **password** for your MySQL database.
4. Confirm that MySQL is running by opening the **MySQL Workbench** or using the `mysql -u root -p` command in the command line.

---

### **Step 4: Install Microsoft C++ Redistributable**

1. Download **Microsoft Visual C++ Redistributable** from the [Microsoft Download Center](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170).
2. Run the installer (`VC_redist.x64.exe` for 64-bit systems).
3. Follow the prompts to complete the installation.

---

### **Step 5: Install osTicket**

1. Download the latest **osTicket** from [osTicket.com](https://osticket.com/download).
2. Extract the contents of the zip file to the folder `C:\inetpub\wwwroot\osticket`.
3. Open your browser and navigate to:  
   `http://localhost/osticket/setup.php`
4. Fill in the required details:
   - **Database Host:** `localhost`
   - **Database Name:** The MySQL database you created earlier
   - **Database User:** The MySQL user you created earlier
5. Click **Install Now** to complete the installation.
6. After the installation is complete, delete the `setup` folder inside the osTicket directory for security purposes.

---

## **Final Configuration**

- Configure your email settings (SMTP and IMAP) if you want to enable email-based ticketing.
- Run a test by creating and closing a sample ticket to ensure everything is working correctly.
- If using Azure VMs, consider setting up **Network Security Groups (NSGs)** to allow incoming HTTP traffic.

---

## **Additional Resources**

- [osTicket Official Documentation](https://docs.osticket.com/)
- [osTicket Community Forums](https://forum.osticket.com/)
