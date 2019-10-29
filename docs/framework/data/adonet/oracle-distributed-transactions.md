---
title: Oracle 分布式事务
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: edd06b94ce4157e90d334ee7feac2a449f7ee74b
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040482"
---
# <a name="oracle-distributed-transactions"></a>Oracle 分布式事务
<xref:System.Data.OracleClient.OracleConnection> 对象自动在现有分布式事务中登记（如果确定某个事务是活动的）。 如果连接从连接池中打开或检索，将自动登记事务。 可以禁用现有事务中的自动登记，方法是将  
  
```csharp  
Enlist=false  
```  
  
 指定为 <xref:System.Data.OracleClient.OracleConnection> 的连接字符串参数。  
  
## <a name="see-also"></a>请参阅

- [Oracle 和 ADO.NET](oracle-and-adonet.md)
- [ADO.NET 概述](ado-net-overview.md)
