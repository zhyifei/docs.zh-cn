---
title: Oracle 分布式事务
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: 0e9dcb30eb1962071d7154d4bbf929871c8a12d2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765196"
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="f652a-102">Oracle 分布式事务</span><span class="sxs-lookup"><span data-stu-id="f652a-102">Oracle Distributed Transactions</span></span>
<span data-ttu-id="f652a-103"><xref:System.Data.OracleClient.OracleConnection> 对象自动在现有分布式事务中登记（如果确定某个事务是活动的）。</span><span class="sxs-lookup"><span data-stu-id="f652a-103">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="f652a-104">如果连接从连接池中打开或检索，将自动登记事务。</span><span class="sxs-lookup"><span data-stu-id="f652a-104">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="f652a-105">可以禁用现有事务中的自动登记，方法是将</span><span class="sxs-lookup"><span data-stu-id="f652a-105">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```  
Enlist=false  
```  
  
 <span data-ttu-id="f652a-106">指定为 <xref:System.Data.OracleClient.OracleConnection> 的连接字符串参数。</span><span class="sxs-lookup"><span data-stu-id="f652a-106">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f652a-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="f652a-107">See Also</span></span>  
 [<span data-ttu-id="f652a-108">Oracle 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f652a-108">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="f652a-109">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="f652a-109">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
