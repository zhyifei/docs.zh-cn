---
title: 导航 DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: 1819d468d12c03ce0c4faac11f4b20b8fe0f9c33
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43805684"
---
# <a name="navigating-datarelations"></a><span data-ttu-id="79a65-102">导航 DataRelation</span><span class="sxs-lookup"><span data-stu-id="79a65-102">Navigating DataRelations</span></span>
<span data-ttu-id="79a65-103"><xref:System.Data.DataRelation> 的一项主要功能就是在 <xref:System.Data.DataTable> 中从一个 <xref:System.Data.DataSet> 浏览到另一个。</span><span class="sxs-lookup"><span data-stu-id="79a65-103">One of the primary functions of a <xref:System.Data.DataRelation> is to allow navigation from one <xref:System.Data.DataTable> to another within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="79a65-104">这使您可以检索所有相关<xref:System.Data.DataRow>中一个对象**DataTable**如果给定的单个**DataRow**从相关**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="79a65-104">This allows you to retrieve all the related <xref:System.Data.DataRow> objects in one **DataTable** when given a single **DataRow** from a related **DataTable**.</span></span> <span data-ttu-id="79a65-105">例如，在建立**DataRelation**之间的客户表和 orders 的表，可以检索有关特定客户行使用的所有订单行**GetChildRows**。</span><span class="sxs-lookup"><span data-stu-id="79a65-105">For example, after establishing a **DataRelation** between a table of customers and a table of orders, you can retrieve all the order rows for a particular customer row using **GetChildRows**.</span></span>  
  
 <span data-ttu-id="79a65-106">下面的代码示例将创建**DataRelation**之间**客户**表和**订单**的表**数据集**，并返回每个客户的所有订单。</span><span class="sxs-lookup"><span data-stu-id="79a65-106">The following code example creates a **DataRelation** between the **Customers** table and the **Orders** table of a **DataSet** and returns all the orders for each customer.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 <span data-ttu-id="79a65-107">下一示例以上例为基础，将四个表关联在一起，并浏览这些关系。</span><span class="sxs-lookup"><span data-stu-id="79a65-107">The next example builds on the preceding example, relating four tables together and navigating those relationships.</span></span> <span data-ttu-id="79a65-108">如前面的示例中所示**CustomerID**相关**客户**表**订单**表。</span><span class="sxs-lookup"><span data-stu-id="79a65-108">As in the previous example, **CustomerID** relates the **Customers** table to the **Orders** table.</span></span> <span data-ttu-id="79a65-109">对于中的每个客户**客户**表中的所有子行**订单**取决于都表，以便返回特定客户的订单数以及它们**OrderID**值。</span><span class="sxs-lookup"><span data-stu-id="79a65-109">For each customer in the **Customers** table, all the child rows in the **Orders** table are determined, in order to return the number of orders a particular customer has and their **OrderID** values.</span></span>  
  
 <span data-ttu-id="79a65-110">扩展的示例还将返回的值从**OrderDetails**并**产品**表。</span><span class="sxs-lookup"><span data-stu-id="79a65-110">The expanded example also returns the values from the **OrderDetails** and **Products** tables.</span></span> <span data-ttu-id="79a65-111">**订单**表与相关**OrderDetails**表可使用**OrderID**来确定每个客户订单的产品及数量进行排序。</span><span class="sxs-lookup"><span data-stu-id="79a65-111">The **Orders** table is related to the **OrderDetails** table using **OrderID** to determine, for each customer order, what products and quantities were ordered.</span></span> <span data-ttu-id="79a65-112">因为**OrderDetails**表仅包含**ProductID**已订购产品， **OrderDetails**与相关**产品**使用**ProductID**为了返回**ProductName**。</span><span class="sxs-lookup"><span data-stu-id="79a65-112">Because the **OrderDetails** table only contains the **ProductID** of an ordered product, **OrderDetails** is related to **Products** using **ProductID** in order to return the **ProductName**.</span></span> <span data-ttu-id="79a65-113">在这一关系，**产品**表为父表和**订单详细信息**表为子表。</span><span class="sxs-lookup"><span data-stu-id="79a65-113">In this relation, the **Products** table is the parent and the **Order Details** table is the child.</span></span> <span data-ttu-id="79a65-114">因此，当循环访问**OrderDetails**表中， **GetParentRow**调用以检索相关**ProductName**值。</span><span class="sxs-lookup"><span data-stu-id="79a65-114">As a result, when iterating through the **OrderDetails** table, **GetParentRow** is called to retrieve the related **ProductName** value.</span></span>  
  
 <span data-ttu-id="79a65-115">请注意，当**DataRelation**为创建**客户**并**订单**表，为指定任何值**createConstraints**标志 (默认值是 **，则返回 true**)。</span><span class="sxs-lookup"><span data-stu-id="79a65-115">Notice that when the **DataRelation** is created for the **Customers** and **Orders** tables, no value is specified for the **createConstraints** flag (the default is **true**).</span></span> <span data-ttu-id="79a65-116">这假定所有中行**订单**表具有**CustomerID**存在的父代中的值**客户**表。</span><span class="sxs-lookup"><span data-stu-id="79a65-116">This assumes that all the rows in the **Orders** table have a **CustomerID** value that exists in the parent **Customers** table.</span></span> <span data-ttu-id="79a65-117">如果**CustomerID**存在于**订单**表中不存在**客户**表，<xref:System.Data.ForeignKeyConstraint>会导致引发异常。</span><span class="sxs-lookup"><span data-stu-id="79a65-117">If a **CustomerID** exists in the **Orders** table that does not exist in the **Customers** table, a <xref:System.Data.ForeignKeyConstraint> causes an exception to be thrown.</span></span>  
  
 <span data-ttu-id="79a65-118">当子列可能包含父列不包含的值时，设置**createConstraints**标记，用于**false**添加时**DataRelation**。</span><span class="sxs-lookup"><span data-stu-id="79a65-118">When the child column might contain values that the parent column does not contain, set the **createConstraints** flag to **false** when adding the **DataRelation**.</span></span> <span data-ttu-id="79a65-119">在示例中， **createConstraints**标志设置为**false**有关**DataRelation**之间**订单**表和**OrderDetails**表。</span><span class="sxs-lookup"><span data-stu-id="79a65-119">In the example, the **createConstraints** flag is set to **false** for the **DataRelation** between the **Orders** table and the **OrderDetails** table.</span></span> <span data-ttu-id="79a65-120">这使应用程序返回中的所有记录**OrderDetails**表，并仅从记录的子集**订单**表而不会生成运行时异常。</span><span class="sxs-lookup"><span data-stu-id="79a65-120">This enables the application to return all the records from the **OrderDetails** table and only a subset of records from the **Orders** table without generating a run-time exception.</span></span> <span data-ttu-id="79a65-121">该扩展示例生成以下格式的输出。</span><span class="sxs-lookup"><span data-stu-id="79a65-121">The expanded sample generates output in the following format.</span></span>  
  
```  
Customer ID: NORTS  
  Order ID: 10517  
        Order Date: 4/24/1997 12:00:00 AM  
           Product: Filo Mix  
          Quantity: 6  
           Product: Raclette Courdavault  
          Quantity: 4  
           Product: Outback Lager  
          Quantity: 6  
  Order ID: 11057  
        Order Date: 4/29/1998 12:00:00 AM  
           Product: Outback Lager  
          Quantity: 3  
```  
  
 <span data-ttu-id="79a65-122">下面的代码示例是一个扩展的示例位置中的值**OrderDetails**并**产品**返回表，使用中的记录的一个子集**订单**返回的表。</span><span class="sxs-lookup"><span data-stu-id="79a65-122">The following code example is an expanded sample where the values from the **OrderDetails** and **Products** tables are returned, with only a subset of the records in the **Orders** table being returned.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="79a65-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="79a65-123">See Also</span></span>  
 [<span data-ttu-id="79a65-124">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="79a65-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="79a65-125">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="79a65-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
