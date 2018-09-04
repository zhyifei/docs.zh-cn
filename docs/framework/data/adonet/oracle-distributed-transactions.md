---
title: Oracle 分布式事务
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: a3b8a50b42b945a0cdc1cbfbc4cc9eab835e90e4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505394"
---
# <a name="oracle-distributed-transactions"></a>Oracle 分布式事务
<xref:System.Data.OracleClient.OracleConnection> 对象自动在现有分布式事务中登记（如果确定某个事务是活动的）。 如果连接从连接池中打开或检索，将自动登记事务。 可以禁用现有事务中的自动登记，方法是将  
  
```  
Enlist=false  
```  
  
 指定为 <xref:System.Data.OracleClient.OracleConnection> 的连接字符串参数。  
  
## <a name="see-also"></a>请参阅  
 [Oracle 和 ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)
