# Joining a Computer to The Domain

A computer object in AD represents a computer that is part of an organization’s AD network, it has attributes that contain information such as computer name, computer name (pre-Windows 2000), its unique ID, DNS name, role, description, location, who the computer is managed by, the operating system version it is running on, and more.

## DNS Configuration:

For the computer to be able to resolve the domain name, it must have the DC's ip as a dns server for the network interface that is connected to the lan.

```powershell
Set-DNSClientServerAddress –InterfaceIndex <interface id> –ServerAddresses <dc ip>
```

## Joining The Domain:

```powershell
$creds = Get-Credentials # will be prompted for domain user creds, could use domain admin
Add-Computer -DomainName adlab -Force -Restart 
```