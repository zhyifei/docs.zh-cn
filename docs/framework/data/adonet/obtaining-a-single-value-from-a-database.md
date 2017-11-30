---
title: "从数据库获取单一值"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 513310ddfb578f127ee70059dec386f207180907
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="obtaining-a-single-value-from-a-database"></a><span data-ttu-id="e1267-102">从数据库获取单一值</span><span class="sxs-lookup"><span data-stu-id="e1267-102">Obtaining a Single Value from a Database</span></span>
<span data-ttu-id="e1267-103">您可能需要返回只是单个值的数据库信息，而不需要返回表或数据流形式的数据库信息。</span><span class="sxs-lookup"><span data-stu-id="e1267-103">You may need to return database information that is simply a single value rather than in the form of a table or data stream.</span></span> <span data-ttu-id="e1267-104">例如，你可能想要返回的结果计数等聚合函数 (\*)，（price） 或 AVG(Quantity)。</span><span class="sxs-lookup"><span data-stu-id="e1267-104">For example, you may want to return the result of an aggregate function such as COUNT(\*), SUM(Price), or AVG(Quantity).</span></span> <span data-ttu-id="e1267-105">**命令**对象提供的功能，以返回单个值使用**ExecuteScalar**方法。</span><span class="sxs-lookup"><span data-stu-id="e1267-105">The **Command** object provides the capability to return single values using the **ExecuteScalar** method.</span></span> <span data-ttu-id="e1267-106">**ExecuteScalar**方法返回时，为标量值，结果集的第一行的第一列的值。</span><span class="sxs-lookup"><span data-stu-id="e1267-106">The **ExecuteScalar** method returns, as a scalar value, the value of the first column of the first row of the result set.</span></span>  
  
 <span data-ttu-id="e1267-107">下面的代码示例使用 <xref:System.Data.SqlClient.SqlCommand> 在数据库中插入一个新值。</span><span class="sxs-lookup"><span data-stu-id="e1267-107">The following code example inserts a new value in the database using a <xref:System.Data.SqlClient.SqlCommand>.</span></span> <span data-ttu-id="e1267-108">使用 <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> 方法可返回已插入记录的标识列值。</span><span class="sxs-lookup"><span data-stu-id="e1267-108">The <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> method is used to return the identity column value for the inserted record.</span></span>  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e1267-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1267-109">See Also</span></span>  
 [<span data-ttu-id="e1267-110">命令和参数</span><span class="sxs-lookup"><span data-stu-id="e1267-110">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="e1267-111">执行命令</span><span class="sxs-lookup"><span data-stu-id="e1267-111">Executing a Command</span></span>](../../../../docs/framework/data/adonet/executing-a-command.md)  
 [<span data-ttu-id="e1267-112">DbConnection、 DbCommand 和 DbException</span><span class="sxs-lookup"><span data-stu-id="e1267-112">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [<span data-ttu-id="e1267-113">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="e1267-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
