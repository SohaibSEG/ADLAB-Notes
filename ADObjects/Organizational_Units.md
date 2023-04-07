# Oranizational Units
In Active Directory, Organizational Units (OUs) are containers that enable the grouping of various objects, including users, groups, computers, and other OUs within a domain. By organizing objects based on the company's organizational structure, geographic location, or any other criteria that makes sense, OUs provide a structure and order within the domain.

OUs can also be utilized to delegate administrative authority to specific users or groups, allowing them to manage the objects within that OU. Additionally, they can be employed to apply group policies or other settings to a specific group of objects within the domain. OUs are hierarchical, and they can be nested within one another to create a complex structure that replicates an organization's hierarchy.

## Creating OUs
```powershell
# The following command creates a new OU called "Marketing" in the domain "adlab.loc"
New-ADOrganizationalUnit -Name "Marketing" -Path "DC=adlab,DC=loc"
```

## Listing OUs in a Domain:
```powershell
# The following command retrieves a list of all OUs in the "adlab.loc" domain
Get-ADOrganizationalUnit -Filter * -SearchBase "DC=adlab,DC=loc"
```

## Modifying OUs:
```powershell 
# The following command modifies the description of the "Marketing" OU
Set-ADOrganizationalUnit -Identity "OU=Marketing,DC=adlab,DC=loc" -Description "New Description"
```

## Removing OUs:

```powershell
# The following command removes the "Marketing" OU
# Note that this command will also remove any objects that are contained within the OU
Remove-ADOrganizationalUnit -Identity "OU=Marketing,DC=adlab,DC=loc"
```
