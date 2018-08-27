---
title: 使用组合键进行联接（C# 中的 LINQ）
description: 了解如何在 LINQ 中使用组合键进行联接。
ms.date: 12/1/2016
ms.assetid: da70b54d-3213-45eb-8437-fbe75cbcf935
ms.openlocfilehash: ae37d03f996f0b0cc184a86663f16d62e6c29c69
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932329"
---
# <a name="join-by-using-composite-keys"></a><span data-ttu-id="b58c2-103">使用组合键进行联接</span><span class="sxs-lookup"><span data-stu-id="b58c2-103">Join by using composite keys</span></span>

<span data-ttu-id="b58c2-104">此示例演示如何执行想要使用多个键来定义匹配的联接操作。</span><span class="sxs-lookup"><span data-stu-id="b58c2-104">This example shows how to perform join operations in which you want to use more than one key to define a match.</span></span> <span data-ttu-id="b58c2-105">使用组合键来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="b58c2-105">This is accomplished by using a composite key.</span></span> <span data-ttu-id="b58c2-106">以匿名类型或包含要比较值的命名类型的形式来创建组合键。</span><span class="sxs-lookup"><span data-stu-id="b58c2-106">You create a composite key as an anonymous type or named typed with the values that you want to compare.</span></span> <span data-ttu-id="b58c2-107">若要跨方法边界传递查询变量，请为该键使用重写 <xref:System.Object.Equals%2A> 和 <xref:System.Object.GetHashCode%2A> 的命名类型。</span><span class="sxs-lookup"><span data-stu-id="b58c2-107">If the query variable will be passed across method boundaries, use a named type that overrides <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> for the key.</span></span> <span data-ttu-id="b58c2-108">属性的名称以及属性出现的顺序在每个键中必须相同。</span><span class="sxs-lookup"><span data-stu-id="b58c2-108">The names of the properties, and the order in which they occur, must be identical in each key.</span></span>

## <a name="example"></a><span data-ttu-id="b58c2-109">示例</span><span class="sxs-lookup"><span data-stu-id="b58c2-109">Example</span></span>

<span data-ttu-id="b58c2-110">以下示例演示如何使用组合键联接 3 个表中的数据：</span><span class="sxs-lookup"><span data-stu-id="b58c2-110">The following example demonstrates how to use a composite key to join data from three tables:</span></span>

```csharp
var query = from o in db.Orders
    from p in db.Products
    join d in db.OrderDetails
        on new {o.OrderID, p.ProductID} equals new {d.OrderID, d.ProductID} into details
        from d in details
        select new {o.OrderID, p.ProductID, d.UnitPrice};
```

<span data-ttu-id="b58c2-111">组合键上的类型推理取决于这些键中属性的名称，以及属性出现的顺序。</span><span class="sxs-lookup"><span data-stu-id="b58c2-111">Type inference on composite keys depends on the names of the properties in the keys, and the order in which they occur.</span></span> <span data-ttu-id="b58c2-112">如果源序列中属性的名称不同，则必须在键中分配新名称。</span><span class="sxs-lookup"><span data-stu-id="b58c2-112">If the properties in the source sequences don't have the same names, you must assign new names in the keys.</span></span> <span data-ttu-id="b58c2-113">例如，如果 `Orders` 表和 `OrderDetails` 表为各自的列分别使用不同的名称，则可通过在匿名类型中分配相同的名称来创建组合键：</span><span class="sxs-lookup"><span data-stu-id="b58c2-113">For example, if the `Orders` table and `OrderDetails` table each used different names for their columns, you could create composite keys by assigning identical names in the anonymous types:</span></span>

```csharp
join...on new {Name = o.CustomerName, ID = o.CustID} equals
    new {Name = d.CustName, ID = d.CustID }
```

<span data-ttu-id="b58c2-114">还可以在 `group` 子句中使用组合键。</span><span class="sxs-lookup"><span data-stu-id="b58c2-114">Composite keys can be also used in a `group` clause.</span></span>

## <a name="see-also"></a><span data-ttu-id="b58c2-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="b58c2-115">See also</span></span>

- [<span data-ttu-id="b58c2-116">语言集成查询 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="b58c2-116">Language Integrated Query (LINQ)</span></span>](index.md)  
- [<span data-ttu-id="b58c2-117">join 子句</span><span class="sxs-lookup"><span data-stu-id="b58c2-117">join clause</span></span>](../language-reference/keywords/join-clause.md)  
- [<span data-ttu-id="b58c2-118">group 子句</span><span class="sxs-lookup"><span data-stu-id="b58c2-118">group clause</span></span>](../language-reference/keywords/group-clause.md)  