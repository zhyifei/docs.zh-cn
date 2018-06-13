---
title: 查询类型化数据集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: 30a6512202615590a4b399b8ce7173b213a8873c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353480"
---
# <a name="querying-typed-datasets"></a><span data-ttu-id="b3e5c-102">查询类型化数据集</span><span class="sxs-lookup"><span data-stu-id="b3e5c-102">Querying Typed DataSets</span></span>
<span data-ttu-id="b3e5c-103">如果在应用程序设计时已知 <xref:System.Data.DataSet> 的架构，则建议在使用 <xref:System.Data.DataSet> 时使用类型化 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b3e5c-103">If the schema of the <xref:System.Data.DataSet> is known at application design time, we recommend that you use a typed <xref:System.Data.DataSet> when using [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="b3e5c-104">类型化 <xref:System.Data.DataSet> 是从 <xref:System.Data.DataSet> 中派生的类。</span><span class="sxs-lookup"><span data-stu-id="b3e5c-104">A typed <xref:System.Data.DataSet> is a class that derives from a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b3e5c-105">因此，它继承 <xref:System.Data.DataSet> 的所有方法、事件和属性。</span><span class="sxs-lookup"><span data-stu-id="b3e5c-105">As such, it inherits all the methods, events, and properties of a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b3e5c-106">此外，类型化 <xref:System.Data.DataSet> 还提供强类型方法、事件和属性。</span><span class="sxs-lookup"><span data-stu-id="b3e5c-106">Additionally, a typed <xref:System.Data.DataSet> provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="b3e5c-107">这意味着可以按名称而不使用基于集合的方法来访问表和列。</span><span class="sxs-lookup"><span data-stu-id="b3e5c-107">This means that you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="b3e5c-108">这可使查询更简单、更具可读性。</span><span class="sxs-lookup"><span data-stu-id="b3e5c-108">This makes queries simpler and more readable.</span></span> <span data-ttu-id="b3e5c-109">有关详细信息，请参阅[类型化数据集](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)。</span><span class="sxs-lookup"><span data-stu-id="b3e5c-109">For more information, see [Typed DataSets](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="b3e5c-110"> 还支持对类型化 <xref:System.Data.DataSet> 进行查询。</span><span class="sxs-lookup"><span data-stu-id="b3e5c-110"> also supports querying over a typed <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b3e5c-111">对于类型化 <xref:System.Data.DataSet>，您不必使用泛型 <xref:System.Data.DataRowExtensions.Field%2A> 方法或 <xref:System.Data.DataRowExtensions.SetField%2A> 方法即可访问列数据。</span><span class="sxs-lookup"><span data-stu-id="b3e5c-111">With a typed <xref:System.Data.DataSet>, you do not have to use the generic <xref:System.Data.DataRowExtensions.Field%2A> method or <xref:System.Data.DataRowExtensions.SetField%2A> method to access column data.</span></span>  <span data-ttu-id="b3e5c-112">由于 <xref:System.Data.DataSet> 中包括类型信息，因此属性名称在编译时可用。</span><span class="sxs-lookup"><span data-stu-id="b3e5c-112">Property names are available at compile time because the type information is included in the <xref:System.Data.DataSet>.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="b3e5c-113"> 提供对正确类型的列值的访问，以便可以在编译代码时而不是在运行时捕获类型不匹配错误。</span><span class="sxs-lookup"><span data-stu-id="b3e5c-113"> provides access to column values as the correct type, so that type mismatch errors are caught when the code is compiled instead of at run time.</span></span>  
  
 <span data-ttu-id="b3e5c-114">在可以开始查询类型化 <xref:System.Data.DataSet> 之前，必须先通过使用 [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] 中的数据集设计器生成该类。</span><span class="sxs-lookup"><span data-stu-id="b3e5c-114">Before you can begin querying a typed <xref:System.Data.DataSet>, you must generate the class by using the DataSet Designer in [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].</span></span>  <span data-ttu-id="b3e5c-115">有关详细信息，请参阅[创建和配置数据集](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="b3e5c-115">For more information, see [Create and configure datasets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3e5c-116">示例</span><span class="sxs-lookup"><span data-stu-id="b3e5c-116">Example</span></span>  
 <span data-ttu-id="b3e5c-117">下面的示例演示对类型化 <xref:System.Data.DataSet> 进行查询：</span><span class="sxs-lookup"><span data-stu-id="b3e5c-117">The following example shows a query over a typed <xref:System.Data.DataSet>:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b3e5c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="b3e5c-118">See Also</span></span>  
 [<span data-ttu-id="b3e5c-119">查询数据集</span><span class="sxs-lookup"><span data-stu-id="b3e5c-119">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [<span data-ttu-id="b3e5c-120">跨表查询</span><span class="sxs-lookup"><span data-stu-id="b3e5c-120">Cross-Table Queries</span></span>](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 [<span data-ttu-id="b3e5c-121">单表查询</span><span class="sxs-lookup"><span data-stu-id="b3e5c-121">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
