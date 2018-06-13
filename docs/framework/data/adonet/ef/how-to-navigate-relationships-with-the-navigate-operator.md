---
title: 如何：使用导航运算符导航关系
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79996d2d-9b03-4a9d-82cc-7c5e7c2ad93d
ms.openlocfilehash: 3db44ccee4420423072fc256dbed888c78fc4417
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761826"
---
# <a name="how-to-navigate-relationships-with-the-navigate-operator"></a><span data-ttu-id="0bf8e-102">如何：使用导航运算符导航关系</span><span class="sxs-lookup"><span data-stu-id="0bf8e-102">How to: Navigate Relationships with the Navigate Operator</span></span>
<span data-ttu-id="0bf8e-103">本主题演示如何使用 <xref:System.Data.EntityClient.EntityCommand> 对象针对概念模型执行命令，以及如何使用 <xref:System.Data.Metadata.Edm.RefType> 检索 <xref:System.Data.EntityClient.EntityDataReader> 结果。</span><span class="sxs-lookup"><span data-stu-id="0bf8e-103">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the <xref:System.Data.Metadata.Edm.RefType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="0bf8e-104">运行本示例中的代码</span><span class="sxs-lookup"><span data-stu-id="0bf8e-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="0bf8e-105">添加[AdventureWorks 销售模型](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)到你的项目和配置项目以使用[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0bf8e-105">Add the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="0bf8e-106">有关详细信息，请参阅[如何： 使用实体数据模型向导](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)。</span><span class="sxs-lookup"><span data-stu-id="0bf8e-106">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="0bf8e-107">在应用程序的代码页中，添加以下 `using` 语句（在 Visual Basic 中为 `Imports`）：</span><span class="sxs-lookup"><span data-stu-id="0bf8e-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="0bf8e-108">示例</span><span class="sxs-lookup"><span data-stu-id="0bf8e-108">Example</span></span>  
 <span data-ttu-id="0bf8e-109">下面的示例演示如何导航中的关系[!INCLUDE[esql](../../../../../includes/esql-md.md)]使用[导航](../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)运算符。</span><span class="sxs-lookup"><span data-stu-id="0bf8e-109">The following example shows how to navigate relationships in [!INCLUDE[esql](../../../../../includes/esql-md.md)] by using the [NAVIGATE](../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) operator.</span></span> <span data-ttu-id="0bf8e-110">`Navigate`运算符采用以下参数： 实体、 关系类型、 在关系的结束和关系的开头的实例。</span><span class="sxs-lookup"><span data-stu-id="0bf8e-110">The `Navigate` operator takes the following parameters: an instance of an entity, the relationship type, the end of the relationship, and the beginning of the relationship.</span></span> <span data-ttu-id="0bf8e-111">（可选） 可以将仅实体和关系类型设置为的一个实例传递`Navigate`运算符。</span><span class="sxs-lookup"><span data-stu-id="0bf8e-111">Optionally, you can pass only an instance of an entity and the relationship type to the `Navigate` operator.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#navigatewithnavoperatorwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#navigatewithnavoperatorwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="0bf8e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bf8e-112">See Also</span></span>  
 [<span data-ttu-id="0bf8e-113">用于实体框架的 EntityClient 提供程序</span><span class="sxs-lookup"><span data-stu-id="0bf8e-113">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
 [<span data-ttu-id="0bf8e-114">实体 SQL 语言</span><span class="sxs-lookup"><span data-stu-id="0bf8e-114">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
