# Installing Active Directory Domain Services
AD DS is the core component of Active Directory that enables users to authenticate and access resources on the network.

## Domain
In simple words, a domain can be called as a collection or structure of all Active Directory objects like users, computers, groups etc sharing a common Active Directory database and is managed by main server of the domain which is called as a Domain controller. A domain is always referred to by its unique name and has a proper domain name structure.
Domains can have subdomains and form a domain tree.

## Forest

A forest is simply a collection of domain trees.


## Installing AD DS on the DC

```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
```

## Installing  a new AD Forest

```powershell
# Renaaming the DC to distinguish it from other hosts in the network
Rename-Computer -NewName DC -Restart
# Installing a new forest
$Password = <password plaintext> 
$SecurePassword = $Password | ConvertTo-SecureString -AsPlainText -Force 
# the domain name will be adlab.loc
Install-ADDSForest -DomainName adlab.loc -SafeModeAdministratorPassword $SecurePassword -Force
```

