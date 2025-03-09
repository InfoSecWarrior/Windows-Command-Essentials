# 🔥 Windows Firewall Management

## 🔧 Windows Firewall Service Management

### 📌 Check Windows Firewall Service Status

- Retrieves the configuration details of the Windows Firewall service:
  ```cmd
  sc qc MpsSvc
  ```

- Checks the current status of the Windows Firewall service:
  ```cmd
  sc query MpsSvc
  ```

### ▶️ Start and ⏹️ Stop Windows Firewall Service

- Stops the Windows Firewall service:
  ```cmd
  sc stop MpsSvc
  ```

- Starts the Windows Firewall service:
  ```cmd
  sc start MpsSvc
  ```

## ⚙️ Configuring Windows Firewall Using `netsh`

### 🛠️ Access Windows Firewall Settings

- Opens the Windows Firewall settings in the command-line interface:
  ```cmd
  netsh advfirewall firewall
  ```

### ❓ Display Help for Firewall Commands

- Displays the help menu for Windows Firewall advanced settings:
  ```cmd
  netsh advfirewall /?
  ```

- Shows available options for displaying firewall settings:
  ```cmd
  netsh advfirewall show /?
  ```

### 📜 Display Firewall Profiles

- Displays the current firewall profile:
  ```cmd
  netsh advfirewall show currentprofile
  ```

- Shows the firewall settings for the public profile:
  ```cmd
  netsh advfirewall show publicprofile
  ```

- Shows the firewall settings for the private profile:
  ```cmd
  netsh advfirewall show privateprofile
  ```

- Displays settings for all firewall profiles:
  ```cmd
  netsh advfirewall show allprofiles
  ```

### 🚦 Enable or Disable Windows Firewall

- Disables the Windows Firewall:
  ```cmd
  netsh firewall set opmode disable
  ```

- Enables the Windows Firewall:
  ```cmd
  netsh firewall set opmode enable
  ```

- Turns off the firewall for all profiles:
  ```cmd
  netsh advfirewall set allprofiles state off
  ```

- Turns on the firewall for all profiles:
  ```cmd
  netsh advfirewall set allprofiles state on
  ```

### 🔍 View and Modify Firewall Rules

- Displays help for firewall rule commands:
  ```cmd
  netsh advfirewall firewall /?
  ```

- Dumps the current firewall configuration:
  ```cmd
  netsh advfirewall firewall dump
  ```

- Opens TCP port 23 for Telnet Server:
  ```cmd
  netsh firewall add portopening tcp 23 "Telnet Server"
  ```

- Displays the current state of the firewall:
  ```cmd
  netsh firewall show state
  ```

- Adds a rule to allow inbound FTP client connections:
  ```cmd
  netsh advfirewall firewall add rule name="Permit FTP Client" dir=in action=allow enable=yes profile=any program=%SystemRoot%\System32\ftp.exe
  ```

- Displays all configured firewall rules:
  ```cmd
  netsh advfirewall firewall show rule
  ```

- Displays details of the "Permit FTP Client" rule:
  ```cmd
  netsh advfirewall firewall show rule name="Permit FTP Client"
  ```

### ➕ Adding and ➖ Removing Specific Rules

- Allows inbound RDP traffic on port 3389:
  ```cmd
  netsh advfirewall firewall add rule name="RDP" dir=in action=allow enable=yes profile=any protocol=TCP localport=3389
  ```

- Deletes the "RDP" rule:
  ```cmd
  netsh advfirewall firewall delete rule name="RDP" dir=in
  ```

### ✏️ Modifying Firewall Rules

- Modifies the "HTTP 80" rule to allow traffic on additional ports (80, 81, 82, 83):
  ```cmd
  netsh advfirewall firewall set rule name="HTTP 80" new localport=80,81,82,83 action=allow
  ```

## 🖥️ Managing Windows Firewall Using PowerShell

- Lists all firewall rules:
  ```powershell
  get-netfirewallrule -all
  ```

- Lists all firewall rules from the configurable service store:
  ```powershell
  get-netfirewallrule -policystore configurableservicestore -all
  ```

## 🛡️ Windows Defender Antivirus Management

### 📋 Check Windows Defender Status

- Checks the status of Windows Defender:
  ```cmd
  sc query windefend
  ```

- Retrieves the configuration details of Windows Defender:
  ```cmd
  sc qc windefend
  
