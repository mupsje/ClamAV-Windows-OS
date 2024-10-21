# ClamAV-Windows-OS
Install CLAMAV on Windows OS

ClamAV is an open-source antivirus engine that can be installed on Windows, Linux, and Mac os. Here we learn how to install and configure it on Windows OS.
1. Download the ClamAV.
You can download the latest stable version of ClamAV from the below link. https://www.clamav.net/downloads

2. Install the ClamAV.
  - If you have downloaded the .msi version of the installation package, double-click on it and follow the instructions to install it.
  - If you have downloaded the .zip version of the installation package, unzip it into a directory of your windows machine. eg: C:\ClamAV

3. Configure the ClamAV.
Once you have installed ClamAV, navigate to the installation folder and find for conf_examples folder. You can see the clamd.conf.sample file and freshclam.conf.sample config file inside the conf_examples folder. Then copy those two files to the installation directory. (eg: C:\ClamAV)
  - Rename the clamd.conf.sample to **clamd.conf
  - Rename freshclam.conf.sample to freshclam.conf

  - Open clamd.conf with a text editor.
  - Comment/Remove the word Example in line number 8. (If you have commented out it, it should look like #Example)

      ![image](https://github.com/user-attachments/assets/a7f8d139-971d-4b3d-92ce-47d7515a9d3a)
    
  - Find for #LogFile "C:\Program Files\ClamAV\clamd.log" line and remove the leading # in it to enable the logging. Also, correct the ClamAV installation path in it.

      ![image](https://github.com/user-attachments/assets/12c2d60f-aa65-4977-9f51-2367eed13715)
  - Find for **TCPSocket 3310 and make sure it is not commented out.
    Also, find for **TCPAddr localhost and make sure it is not commented out.
  - Save the file and exit.




