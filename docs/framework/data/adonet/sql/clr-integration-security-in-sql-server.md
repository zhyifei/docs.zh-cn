---
title: SQL Server 中的 CLR 集成安全性
ms.date: 03/30/2017
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
ms.openlocfilehash: 946401211d515df9ba5b9e38d7cfd10730973b64
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165810"
---
# <a name="clr-integration-security-in-sql-server"></a>SQL Server 中的 CLR 集成安全性
Microsoft SQL Server 提供 .NET Framework 的公共语言运行时 (CLR) 组件集成。 通过 CLR 集成，您可以使用任何 .NET Framework 语言（如 Microsoft Visual Basic .NET 或 Microsoft Visual C#）编写存储过程、触发器、用户定义的类型、用户定义的函数、用户定义的聚合以及流式表值函数。  
  
 CLR 支持一种用于托管代码的安全模型，称为代码访问安全性 (CAS)。 在此模型中，将根据元数据中代码提供的证据向程序集授予权限。 SQL Server 将 SQL Server 的基于用户的安全模型与 CLR 的基于代码启用的安全模型相集成。  
  
## <a name="external-resources"></a>外部资源  
 有关 CLR 与 SQL Server 集成的更多信息，请参见下列资源。  
  
|资源|描述|  
|--------------|-----------------|  
|[代码访问安全性](../../../../../docs/framework/misc/code-access-security.md)|包含描述 .NET Framework 中 CAS 的主题。|  
|[CLR 集成安全性](/sql/relational-databases/clr-integration/security/clr-integration-security)|讨论在 SQL Server 内部执行的托管代码的安全模型。|  
  
## <a name="see-also"></a>请参阅

- [保证 ADO.NET 应用程序的安全](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [SQL Server 中的应用程序安全性方案](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [SQL Server 公共语言运行时集成](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)
- [ADO.NET 概述](../../../../../docs/framework/data/adonet/ado-net-overview.md)
