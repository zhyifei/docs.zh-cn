---
title: 如何：执行多态查询
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: 18e2bfee223fa14ec9a232fe308ad2edda6bec55
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-execute-a-polymorphic-query"></a><span data-ttu-id="a9f3c-102">如何：执行多态查询</span><span class="sxs-lookup"><span data-stu-id="a9f3c-102">How to: Execute a Polymorphic Query</span></span>
<span data-ttu-id="a9f3c-103">本主题演示如何执行多态[!INCLUDE[esql](../../../../../includes/esql-md.md)]查询使用[OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md)运算符。</span><span class="sxs-lookup"><span data-stu-id="a9f3c-103">This topic shows how to execute a polymorphic [!INCLUDE[esql](../../../../../includes/esql-md.md)] query using the [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operator.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="a9f3c-104">运行本示例中的代码</span><span class="sxs-lookup"><span data-stu-id="a9f3c-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="a9f3c-105">添加[School 模型](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac)到你的项目和配置项目以使用实体框架。</span><span class="sxs-lookup"><span data-stu-id="a9f3c-105">Add the [School Model](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="a9f3c-106">有关详细信息，请参阅[如何： 使用实体数据模型向导](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)。</span><span class="sxs-lookup"><span data-stu-id="a9f3c-106">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="a9f3c-107">在应用程序的代码页中，添加以下 `using` 语句（在 Visual Basic 中为 `Imports`）：</span><span class="sxs-lookup"><span data-stu-id="a9f3c-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="a9f3c-108">修改要按照中的步骤具有每个 hierrachy 表继承的概念模型[演练： 映射继承-每个层次结构一个表](http://msdn.microsoft.com/library/49b685cf-9db8-4d6d-b885-8837ed238f55)。</span><span class="sxs-lookup"><span data-stu-id="a9f3c-108">Modify the conceptual model to have a table-per-hierrachy inheritance by following the steps in [Walkthrough: Mapping Inheritance - Table-per-Hierarchy](http://msdn.microsoft.com/library/49b685cf-9db8-4d6d-b885-8837ed238f55).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9f3c-109">示例</span><span class="sxs-lookup"><span data-stu-id="a9f3c-109">Example</span></span>  
 <span data-ttu-id="a9f3c-110">下面的示例使用 OFTYPE 运算符从 `OnsiteCourses` 的集合中获取和显示仅包含 `Courses` 的集合。</span><span class="sxs-lookup"><span data-stu-id="a9f3c-110">The following example uses an OFTYPE operator to get and display a collection of only `OnsiteCourses` from a collection of `Courses`.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
 [!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]  
  
## <a name="see-also"></a><span data-ttu-id="a9f3c-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9f3c-111">See Also</span></span>  
 [<span data-ttu-id="a9f3c-112">用于实体框架的 EntityClient 提供程序</span><span class="sxs-lookup"><span data-stu-id="a9f3c-112">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
 [<span data-ttu-id="a9f3c-113">实体 SQL 语言</span><span class="sxs-lookup"><span data-stu-id="a9f3c-113">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
