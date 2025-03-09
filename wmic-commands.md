# Update Drivers Using WMIC Command

## **WMIC Commands and Their Usage**

### **General Help**
Retrieves general help information for WMIC commands.
```powershell
wmic /?
```

---
### **BIOS Information**
Retrieves BIOS-related information including name, version, and serial number.
```powershell
wmic bios get name, version, serialnumber
```

Retrieves only the BIOS serial number.
```powershell
wmic bios get serialnumber
```

Displays the BIOS manufacturer.
```powershell
wmic bios get manufacturer
```

Displays BIOS details in a list format.
```powershell
wmic bios get /format:list
```

---
### **Computer System Information**
Retrieves computer system product information from SMBIOS.
```powershell
wmic csproduct get name
```

Displays detailed computer system product information.
```powershell
wmic csproduct get /format:list
```

Displays boot configuration details.
```powershell
wmic bootconfig get /format:list
```

Retrieves details of logical disks.
```powershell
wmic logicaldisk get /format:list
```

Displays the computer system model.
```powershell
wmic computersystem get model
```

Displays computer system details in a list format.
```powershell
wmic computersystem get /format:list
```

Retrieves the computer name and system type.
```powershell
wmic computersystem get name, systemtype
```

---
### **Network Information**
Retrieves MAC addresses and network adapter descriptions.
```powershell
wmic nic get macaddress,description
```

Displays detailed network adapter information.
```powershell
wmic nic get /format:list
```

---
### **Hardware Information**
Retrieves motherboard details such as product, manufacturer, version, and serial number.
```powershell
wmic baseboard get product,manufacturer,version,serialnumber
```

Displays the total physical memory (RAM) of the system.
```powershell
wmic computersystem get totalphysicalmemory
```

Retrieves partition details including name, size, and type.
```powershell
wmic partition get name,size,type
```

Displays information about disk drives.
```powershell
wmic diskdrive get name, manufacturer, model, interfacetype, mediatype, serialnumber
```

---
### **Service Management**
Retrieves a brief list of all services.
```powershell
wmic service list brief
```

Retrieves details about system services including name, display name, path, and startup mode.
```powershell
wmic service get name,displayname,pathname,startmode
```

---
### **Operating System Information**
Displays the operating system installation date.
```powershell
wmic os get installdate
```

Retrieves the local date and time.
```powershell
wmic os get localdatetime
```

Displays operating system details in list format.
```powershell
wmic os get /format:list
```

