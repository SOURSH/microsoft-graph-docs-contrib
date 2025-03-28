---
author: "yyuank"
ms.subservice: entra-users
ms.topic: include
---

<!-- markdownlint-disable MD041-->

- *User-PasswordProfile.ReadWrite.All* is the least privileged permission to update the **passwordProfile** property.
- In delegated scenarios, the calling app must be assigned a supported permission *and* a supported Microsoft Entra role.
  - *Privileged Authentication Administrator* is the least privileged role that's allowed to update this property for *all* administrators in the tenant.
  - In general, the signed-in user must have a higher privileged administrator role as indicated in [Who can reset passwords](/graph/api/resources/users#who-can-reset-passwords).
- In app-only scenarios, the calling app must be assigned a supported permission *and* at least the *User Administrator* [Microsoft Entra role](/entra/identity/role-based-access-control/permissions-reference?toc=%2Fgraph%2Ftoc.json).