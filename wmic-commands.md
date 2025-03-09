# Update Drivers Using WMIC Command

## **WMIC Commands and Their Usage**

### **General Help**
```powershell
wmic /?
```

---
### **BIOS Information**
```powershell
wmic bios get name, version, serialnumber
```
- Retrieves BIOS management information.

```powershell
wmic bios get serialnumber
```
- Retrieves the BIOS serial number.

```powershell
wmic bios get manufacturer
```
- Displays the BIOS manufacturer.

```powershell
wmic bios get /format:list
```
- Displays BIOS details in a list format.

---
### **Computer System Information**
```powershell
wmic csproduct get name
```
- Retrieves computer system product information from SMBIOS.

```powershell
wmic csproduct get /format:list
```
- Displays detailed computer system product information.

```powershell
wmic bootconfig get /format:list
```
- Displays boot configuration details.

```powershell
wmic logicaldisk get /format:list
```
- Retrieves details of logical disks.

```powershell
wmic computersystem get model
```
- Displays the computer system model.

```powershell
wmic computersystem get /format:list
```
- Displays computer system details in a list format.

```powershell
wmic computersystem get name, systemtype
```
- Retrieves the computer name and system type.

---
### **Network Information**
```powershell
wmic nic get macaddress,description
```
- Retrieves MAC addresses and network adapter descriptions.

```powershell
wmic nic get /format:list
```
- Displays detailed network adapter information.

---
### **Hardware Information**
```powershell
wmic baseboard get product,manufacturer,version,serialnumber
```
- Retrieves motherboard details such as product, manufacturer, version, and serial number.

```powershell
wmic computersystem get totalphysicalmemory
```
- Displays the total physical memory (RAM) of the system.

```powershell
wmic partition get name,size,type
```
- Retrieves partition details including name, size, and type.

```powershell
wmic diskdrive get name, manufacturer, model, interfacetype, mediatype, serialnumber
```
- Displays information about disk drives.

---
### **Service Management**
```powershell
wmic service list brief
```
- Retrieves a brief list of all services.

```powershell
wmic service get name,displayname,pathname,startmode
```
- Retrieves details about system services including name, display name, path, and startup mode.

---
### **Operating System Information**
```powershell
wmic os get installdate
```
- Displays the operating system installation date.

```powershell
wmic os get localdatetime
```
- Retrieves the local date and time.

```powershell
wmic os get /format:list
```
- Displays operating system details in list format.

```p
