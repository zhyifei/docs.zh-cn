---
title: 从数据库获取单一值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: 5eb81fd2a64f06f1252f71e251e58df568e7407c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120674"
---
# <a name="obtaining-a-single-value-from-a-database"></a><span data-ttu-id="5d74d-102">从数据库获取单一值</span><span class="sxs-lookup"><span data-stu-id="5d74d-102">Obtaining a Single Value from a Database</span></span>
<span data-ttu-id="5d74d-103">您可能需要返回只是单个值的数据库信息，而不需要返回表或数据流形式的数据库信息。</span><span class="sxs-lookup"><span data-stu-id="5d74d-103">You may need to return database information that is simply a single value rather than in the form of a table or data stream.</span></span> <span data-ttu-id="5d74d-104">例如，您可能需要返回 COUNT 等聚合函数的结果 (\*)，sum (price) 或 avg （quantity）。</span><span class="sxs-lookup"><span data-stu-id="5d74d-104">For example, you may want to return the result of an aggregate function such as COUNT(\*), SUM(Price), or AVG(Quantity).</span></span> <span data-ttu-id="5d74d-105">**命令**对象提供了返回单个值使用的功能**ExecuteScalar**方法。</span><span class="sxs-lookup"><span data-stu-id="5d74d-105">The **Command** object provides the capability to return single values using the **ExecuteScalar** method.</span></span> <span data-ttu-id="5d74d-106">**ExecuteScalar**方法返回时，为标量值，结果集的第一行的第一列的值。</span><span class="sxs-lookup"><span data-stu-id="5d74d-106">The **ExecuteScalar** method returns, as a scalar value, the value of the first column of the first row of the result set.</span></span>  
  
 <span data-ttu-id="5d74d-107">下面的代码示例使用 <xref:System.Data.SqlClient.SqlCommand> 在数据库中插入一个新值。</span><span class="sxs-lookup"><span data-stu-id="5d74d-107">The following code example inserts a new value in the database using a <xref:System.Data.SqlClient.SqlCommand>.</span></span> <span data-ttu-id="5d74d-108">使用 <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> 方法可返回已插入记录的标识列值。</span><span class="sxs-lookup"><span data-stu-id="5d74d-108">The <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> method is used to return the identity column value for the inserted record.</span></span>  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5d74d-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d74d-109">See also</span></span>

- [<span data-ttu-id="5d74d-110">命令和参数</span><span class="sxs-lookup"><span data-stu-id="5d74d-110">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="5d74d-111">执行命令</span><span class="sxs-lookup"><span data-stu-id="5d74d-111">Executing a Command</span></span>](../../../../docs/framework/data/adonet/executing-a-command.md)
- [<span data-ttu-id="5d74d-112">DbConnection、DbCommand 和 DbException</span><span class="sxs-lookup"><span data-stu-id="5d74d-112">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)
- [<span data-ttu-id="5d74d-113">ADO.NET 托管提供程序和 DataSet 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="5d74d-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
