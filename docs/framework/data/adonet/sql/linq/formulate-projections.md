---
title: 构建投影
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: 0dfd5d951750de2ab918c51dd9f4f2deeb8a6318
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793829"
---
# <a name="formulate-projections"></a><span data-ttu-id="c14a7-102">构建投影</span><span class="sxs-lookup"><span data-stu-id="c14a7-102">Formulate Projections</span></span>
<span data-ttu-id="c14a7-103">下面的示例演示如何将`select`中的C#和`Select` Visual Basic 语句中的语句与其他功能组合起来以形成查询投影。</span><span class="sxs-lookup"><span data-stu-id="c14a7-103">The following examples show how the `select` statement in C# and `Select` statement in Visual Basic can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c14a7-104">示例</span><span class="sxs-lookup"><span data-stu-id="c14a7-104">Example</span></span>  
 <span data-ttu-id="c14a7-105">下面的示例使用中`Select` `select` C#Visual Basic （子句）中的子句来`Customers`返回的联系人名称序列。</span><span class="sxs-lookup"><span data-stu-id="c14a7-105">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="c14a7-106">示例</span><span class="sxs-lookup"><span data-stu-id="c14a7-106">Example</span></span>  
 <span data-ttu-id="c14a7-107">下面的示例使用 Visual Basic `Select` （`select`中C#的子句）和*匿名类型*中的子句来返回的联系人姓名和电话号码`Customers`序列。</span><span class="sxs-lookup"><span data-stu-id="c14a7-107">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="c14a7-108">示例</span><span class="sxs-lookup"><span data-stu-id="c14a7-108">Example</span></span>  
 <span data-ttu-id="c14a7-109">下面的示例使用 Visual Basic `Select` （`select`中C#的子句）和*匿名类型*中的子句来返回雇员的姓名和电话号码序列。</span><span class="sxs-lookup"><span data-stu-id="c14a7-109">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="c14a7-110">在产生的序列中，`FirstName` 和 `LastName` 字段组合成单个字段 (`Name`)，`HomePhone` 字段重命名为 `Phone`。</span><span class="sxs-lookup"><span data-stu-id="c14a7-110">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="c14a7-111">示例</span><span class="sxs-lookup"><span data-stu-id="c14a7-111">Example</span></span>  
 <span data-ttu-id="c14a7-112">下面的示例使用中`Select` Visual Basic （`select`子句中C#的子句）和*匿名类型*中的子句来返回所有`ProductID`和名为`HalfPrice`的计算值的序列。</span><span class="sxs-lookup"><span data-stu-id="c14a7-112">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="c14a7-113">此值设置为 `UnitPrice` 的 1/2。</span><span class="sxs-lookup"><span data-stu-id="c14a7-113">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="c14a7-114">示例</span><span class="sxs-lookup"><span data-stu-id="c14a7-114">Example</span></span>  
 <span data-ttu-id="c14a7-115">下面的示例使用 Visual Basic `Select` （`select`中C#的子句）和一个*条件语句*中的子句来返回产品名称和产品可用性序列。</span><span class="sxs-lookup"><span data-stu-id="c14a7-115">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="c14a7-116">示例</span><span class="sxs-lookup"><span data-stu-id="c14a7-116">Example</span></span>  
 <span data-ttu-id="c14a7-117">下面的`Select`示例使用 Visual Basic 子句（`select` in 中C#的子句）和一个*已知类型*（Name）返回雇员姓名的序列。</span><span class="sxs-lookup"><span data-stu-id="c14a7-117">The following example uses a Visual Basic `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="c14a7-118">示例</span><span class="sxs-lookup"><span data-stu-id="c14a7-118">Example</span></span>  
 <span data-ttu-id="c14a7-119">下面的示例在`Select` Visual Basic `Where` （`select` `where`和中C#）使用和，以返回伦敦的客户的联系人姓名的*筛选序列*。</span><span class="sxs-lookup"><span data-stu-id="c14a7-119">The following example uses `Select` and `Where` in Visual Basic (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="c14a7-120">示例</span><span class="sxs-lookup"><span data-stu-id="c14a7-120">Example</span></span>  
 <span data-ttu-id="c14a7-121">下面的示例在的`Select` `select` C#Visual Basic （子句）和*匿名类型*中使用子句来返回有关客户的数据的*形状子集*。</span><span class="sxs-lookup"><span data-stu-id="c14a7-121">The following example uses a `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="c14a7-122">示例</span><span class="sxs-lookup"><span data-stu-id="c14a7-122">Example</span></span>  
 <span data-ttu-id="c14a7-123">下面的示例使用嵌套查询返回以下结果：</span><span class="sxs-lookup"><span data-stu-id="c14a7-123">The following example uses nested queries to return the following results:</span></span>  
  
- <span data-ttu-id="c14a7-124">由所有订单及其对应的 `OrderID` 组成的序列。</span><span class="sxs-lookup"><span data-stu-id="c14a7-124">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
- <span data-ttu-id="c14a7-125">由订单中具有折扣的项组成的子序列。</span><span class="sxs-lookup"><span data-stu-id="c14a7-125">A subsequence of the items in the order for which there is a discount.</span></span>  
  
- <span data-ttu-id="c14a7-126">不含运费时节省的资金数额。</span><span class="sxs-lookup"><span data-stu-id="c14a7-126">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="c14a7-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="c14a7-127">See also</span></span>

- [<span data-ttu-id="c14a7-128">查询示例</span><span class="sxs-lookup"><span data-stu-id="c14a7-128">Query Examples</span></span>](query-examples.md)
