---
title: Oracle 分布式事务
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: 8e7530621254881402570b59b47a22052b40f2b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713233"
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="b42fb-102">Oracle 分布式事务</span><span class="sxs-lookup"><span data-stu-id="b42fb-102">Oracle Distributed Transactions</span></span>
<span data-ttu-id="b42fb-103"><xref:System.Data.OracleClient.OracleConnection> 对象自动在现有分布式事务中登记（如果确定某个事务是活动的）。</span><span class="sxs-lookup"><span data-stu-id="b42fb-103">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="b42fb-104">如果连接从连接池中打开或检索，将自动登记事务。</span><span class="sxs-lookup"><span data-stu-id="b42fb-104">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="b42fb-105">可以禁用现有事务中的自动登记，方法是将</span><span class="sxs-lookup"><span data-stu-id="b42fb-105">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```  
Enlist=false  
```  
  
 <span data-ttu-id="b42fb-106">指定为 <xref:System.Data.OracleClient.OracleConnection> 的连接字符串参数。</span><span class="sxs-lookup"><span data-stu-id="b42fb-106">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b42fb-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="b42fb-107">See also</span></span>
- [<span data-ttu-id="b42fb-108">Oracle 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b42fb-108">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [<span data-ttu-id="b42fb-109">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="b42fb-109">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
