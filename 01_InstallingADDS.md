# Installing Active Directory Domain Services
AD DS is the core component of Active Directory that enables users to authenticate and access resources on the network.

## Domain
In simple words, a domain can be called as a collection or structure of all Active Directory objects like users, computers, groups etc sharing a common Active Directory database and is managed by main server of the domain which is called as a Domain controller. A domain is always referred to by its unique name and has a proper domain name structure.

An Active Directory domain is made up of the following components:
-  An [X.500](https://en.wikipedia.org/wiki/X.500)-based hierarchical structure of containers and objects
-  A DNS domain name as a unique identifier
-  A security service, which authenticates and authorizes any access to resources via
accounts in the domain or trusts with other domains
-  Policies that dictate how functionality is restricted for users or machines within that
domain

## Domain Tree
A domain controller can only be authoritative for one domain and that it is not possible to host multiple domains on a single DC.
The adlab.loc domain is the root node of a hierarchical structure called a domain tree, and additional domains such as lab1, lab2, and lab3 can be added using a contiguous naming scheme (e.g., lab1.adlab.loc, lab2.adlab.loc, and lab3.adlab.loc). Each domain tree is named after the root of the tree, so the adlab.loc tree is named after the adlab.loc domain. Even if there is only one domain, it is still considered a domain tree

## Forest
In Active Directory, a forest comprises one or more domain trees that are linked by transitive trusts and share a common Schema and Configuration container. It is worth noting that a forest is formed as soon as a single domain is created, and adding domains to the initial domain tree or creating new domain trees does not result in a new forest.

The first domain created within a forest is referred to as the forest root domain, and the forest itself takes its name from this domain. The forest root domain is significant as it possesses unique characteristics.

It is important to note that the forest root domain cannot be removed once it has been created, as doing so would result in the destruction of the entire forest. While it is possible to rename the forest root domain in Active Directories that are Windows Server 2003 or newer, it is not possible to alter its status as the forest root domain or designate another domain as the root.


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

