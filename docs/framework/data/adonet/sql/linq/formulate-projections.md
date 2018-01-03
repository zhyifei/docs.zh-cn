---
title: "构建投影"
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
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: bb22ddd4882d9885c55301a6fdc6a0eb336b49af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="formulate-projections"></a><span data-ttu-id="9dcf9-102">构建投影</span><span class="sxs-lookup"><span data-stu-id="9dcf9-102">Formulate Projections</span></span>
<span data-ttu-id="9dcf9-103">下面的示例演示如何将 C# 中的 `select` 语句和 `Select` 中的 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 语句与其他功能结合使用以构建查询投影。</span><span class="sxs-lookup"><span data-stu-id="9dcf9-103">The following examples show how the `select` statement in C# and `Select` statement in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dcf9-104">示例</span><span class="sxs-lookup"><span data-stu-id="9dcf9-104">Example</span></span>  
 <span data-ttu-id="9dcf9-105">下面的示例使用 `Select` 中的 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 子句（在 C# 中为 `select` 子句）返回由 `Customers` 的联系人姓名组成的序列。</span><span class="sxs-lookup"><span data-stu-id="9dcf9-105">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="9dcf9-106">示例</span><span class="sxs-lookup"><span data-stu-id="9dcf9-106">Example</span></span>  
 <span data-ttu-id="9dcf9-107">下面的示例使用`Select`中的子句[!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)](`select` C# 中的子句) 和*匿名类型*若要返回的联系人姓名组成的序列和电话号码`Customers`。</span><span class="sxs-lookup"><span data-stu-id="9dcf9-107">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="9dcf9-108">示例</span><span class="sxs-lookup"><span data-stu-id="9dcf9-108">Example</span></span>  
 <span data-ttu-id="9dcf9-109">下面的示例使用`Select`中的子句[!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)](`select` C# 中的子句) 和*匿名类型*返回一系列名称和员工的电话号码。</span><span class="sxs-lookup"><span data-stu-id="9dcf9-109">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="9dcf9-110">在产生的序列中，`FirstName` 和 `LastName` 字段组合成单个字段 (`Name`)，`HomePhone` 字段重命名为 `Phone`。</span><span class="sxs-lookup"><span data-stu-id="9dcf9-110">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="9dcf9-111">示例</span><span class="sxs-lookup"><span data-stu-id="9dcf9-111">Example</span></span>  
 <span data-ttu-id="9dcf9-112">下面的示例使用`Select`中的子句[!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)](`select` C# 中的子句) 和*匿名类型*可返回的所有序列`ProductID`s 和一个名为的计算的值`HalfPrice`。</span><span class="sxs-lookup"><span data-stu-id="9dcf9-112">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="9dcf9-113">此值设置为 `UnitPrice` 的 1/2。</span><span class="sxs-lookup"><span data-stu-id="9dcf9-113">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="9dcf9-114">示例</span><span class="sxs-lookup"><span data-stu-id="9dcf9-114">Example</span></span>  
 <span data-ttu-id="9dcf9-115">下面的示例使用`Select`中的子句[!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)](`select` C# 中的子句) 和一个*条件语句*返回一系列产品名称和产品可用性。</span><span class="sxs-lookup"><span data-stu-id="9dcf9-115">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="9dcf9-116">示例</span><span class="sxs-lookup"><span data-stu-id="9dcf9-116">Example</span></span>  
 <span data-ttu-id="9dcf9-117">下面的示例使用[!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]`Select`子句 (`select` C# 中的子句) 和一个*已知类型*（名称） 可返回雇员的姓名的序列。</span><span class="sxs-lookup"><span data-stu-id="9dcf9-117">The following example uses a [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="9dcf9-118">示例</span><span class="sxs-lookup"><span data-stu-id="9dcf9-118">Example</span></span>  
 <span data-ttu-id="9dcf9-119">下面的示例使用`Select`和`Where`中[!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)](`select`和`where`C# 中) 返回*筛选序列*的位于伦敦的客户的联系人姓名。</span><span class="sxs-lookup"><span data-stu-id="9dcf9-119">The following example uses `Select` and `Where` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="9dcf9-120">示例</span><span class="sxs-lookup"><span data-stu-id="9dcf9-120">Example</span></span>  
 <span data-ttu-id="9dcf9-121">下面的示例使用`Select`中的子句[!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)](`select` C# 中的子句) 和*匿名类型*返回*成形子集*的有关客户的数据。</span><span class="sxs-lookup"><span data-stu-id="9dcf9-121">The following example uses a `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="9dcf9-122">示例</span><span class="sxs-lookup"><span data-stu-id="9dcf9-122">Example</span></span>  
 <span data-ttu-id="9dcf9-123">下面的示例使用嵌套查询返回以下结果：</span><span class="sxs-lookup"><span data-stu-id="9dcf9-123">The following example uses nested queries to return the following results:</span></span>  
  
-   <span data-ttu-id="9dcf9-124">由所有订单及其对应的 `OrderID` 组成的序列。</span><span class="sxs-lookup"><span data-stu-id="9dcf9-124">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
-   <span data-ttu-id="9dcf9-125">由订单中具有折扣的项组成的子序列。</span><span class="sxs-lookup"><span data-stu-id="9dcf9-125">A subsequence of the items in the order for which there is a discount.</span></span>  
  
-   <span data-ttu-id="9dcf9-126">不含运费时节省的资金数额。</span><span class="sxs-lookup"><span data-stu-id="9dcf9-126">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="9dcf9-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="9dcf9-127">See Also</span></span>  
 [<span data-ttu-id="9dcf9-128">查询示例</span><span class="sxs-lookup"><span data-stu-id="9dcf9-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
