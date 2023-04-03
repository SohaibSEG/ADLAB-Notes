# Active Directory Objects 

In Active Directory, objects refer to various resources within the AD network. These resources can take the form of users, computers, printers, or even contact persons who may have vendor relationships with the organization. AD objects possess a unique set of attributes that describe them. These attributes, referred to as AD object attributes, include details such as the user's first and middle name, as well as their reporting manager. The AD schema governs the attributes an object can have, and object classes determine the specific types of objects and the required attributes they should possess.

## Types Of Objects in AD network

Within an AD network, there are two distinct types of objects that can be found: 
**Container objects :** These are objects that can contain other objects within them.They act as a type of folder that can hold other objects.
Example Container Objects : Groups and Organizational Units.

**Leaf Objects :** These are objects that cannot hold other objects within them. They are the lowest level of objects in the AD hierarchy.
Example Leaf Objbects : Users,Computer and Printer.

## A list of AD Objects

Following is a list of objects in Active Directory

- User object
- Contact object
- Printer object
- Computer object
- Shared folder
- Group
- Subnet
- Organizational Unit
- Domain
- Domain controller
- Site objects
- Bulletin
- Foreign security principals
  

## Uniquely Identifying Objects 

In Active Directory, it's essential to ensure that every object can be uniquely located and identified, especially when dealing with a vast amount of objects. For this reason, the system assigns a globally unique identifier (GUID) to each object during its creation. The GUID is a 128-bit number that Microsoft created as its version of the universally unique identifier (UUID) concept from Digital Equipment Corporation. With the GUID, every object in Active Directory is guaranteed to have a unique identifier that sets it apart from all other objects in the network.

## Distinuished Names

In Active Directory, distinguished names are used to uniquely identify objects within the directory. A distinguished name consists of a series of naming attributes that provide a full path to the object within the directory tree. The naming attributes included in the distinguished name are based on the attributes defined in the AD schema for the specific object class.
Example : 

```
DistinguishedName : CN=WORKSTATION,OU=adlab,DC=adlab,DC=loc
DNSHostName       : workstation.adlab.loc
Enabled           : True
Name              : WORKSTATION
ObjectClass       : computer
ObjectGUID        : 673f5bee-22f4-4d93-9c84-ad5c7e8a0850
SamAccountName    : WORKSTATION$
SID               : S-1-5-21-3112958593-1653903949-1071568521-1103
UserPrincipalName :
```

This shows a Computer Object that has a Distinguished Name  " CN=WORKSTATION,OU=adlab,DC=adlab,DC=loc ", In this case, the object has a the common name "workstation", and is located within an organizational unit (OU) called "adlab" in the "adlab.loc" domain.


**Attribute Types from RFC2253**
|   Key     |   Attribute               |
|-----------|---------------------------|
|   CN      | Common name               |
|   L       | Locality name             |
|   ST      | State or province name    |
|   O       | Organization name         |
|   OU      | Organizational unit name  |
|   C       | Country name              |
|   STREET  | Street address            |
|   DC      | Domain component          |
|   UID     | User ID                   |
