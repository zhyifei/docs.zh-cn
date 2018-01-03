---
title: "Oracle 分布式事务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 104befd25d30d050fee0a053a413b13fe6d1fc51
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="504df-102">Oracle 分布式事务</span><span class="sxs-lookup"><span data-stu-id="504df-102">Oracle Distributed Transactions</span></span>
<span data-ttu-id="504df-103"><xref:System.Data.OracleClient.OracleConnection> 对象自动在现有分布式事务中登记（如果确定某个事务是活动的）。</span><span class="sxs-lookup"><span data-stu-id="504df-103">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="504df-104">如果连接从连接池中打开或检索，将自动登记事务。</span><span class="sxs-lookup"><span data-stu-id="504df-104">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="504df-105">可以禁用现有事务中的自动登记，方法是将</span><span class="sxs-lookup"><span data-stu-id="504df-105">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```  
Enlist=false  
```  
  
 <span data-ttu-id="504df-106">指定为 <xref:System.Data.OracleClient.OracleConnection> 的连接字符串参数。</span><span class="sxs-lookup"><span data-stu-id="504df-106">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="504df-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="504df-107">See Also</span></span>  
 [<span data-ttu-id="504df-108">Oracle 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="504df-108">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="504df-109">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="504df-109">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
