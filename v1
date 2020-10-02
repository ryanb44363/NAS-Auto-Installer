# Installer and Setup for NAS Server (Raspbian)
# Adapted by Ryan Bellknapp - Made by Ksk Royal

# Link to Video: https://www.youtube.com/watch?v=s0Sc2n3gUqA&t=195s

# This has not been tested and may not be accurate.

#Prerequisites 
"""

Install Advanced IP Scanner To find the IP address Of your Raspberry Pi 4  - https://www.advanced-ip-scanner.com/

Download Raspbian Image - https://www.raspberrypi.org/downloads...

Burn it using Etcher - https://www.balena.io/etcher/

SD Formatter - https://www.sdcard.org/downloads/form...

Lan Drive - http://bit.ly/32HnobF


"""

import pyautogui, os, time, random

x = input("Would you like to run the following Pyautogui program?")

pyautogui.click()

time.sleep(.2)

pyautogui.typewrite("sudo apt-get update") # Updating the Pi Raspbian software.

time.sleep(15)

#--------------------------------------------------


pyautogui.typewrite("sudo apt-get install ntfs-3g") # Installing NTFS.

time.sleep(15)

pyautogui.typewrite("sudo apt-get install exfat-utils exfat-fuse") # Installing Exfat.

time.sleep(15)

pyautogui.typewrite("sudo apt-get install samba samba-common-bin") # Installing Samba Server.

time.sleep(15)

pyautogui.typewrite("sudo mkdir /NAS-LINKS") # Creating a directory within the root.

time.sleep(15)

pyautogui.typewrite("Sudo chmod 777 /NAS-LINKS") # Changing the permissions to the Server.

time.sleep(15)

pyautogui.typewrite("LSBLK") # Check the mounting point of the connected drive.

time.sleep(2)

y = input("What is the # associated with the drive?")

pyautogui.typewrite("sudo mount /dev/sda" + y + " /LINKS-NAS")

time.sleep(2)


#--------------------------------------------------

# Configuring Samba:

pyautogui.typewrite("sudo nano /etc/samba/smb.conf")

pyautogui.typewrite("LINKS-NAS")

pyautogui.press("enter")

time.sleep(2)

pyautogui.typewrite('comment = "This is the Fernbank LINKS NAS Server."')

pyautogui.press("enter")

time.sleep(2)

pyautogui.typewrite("path = /LINKS-NAS")

pyautogui.press("enter")

time.sleep(2)

pyautogui.typewrite("browseable = yes")

pyautogui.press("enter")

time.sleep(2)

pyautogui.typewrite("read only = no")

pyautogui.press("enter")

time.sleep(2)

pyautogui.typewrite("writable = yes")

pyautogui.press("enter")

time.sleep(2)

pyautogui.typewrite("create mask = 0777")

pyautogui.press("enter")

time.sleep(2)

pyautogui.typewrite("directory mask = 0777")

pyautogui.press("enter")

time.sleep(2)

pyautogui.typewrite("public = no")

pyautogui.press("enter")

time.sleep(2)

pyautogui.typewrite("force user = root")

#--------------------------------------------------

pyautogui.typewrite("Sudo adduser Ryan") # Adding user to the Server.

time.sleep(2)

pyautogui.typewrite("Sudo smbpasswd -a 4468") # Assigning a password to the new user.

time.sleep(2)

#--------------------------------------------------

pyautogui.typewrite("sudo /etc/init.d/smbd restart") # Restart Samba.

time.sleep(2)

pyautogui.typewrite("sudo /etc/init.d/nmbd restart") # Restart Samba.

#--------------------------------------------------

# Enabling Auto Mounting Drives Upon Rebooting.

pyautogui.typewrite("sudo nano /etc/fstab")

time.sleep(2)

pyautogui.press("enter")

time.sleep(2)

pyautogui.typewrite("/dev/sda1 /LINKS-NAS auto defaults, user 0 2")

#--------------------------------------------------

# Setting a Static IP for Server.

pyautogui.typewrite("Sudo nano /etc/dhcpcd.conf")

i = 1

for i in 75():
    pyautogui.press("keyDown")

pyautogui.typewrite("static ip_address = 192.168.0.23")

pyautogui.press("enter")

time.sleep(2)

pyautogui.typewrite("static routers = ...")

pyautogui.press("enter")

time.sleep(2)

pyautogui.typewrite("static domain_name servers = 192.168.0.1")

#--------------------------------------------------

quit()
