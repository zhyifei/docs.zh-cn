---
title: 如何：执行多态查询
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: 08ae5722267ef781ed6bee59c7895269f63a75e5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355529"
---
# <a name="how-to-execute-a-polymorphic-query"></a><span data-ttu-id="49725-102">如何：执行多态查询</span><span class="sxs-lookup"><span data-stu-id="49725-102">How to: Execute a Polymorphic Query</span></span>

<span data-ttu-id="49725-103">本主题演示如何执行多态[!INCLUDE[esql](../../../../../includes/esql-md.md)]使用查询[OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md)运算符。</span><span class="sxs-lookup"><span data-stu-id="49725-103">This topic shows how to execute a polymorphic [!INCLUDE[esql](../../../../../includes/esql-md.md)] query using the [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operator.</span></span>

### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="49725-104">运行本示例中的代码</span><span class="sxs-lookup"><span data-stu-id="49725-104">To run the code in this example</span></span>

1. <span data-ttu-id="49725-105">添加[School 模型](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100))到你的项目和配置项目以使用实体框架。</span><span class="sxs-lookup"><span data-stu-id="49725-105">Add the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="49725-106">有关详细信息，请参阅[如何：使用实体数据模型向导](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="49725-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>

2. <span data-ttu-id="49725-107">在应用程序的代码页中，添加以下 `using` 语句（在 Visual Basic 中为 `Imports`）：</span><span class="sxs-lookup"><span data-stu-id="49725-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. <span data-ttu-id="49725-108">修改概念模型中的步骤具有每个层次结构一个表继承[演练：映射继承-每个层次结构一个表](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="49725-108">Modify the conceptual model to have a table-per-hierarchy inheritance by following the steps in [Walkthrough: Mapping Inheritance - Table-per-Hierarchy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).</span></span>

## <a name="example"></a><span data-ttu-id="49725-109">示例</span><span class="sxs-lookup"><span data-stu-id="49725-109">Example</span></span>

<span data-ttu-id="49725-110">下面的示例使用 OFTYPE 运算符从 `OnsiteCourses` 的集合中获取和显示仅包含 `Courses` 的集合。</span><span class="sxs-lookup"><span data-stu-id="49725-110">The following example uses an OFTYPE operator to get and display a collection of only `OnsiteCourses` from a collection of `Courses`.</span></span>

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a><span data-ttu-id="49725-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="49725-111">See also</span></span>

- [<span data-ttu-id="49725-112">用于实体框架的 EntityClient 提供程序</span><span class="sxs-lookup"><span data-stu-id="49725-112">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
- [<span data-ttu-id="49725-113">实体 SQL 语言</span><span class="sxs-lookup"><span data-stu-id="49725-113">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
