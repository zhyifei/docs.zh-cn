---
title: "添加 DataRelation"
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
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 9741f44b68e1cac8c464338f556979d682d9e128
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="adding-datarelations"></a><span data-ttu-id="01af6-102">添加 DataRelation</span><span class="sxs-lookup"><span data-stu-id="01af6-102">Adding DataRelations</span></span>
<span data-ttu-id="01af6-103">在包含多个 <xref:System.Data.DataSet> 对象的 <xref:System.Data.DataTable> 中，可以使用 <xref:System.Data.DataRelation> 对象来使一个表与另一个表相关，在多个表之间导航，以及从相关表中返回子行或父行。</span><span class="sxs-lookup"><span data-stu-id="01af6-103">In a <xref:System.Data.DataSet> with multiple <xref:System.Data.DataTable> objects, you can use <xref:System.Data.DataRelation> objects to relate one table to another, to navigate through the tables, and to return child or parent rows from a related table.</span></span>  
  
 <span data-ttu-id="01af6-104">若要创建所需的参数**DataRelation**是一个名为**DataRelation**正在创建，并且一个或多个数组<xref:System.Data.DataColumn>对充当父和子列的引用对关系中的列。</span><span class="sxs-lookup"><span data-stu-id="01af6-104">The arguments required to create a **DataRelation** are a name for the **DataRelation** being created, and an array of one or more <xref:System.Data.DataColumn> references to the columns that serve as the parent and child columns in the relationship.</span></span> <span data-ttu-id="01af6-105">创建后**DataRelation**，您可以使用它，表之间导航，并检索值。</span><span class="sxs-lookup"><span data-stu-id="01af6-105">After you have created a **DataRelation**, you can use it to navigate between tables and to retrieve values.</span></span>  
  
 <span data-ttu-id="01af6-106">添加**DataRelation**到<xref:System.Data.DataSet>添加时，默认情况下，<xref:System.Data.UniqueConstraint>到父表和<xref:System.Data.ForeignKeyConstraint>到子表。</span><span class="sxs-lookup"><span data-stu-id="01af6-106">Adding a **DataRelation** to a <xref:System.Data.DataSet> adds, by default, a <xref:System.Data.UniqueConstraint> to the parent table and a <xref:System.Data.ForeignKeyConstraint> to the child table.</span></span> <span data-ttu-id="01af6-107">有关这些默认约束的详细信息，请参阅[数据表约束](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)。</span><span class="sxs-lookup"><span data-stu-id="01af6-107">For more information about these default constraints, see [DataTable Constraints](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="01af6-108">下面的代码示例创建**DataRelation**使用两个<xref:System.Data.DataTable>中的对象<xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="01af6-108">The following code example creates a **DataRelation** using two <xref:System.Data.DataTable> objects in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="01af6-109">每个<xref:System.Data.DataTable>包含一个名为列**CustID**，它用作这两者之间的链接<xref:System.Data.DataTable>对象。</span><span class="sxs-lookup"><span data-stu-id="01af6-109">Each <xref:System.Data.DataTable> contains a column named **CustID**, which serves as a link between the two <xref:System.Data.DataTable> objects.</span></span> <span data-ttu-id="01af6-110">该示例将添加一个**DataRelation**到**关系**集合<xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="01af6-110">The example adds a single **DataRelation** to the **Relations** collection of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="01af6-111">在示例中的第一个参数指定的名称**DataRelation**正在创建。</span><span class="sxs-lookup"><span data-stu-id="01af6-111">The first argument in the example specifies the name of the **DataRelation** being created.</span></span> <span data-ttu-id="01af6-112">第二个参数设置父**DataColumn** ，第三个参数设置子**DataColumn**。</span><span class="sxs-lookup"><span data-stu-id="01af6-112">The second argument sets the parent **DataColumn** and the third argument sets the child **DataColumn**.</span></span>  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 <span data-ttu-id="01af6-113">A **DataRelation**还有**嵌套**属性，当设置为**true**，使行从子表嵌套在来自父表的关联行在使用的 XML 元素作为写入时<xref:System.Data.DataSet.WriteXml%2A>。</span><span class="sxs-lookup"><span data-stu-id="01af6-113">A **DataRelation** also has a **Nested** property which, when set to **true**, causes the rows from the child table to be nested within the associated row from the parent table when written as XML elements using <xref:System.Data.DataSet.WriteXml%2A> .</span></span> <span data-ttu-id="01af6-114">有关详细信息，请参阅[在数据集中使用 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)。</span><span class="sxs-lookup"><span data-stu-id="01af6-114">For more information, see [Using XML in a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01af6-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="01af6-115">See Also</span></span>  
 [<span data-ttu-id="01af6-116">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="01af6-116">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="01af6-117">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="01af6-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
