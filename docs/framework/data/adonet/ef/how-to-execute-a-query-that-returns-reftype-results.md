---
title: 如何：执行返回 RefType 结果的查询
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dbbfbcd-93f5-4546-9dbf-e5fa290b69fa
ms.openlocfilehash: f3f1e11d3211140abb02733de4b5b46ac93cf769
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59317163"
---
# <a name="how-to-execute-a-query-that-returns-reftype-results"></a><span data-ttu-id="bd27d-102">如何：执行返回 RefType 结果的查询</span><span class="sxs-lookup"><span data-stu-id="bd27d-102">How to: Execute a Query that Returns RefType Results</span></span>
<span data-ttu-id="bd27d-103">本主题演示如何使用 <xref:System.Data.EntityClient.EntityCommand> 对象针对概念模型执行命令，以及如何使用 <xref:System.Data.Metadata.Edm.RefType> 检索 <xref:System.Data.EntityClient.EntityDataReader> 结果。</span><span class="sxs-lookup"><span data-stu-id="bd27d-103">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the <xref:System.Data.Metadata.Edm.RefType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="bd27d-104">运行本示例中的代码</span><span class="sxs-lookup"><span data-stu-id="bd27d-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="bd27d-105">添加[AdventureWorks 销售模型](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)到你的项目和配置项目以使用[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bd27d-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="bd27d-106">有关详细信息，请参阅[如何：使用实体数据模型向导](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="bd27d-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="bd27d-107">在应用程序的代码页中，添加以下 `using` 语句（在 Visual Basic 中为 `Imports`）：</span><span class="sxs-lookup"><span data-stu-id="bd27d-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="bd27d-108">示例</span><span class="sxs-lookup"><span data-stu-id="bd27d-108">Example</span></span>  
 <span data-ttu-id="bd27d-109">本示例执行返回 <xref:System.Data.Metadata.Edm.RefType> 结果的查询。</span><span class="sxs-lookup"><span data-stu-id="bd27d-109">This example executes a query that returns <xref:System.Data.Metadata.Edm.RefType> results.</span></span> <span data-ttu-id="bd27d-110">如果你将以下查询作为自变量传递给 `ExectueRefTypeQuery` 函数，该函数会返回一个对实体的引用：</span><span class="sxs-lookup"><span data-stu-id="bd27d-110">If you pass the following query as an argument to the `ExectueRefTypeQuery` function, the function returns a reference to the entity:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#REF2](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref2)]  
  
 <span data-ttu-id="bd27d-111">如果传递参数化查询（如下面的查询），请将 <xref:System.Data.EntityClient.EntityParameter> 对象添加到 <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> 对象的 <xref:System.Data.EntityClient.EntityCommand> 属性。</span><span class="sxs-lookup"><span data-stu-id="bd27d-111">If you pass a parameterized query, like the following, add the <xref:System.Data.EntityClient.EntityParameter> objects to the <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> property on the <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#REF3](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref3)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLRefTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlreftypes)]
 [!code-vb[DP EntityServices Concepts#eSQLRefTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlreftypes)]  
  
## <a name="see-also"></a><span data-ttu-id="bd27d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd27d-112">See also</span></span>

- [<span data-ttu-id="bd27d-113">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="bd27d-113">Entity SQL Reference</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="bd27d-114">用于实体框架的 EntityClient 提供程序</span><span class="sxs-lookup"><span data-stu-id="bd27d-114">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
