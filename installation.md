# Installation Guide for FouzderIT Business Suite

Follow these steps to install the FouzderIT Business Suite on your hosting server. This guide assumes you have access to your hosting control panel and basic familiarity with managing files and databases.

#### Step-by-Step Installation Instructions

1. **Download the Business Suite**
   
   - Login to the [FouzderIT client portal](https://hr.fouzderit.com).
   - Locate and download the latest version of the FouzderIT Business Suite ZIP file.

2. **Access Hosting Control Panel**
   
   - Login to your hosting control panel and open the **File Manager**.
   - Navigate to the document root of the domain or sub-domain where you want to install FouzderIT Business Suite. This is typically the `public_html` folder for the primary domain.

3. **Upload the FouzderIT ZIP File**
   
   - In the **File Manager**, upload the ZIP file you downloaded in Step 1.
   - Once the upload is complete, close the upload window.

4. **Extract the Files**
   
   - Locate the uploaded ZIP file in **File Manager**. If you do not see it, refresh the page.
   - Select the ZIP file, then click the **Extract** button to unpack the contents.

5. **Set Up the Database**
   
   - Return to your control panel and open **MySQL Databases**.
   - Create a new database and a new database user. Be sure to write down the database name, user, and password, as you’ll need them during the installation.
   - Add the new user to the database and grant **All Privileges**.

6. **Begin Installation**
   
   - Open your browser and navigate to the installation URL (the URL of your domain or sub-domain where you extracted the files).
   - Enter the database details, including the host (usually `localhost`), database name, user, and password.

7. **Create Admin User**
   
   - Click **Next** to continue. The installer will prompt you to set up an initial user account. This will be your admin account, so choose a secure password and memorable login details.

8. **Complete Installation**
   
   - After entering the admin user information, click **Finish** to complete the installation.
   - Your FouzderIT Business Suite installation is now complete, and you can begin configuring and using the platform.