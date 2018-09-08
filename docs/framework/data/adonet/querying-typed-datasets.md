---
title: 查询类型化数据集
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: d956fd5f07c108146d20623bcf811266380c132c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44200940"
---
# <a name="query-typed-datasets"></a><span data-ttu-id="45278-102">查询类型化数据集</span><span class="sxs-lookup"><span data-stu-id="45278-102">Query typed DataSets</span></span>

<span data-ttu-id="45278-103">如果的架构<xref:System.Data.DataSet>在应用程序设计时已知，我们建议你使用类型化<xref:System.Data.DataSet>时使用 LINQ to DataSet。</span><span class="sxs-lookup"><span data-stu-id="45278-103">If the schema of the <xref:System.Data.DataSet> is known at application design time, we recommend that you use a typed <xref:System.Data.DataSet> when using LINQ to DataSet.</span></span> <span data-ttu-id="45278-104">类型化 <xref:System.Data.DataSet> 是从 <xref:System.Data.DataSet> 中派生的类。</span><span class="sxs-lookup"><span data-stu-id="45278-104">A typed <xref:System.Data.DataSet> is a class that derives from a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="45278-105">因此，它继承 <xref:System.Data.DataSet> 的所有方法、事件和属性。</span><span class="sxs-lookup"><span data-stu-id="45278-105">As such, it inherits all the methods, events, and properties of a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="45278-106">此外，类型化 <xref:System.Data.DataSet> 还提供强类型方法、事件和属性。</span><span class="sxs-lookup"><span data-stu-id="45278-106">Additionally, a typed <xref:System.Data.DataSet> provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="45278-107">这意味着可以按名称而不使用基于集合的方法来访问表和列。</span><span class="sxs-lookup"><span data-stu-id="45278-107">This means that you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="45278-108">这可使查询更简单、更具可读性。</span><span class="sxs-lookup"><span data-stu-id="45278-108">This makes queries simpler and more readable.</span></span> <span data-ttu-id="45278-109">有关详细信息，请参阅[类型化数据集](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)。</span><span class="sxs-lookup"><span data-stu-id="45278-109">For more information, see [Typed DataSets](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>

<span data-ttu-id="45278-110">LINQ to DataSet 还支持对类型化查询<xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="45278-110">LINQ to DataSet also supports querying over a typed <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="45278-111">对于类型化 <xref:System.Data.DataSet>，您不必使用泛型 <xref:System.Data.DataRowExtensions.Field%2A> 方法或 <xref:System.Data.DataRowExtensions.SetField%2A> 方法即可访问列数据。</span><span class="sxs-lookup"><span data-stu-id="45278-111">With a typed <xref:System.Data.DataSet>, you do not have to use the generic <xref:System.Data.DataRowExtensions.Field%2A> method or <xref:System.Data.DataRowExtensions.SetField%2A> method to access column data.</span></span> <span data-ttu-id="45278-112">由于 <xref:System.Data.DataSet> 中包括类型信息，因此属性名称在编译时可用。</span><span class="sxs-lookup"><span data-stu-id="45278-112">Property names are available at compile time because the type information is included in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="45278-113">LINQ 到数据集作为正确类型，提供到列的值的访问，以便在编译代码而不是在运行时捕获类型不匹配错误。</span><span class="sxs-lookup"><span data-stu-id="45278-113">LINQ to DataSet provides access to column values as the correct type, so that type mismatch errors are caught when the code is compiled instead of at run time.</span></span>

<span data-ttu-id="45278-114">你可以开始查询类型化之前<xref:System.Data.DataSet>，必须通过使用生成该类**数据集设计器**Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="45278-114">Before you can begin querying a typed <xref:System.Data.DataSet>, you must generate the class by using the **DataSet Designer** in Visual Studio.</span></span> <span data-ttu-id="45278-115">有关详细信息，请参阅[创建和配置数据集](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="45278-115">For more information, see [Create and configure DataSets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span></span>

## <a name="example"></a><span data-ttu-id="45278-116">示例</span><span class="sxs-lookup"><span data-stu-id="45278-116">Example</span></span>

<span data-ttu-id="45278-117">下面的示例演示对类型化 <xref:System.Data.DataSet> 进行查询：</span><span class="sxs-lookup"><span data-stu-id="45278-117">The following example shows a query over a typed <xref:System.Data.DataSet>:</span></span>

```csharp
var query = from o in orders
            where o.OnlineOrderFlag == true
            select new { o.SalesOrderID,
                         o.OrderDate,
                         o.SalesOrderNumber };

foreach(var order in query)
{
    Console.WriteLine("{0}\t{1:d}\t{2}",
      order.SalesOrderID,
      order.OrderDate,
      order.SalesOrderNumber);
}
```

```vb
Dim orders = ds.Tables("SalesOrderHeader")

Dim query = _
       From o In orders _
       Where o.OnlineOrderFlag = True _
       Select New {SalesOrderID := o.SalesOrderID, _
                   OrderDate := o.OrderDate, _
                   SalesOrderNumber := o.SalesOrderNumber}

For Each Dim onlineOrder In query
 Console.WriteLine("{0}\t{1:d}\t{2}", _
 onlineOrder.SalesOrderID, _
 onlineOrder.OrderDate, _
 onlineOrder.SalesOrderNumber)
Next
```

## <a name="see-also"></a><span data-ttu-id="45278-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="45278-118">See also</span></span>

- [<span data-ttu-id="45278-119">查询数据集</span><span class="sxs-lookup"><span data-stu-id="45278-119">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="45278-120">跨表查询</span><span class="sxs-lookup"><span data-stu-id="45278-120">Cross-Table Queries</span></span>](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)
- [<span data-ttu-id="45278-121">单表查询</span><span class="sxs-lookup"><span data-stu-id="45278-121">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
