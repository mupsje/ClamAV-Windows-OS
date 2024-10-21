# ClamAV-Windows-OS
Install CLAMAV on Windows OS

ClamAV is an open-source antivirus engine that can be installed on Windows, Linux, and Mac os. Here we learn how to install and configure it on Windows OS.

**1. Download the ClamAV.**
You can download the latest stable version of ClamAV from the below link. https://www.clamav.net/downloads

**2. Install the ClamAV.**
  - If you have downloaded the **.msi** version of the installation package, double-click on it and follow the instructions to install it.
  - If you have downloaded the **.zip** version of the installation package, unzip it into a directory of your windows machine. eg: *C:\ClamAV*

**3. Configure the ClamAV.**
Once you have installed ClamAV, navigate to the installation folder and find for `conf_examples` folder. You can see the `clamd.conf.sample` file and `freshclam.conf.sample` config file inside the __conf_examples__ folder. Then copy those two files to the installation directory. (eg: C:\ClamAV)
  - Rename the clamd.conf.sample to `clamd.conf`
  - Rename freshclam.conf.sample to `freshclam.conf`
    
  **Modify clamp.conf**

  - Open clamd.conf with a text editor.
  - Comment/Remove the word Example in line number 8. (If you have commented out it, it should look like #Example)

      ![image](https://github.com/user-attachments/assets/a7f8d139-971d-4b3d-92ce-47d7515a9d3a)
    
  - Find for #LogFile "C:\Program Files\ClamAV\clamd.log" line and remove the leading # in it to enable the logging. Also, correct the ClamAV installation path in it.

      ![image](https://github.com/user-attachments/assets/12c2d60f-aa65-4977-9f51-2367eed13715)
    
  - Find for `TCPSocket 3310` and make sure it is not commented out.
    Also, find for `TCPAddr localhost` and make sure it is not commented out.
  - Save the file and exit.

  **Modify freshclam.conf**

  - Open `freshclam.conf` with a text editor.
  - Comment/Remove the word `Example` in line number 8. (If you have commented out it, it should look like `#Example`)

      ![image](https://github.com/user-attachments/assets/5c9086cc-3b2c-42b0-ac8a-4de7e0b07dd2)

  - Find for `#UpdateLogFile "C:\Program Files\ClamAV\freshclam.log"` line and remove the leading `#` in it to enable the logging. Also, correct the ClamAV installation path in it.

      ![image](https://github.com/user-attachments/assets/c6f74b40-5d54-4b88-a90a-a0f7da3cbf07)

  - Find for `#DatabaseDirectory "C:\Program Files\ClamAV\database"` line and remove the leading `#` in it to enable the logging. Also, correct the ClamAV installation path in it.

      ![image](https://github.com/user-attachments/assets/8729fcf9-7749-4867-b4f1-3eeb89bc1d5a)

  - Save the file and exit.
    
**4. Install ClamAV as a windows service.**
Open the Windows Command Prompt in Administrator Mode and navigate to the installation directory *(eg: C:\ClamAV)*.

Run the following command to install as a service.
`clamd.exe --install`

![image](https://github.com/user-attachments/assets/cb78ab0c-2f8a-4f9a-9cc3-59ddb94bf299)


**5. Update the ClamAV database.**
Open the Windows Command Prompt in Administrator Mode and navigate to the installation directory *(eg: C:\ClamAV)*.

Run the following command to update the ClamAV database.
`freshclam.exe`

![image](https://github.com/user-attachments/assets/897a1fa1-456e-4b13-a417-c4c1ad57bfd2)

**6. Running the ClamAV service.**

To install the services, first use the command:
```
clamd --install-service
```
Then use bash```net start clamd``` and ```net stop clamd``` to start/stop the service.

To uninstall the service, use:
```
clamd --uninstall-service
```
Services can also be managed via the Services application on Windows.

Open the Windows Services (execute `services.msc` command in the run window to open the windows services) and start the ClamAV service,
Service name: `ClamAV ClamD`

![image](https://github.com/user-attachments/assets/0aacdd8c-dcc8-412d-b193-29810d64a5db)

Now the ClamAV service is up and running.






from: https://medium.com/aeturnuminc/clamav-install-on-windows-5971358b2bc7







