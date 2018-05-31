---
title: Adding or Deleting an Application Directory Partition Replica
description: The first replica of an application directory partition is created on the domain controller that was bound to it at creation time.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\mbaldwin
ms.assetid: 2dafc822-d0e8-4960-9a45-cc21d1d2924c
ms.prod: windows-server-dev
ms.technology: active-directory-domain-services
ms.tgt_platform: multiple
keywords:
- Adding or Deleting an Application Directory Partition Replica AD
- Application Directory Partitions AD , Adding or Deleting a Partition Replica
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# Adding or Deleting an Application Directory Partition Replica

The first replica of an application directory partition is created on the domain controller that was bound to it at creation time. Additional replicas can be created on any domain controller in the forest, not necessarily in the same domain as the initial domain controller. An application directory partition replica can only exist on a domain controller that is running Windows Server 2003 or later. For more information, see this TechNet article on [Partition Management](https://TechNet.Microsoft.Com/library/cc730970(WS.10).aspx).

**To add a replica for an application directory partition, perform the following steps**

1.  Search the Partitions container for a [**crossRef**](https://msdn.microsoft.com/library/ms681007) object that has an [**nCName**](https://msdn.microsoft.com/library/ms678699) attribute value that is equal to the distinguished name of the application directory partition.
2.  Bind to the [**crossRef**](https://msdn.microsoft.com/library/ms681007) object with delegation enabled. This is required because the **crossRef** object can only be modified on the Domain-Naming FSMO role holder. With delegation enabled, the domain controller can contact the Domain-Naming FSMO role holder using the same credentials.
3.  Add the distinguished name of the [**nTDSDSA**](https://msdn.microsoft.com/library/ms683855) object for the domain controller that will host the new replica to the [**msDS-NC-Replica-Locations**](https://msdn.microsoft.com/library/ms677446) attribute of the [**crossRef**](https://msdn.microsoft.com/library/ms681007) object.

When the new [**msDS-NC-Replica-Locations**](https://msdn.microsoft.com/library/ms677446) attribute value is replicated to the new domain controller that will host a replica of the application directory partition, the KCC will be triggered to replicate the application directory partition to the target domain controller.

To remove a replica for an application directory partition, perform the same steps above to locate the [**crossRef**](https://msdn.microsoft.com/library/ms681007) object that represents the application directory partition and remove the value that corresponds to the domain controller from the [**msDS-NC-Replica-Locations**](https://msdn.microsoft.com/library/ms677446) attribute of the **crossRef** object.

When the new [**msDS-NC-Replica-Locations**](https://msdn.microsoft.com/library/ms677446) attribute value is replicated to the domain controller that will no longer host a replica of the application directory partition, the KCC will be triggered to remove the replica of the application directory partition on the target domain controller.

If a domain controller that is hosting an application directory partition replica is removed or demoted, the Active Directory server will automatically remove the value corresponding to the domain controller from the [**msDS-NC-Replica-Locations**](https://msdn.microsoft.com/library/ms677446) attribute of all [**crossRef**](https://msdn.microsoft.com/library/ms681007) objects.

 

 



