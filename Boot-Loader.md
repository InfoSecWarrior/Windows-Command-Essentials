# 🚀 Boot Loader Guide

##  What is a Boot Loader?
A **boot loader** is a small piece of code that runs before any operating system is loaded. It is responsible for loading and starting the OS. Each operating system typically has its own boot loader.

---

## 🖥️ Windows Booting Files

-  bootmgr: The OS loader in Windows Vista and later. Found in the **System Reserved Partition** or the Windows installation drive.
-  Boot Configuration Database (BCD): Builds the OS selection menu in Windows Vista and later. Located at `\boot\BCD`.
-  winload.exe: Loads Windows in Vista and later. Located at `%SystemRoot%\system32\winload.exe`.
-  winresume.exe: Resumes Windows from hibernation. Located at `%SystemRoot%\system32\winresume.exe`.
-  ntldr: OS loader in Windows XP and earlier. Located at `C:\ntldr`.
-  boot.ini: Builds the OS selection menu in Windows XP and earlier. Located at `C:\boot.ini`.

---

## 💾 System Reserved Partition
Windows 7 and 8 create a special "System Reserved" partition when installed on a clean disk. This partition is hidden and consumes:
- **100MB** on Windows 7
- **350MB** on Windows 8

---

## ⚙️ Advanced Boot Menu Options

-  Safe Mode: Loads minimal drivers (keyboard, monitor, mouse, storage, etc.).
-  Safe Mode with Networking: Adds network support.
-  Safe Mode with Command Prompt: Starts Safe Mode but opens with a command prompt.
-  Enable Boot Logging: Logs the boot process for troubleshooting.
-  Enable VGA Mode: Starts Windows XP with a basic VGA driver.
-  Last Known Good Configuration: Uses the last successful boot settings.
-  Start Windows Normally: Boots without advanced startup options.
-  Reboot: Restarts the system.

---

## 🛠️ Bootloader Modification Tools

-  EasyBCD 2.2: A tool for modifying the Windows boot loader (Vista and later).

---

## 🔑 Accessing the EFI System Partition in Windows

### 🖥️ Method 1: Using Disk Management
1. Press `Win + R`, type `diskmgmt.msc`, and press **Enter**.
2. Locate the **EFI partition**.
3. Right-click it and select **Change Drive Letter and Paths**.
4. Click **Add**, assign a drive letter (e.g., `Z:`), and click **OK**.
5. Access it via **File Explorer** as `Z:\`.

### 🏁 Method 2: Using Command Prompt
```sh
diskpart
```
```sh
list disk
```
```sh
select disk X      # Replace X with the correct disk number
```
```sh
list partition
```
```sh
select partition Y  # Replace Y with the EFI partition
```
```sh
assign letter=Z
```
```sh
exit
```

### ⚡ Method 3: Using PowerShell
```sh
mountvol Z: /S
```

### 🖥️ Method 4: Accessing EFI Files via Command Line
```sh
cd /d Z:\EFI
```
```sh
dir
```

#### 🔄 Unmount EFI Partition
Using `diskpart`:
```sh
diskpart
```
```sh
select volume Z
```
```sh
remove letter=Z
```
```sh
exit
```
Or using `mountvol`:
```sh
mountvol Z: /D
```

---

## 🔧 Useful Commands for Boot Management

### 🖥️ Windows Boot Commands
```sh
bcdedit /enum                            # View current boot configuration
```
```sh
bcdedit /set {current} safeboot minimal  # Enable Safe Mode  
```
```sh
bcdedit /set {current} safeboot network  # Enable Safe Mode with Networking  
```
```sh
bcdedit /delete {ID}                     # Delete a boot entry  
```
```sh
bootrec /fixmbr                          # Repair Master Boot Record (MBR)  
```
```sh
bootrec /fixboot                         # Fix the boot sector  
```
```sh
bootrec /scanos                          # Scan for installed operating systems  
```
```sh
bootrec /rebuildbcd                      # Rebuild the boot configuration data  
```

### 🐧 Linux Boot (GRUB) Commands
```sh
sudo update-grub                        # Update GRUB boot configuration  
```
```sh
sudo grub-install /dev/sda              # Install GRUB to the primary disk  
```
```sh
cat /boot/grub/grub.cfg                 # View GRUB configuration  
```

---

## 📌 Conclusion
This guide provides an overview of **boot loaders**, boot options, and key commands for **Windows** and **Linux** systems. It serves as a reference for **troubleshooting** and **managing boot processes** effectively. 🚀
