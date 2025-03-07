# Net Services Suite

## General Help

```powershell
net /?
```

### Account and Computer Management
```powershell
net ACCOUNTS C:> net COMPUTER
```

#### Server Configuration
```powershell
net CONFIG Server
```

## Viewing Local and Remote Shares

### Display a list of local shares
```powershell
net share
```

### List the shares on a remote computer
```powershell
net view \192.168.1.65
```

### List all shares on a remote computer, including hidden shares
```powershell
net view \192.168.1.65 /all
```

## Connecting to a Remote Share

### Connect using specific user credentials
```powershell
net use \192.168.1.30 /user:Administrator @rmour123
```

### View shares on a remote computer
```powershell
net view \192.168.1.30
```

### Connect to a remote share with a drive letter
```powershell
net use t: \192.168.1.65\data /user:Armour 123
```

### Disconnect the mapped drive
```powershell
net use t: /delete
```

## Managing Network Sessions and Files

### View active network sessions
```powershell
net session
```

### View open files over the network
```powershell
net file
```

## Workstation and Server Configuration

### View server configuration
```powershell
net config server
```
### View workstation configuration
```powershell
net config WORKSTATION
```
## Network Time Synchronization
```powershell
net TIME
```
