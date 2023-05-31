# Permanently Mount a Windows NTFS Storage in Ubuntu
1) Install the NTFS-3G driver.
2) Create a mount point for the NTFS partition.
3) Edit the /etc/fstab file to mount the NTFS partition at boot.

  ## Install the NTFS-3G driver

  The NTFS-3G driver is a free and open-source software that allows you to read and write to NTFS partitions from Linux. To install the NTFS-3G driver, 
  open a terminal and run the following command:
  ```
  sudo apt install ntfs-3g
  ```

  ## Create a mount point for the NTFS partition

  A mount point is a directory on your Linux system where you can mount a filesystem. 
  To create a mount point for the NTFS partition, open a terminal and run the following command:
  
  ```
  sudo mkdir /mnt/ntfs (or) sudo mkdir /media/bp
  ```
  ## List the disk partition
  
  ```
  sudo fdisk -l
  ```
    
   ## Edit the /etc/fstab file to mount the NTFS partition at boot

  The /etc/fstab file is a configuration file that contains information about filesystems that should be mounted at boot. 
  To edit the /etc/fstab file, open it in a text editor.
  
  ```
  sudo nano /etc/fstab (or) sudo vim /etc/fsrab
  ```
  
  ### Add the following line to the /etc/fstab file:
  
  ```
  /dev/sdb2 /mnt/ntfs ntfs rw,errors=remount-ro 0 0 (or) /dev/sdb2 /media/bp ntfs rw,errors=remount-ro 0 0
  ```
  This line tells the system to mount the NTFS partition at boot, with read/write permissions. 
  The errors=remount-ro option tells the system to remount the partition read-only if there are any errors.

  Save the /etc/fstab file and exit the text editor.


  
