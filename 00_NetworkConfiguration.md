# Network Configuration

This Network Consists of 2 Hosts :
**Domain Controller :** Running windows server 2019 core, will act as a domain controller and will have the static IP 10.0.0.1/24 to be used later for DNS configuration in the other hosts.

**Workstaion :** An example computer that's running windows 10, will be used as a test subject and will have the static ip 10.0.0.2/24 because of the absense of a dhcp server in the network. I may configure one later using the DC or a seperate linux machine

## Domain Controller:

```
# finding the network adapter that is connected to the local network
Get-NetAdapter
# renaming it to distinguish it from other adapters
Rename-NetAdapter -Name "Ethernet" -NewName "lan"
# setting the ip for that adapter to 10.0.0.1/24
Get-NetAdapter -Name lan | New-NetIPAddress –IPAddress 10.0.0.1 -PrefixLength 24
```

## Workstation:

```
# finding the network adapter that is connected to the local network
Get-NetAdapter
# renaming it to distinguish it from other adapters
Rename-NetAdapter -Name "Ethernet" -NewName "lan"
# setting the ip for that adapter to 10.0.0.2/24
Get-NetAdapter -Name lan | New-NetIPAddress –IPAddress 10.0.0.2 -PrefixLength 24
```