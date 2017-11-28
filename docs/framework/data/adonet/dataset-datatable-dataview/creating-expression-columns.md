---
title: "创建表达式列"
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
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 315944262136e5db453ea01eae64fff6cb0d534d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="creating-expression-columns"></a><span data-ttu-id="697a0-102">创建表达式列</span><span class="sxs-lookup"><span data-stu-id="697a0-102">Creating Expression Columns</span></span>
<span data-ttu-id="697a0-103">您可以为列定义表达式，让它能够包含根据同一行中其他列值或根据表中多行的列值计算而得的值。</span><span class="sxs-lookup"><span data-stu-id="697a0-103">You can define an expression for a column, enabling it to contain a value calculated from other column values in the same row or from the column values of multiple rows in the table.</span></span> <span data-ttu-id="697a0-104">要定义要计算的表达式，可使用目标列的 <xref:System.Data.DataColumn.Expression%2A> 属性，并使用 <xref:System.Data.DataColumn.ColumnName%2A> 属性在表达式中引用其他列。</span><span class="sxs-lookup"><span data-stu-id="697a0-104">To define the expression to be evaluated, use the <xref:System.Data.DataColumn.Expression%2A> property of the target column, and use the <xref:System.Data.DataColumn.ColumnName%2A> property to refer to other columns in the expression.</span></span> <span data-ttu-id="697a0-105">用于表达式列的 <xref:System.Data.DataColumn.DataType%2A> 必须适合于表达式将返回的值。</span><span class="sxs-lookup"><span data-stu-id="697a0-105">The <xref:System.Data.DataColumn.DataType%2A> for the expression column must be appropriate for the value that the expression returns.</span></span>  
  
 <span data-ttu-id="697a0-106">下表列出了表中表达式列的几种可能用法。</span><span class="sxs-lookup"><span data-stu-id="697a0-106">The following table lists several possible uses for expression columns in a table.</span></span>  
  
|<span data-ttu-id="697a0-107">表达式类型</span><span class="sxs-lookup"><span data-stu-id="697a0-107">Expression type</span></span>|<span data-ttu-id="697a0-108">示例</span><span class="sxs-lookup"><span data-stu-id="697a0-108">Example</span></span>|  
|---------------------|-------------|  
|<span data-ttu-id="697a0-109">比较</span><span class="sxs-lookup"><span data-stu-id="697a0-109">Comparison</span></span>|<span data-ttu-id="697a0-110">"Total >= 500"</span><span class="sxs-lookup"><span data-stu-id="697a0-110">"Total >= 500"</span></span>|  
|<span data-ttu-id="697a0-111">计算</span><span class="sxs-lookup"><span data-stu-id="697a0-111">Computation</span></span>|<span data-ttu-id="697a0-112">"UnitPrice * Quantity"</span><span class="sxs-lookup"><span data-stu-id="697a0-112">"UnitPrice * Quantity"</span></span>|  
|<span data-ttu-id="697a0-113">聚合</span><span class="sxs-lookup"><span data-stu-id="697a0-113">Aggregation</span></span>|<span data-ttu-id="697a0-114">Sum(Price)</span><span class="sxs-lookup"><span data-stu-id="697a0-114">Sum(Price)</span></span>|  
  
 <span data-ttu-id="697a0-115">你可以设置**表达式**在现有的属性**DataColumn**对象，也可以将该属性用作第三个自变量传递给<xref:System.Data.DataColumn>构造函数，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="697a0-115">You can set the **Expression** property on an existing **DataColumn** object, or you can include the property as the third argument passed to the <xref:System.Data.DataColumn> constructor, as shown in the following example.</span></span>  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 <span data-ttu-id="697a0-116">表达式可以引用其他表达式列，但循环引用（其中两个表达式相互引用）将产生异常。</span><span class="sxs-lookup"><span data-stu-id="697a0-116">Expressions can reference other expression columns; however, a circular reference, in which two expressions reference each other, will generate an exception.</span></span> <span data-ttu-id="697a0-117">有关编写表达式的规则，请参阅<xref:System.Data.DataColumn.Expression%2A>属性**DataColumn**类。</span><span class="sxs-lookup"><span data-stu-id="697a0-117">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="697a0-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="697a0-118">See Also</span></span>  
 <xref:System.Data.DataColumn>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="697a0-119">数据表架构定义</span><span class="sxs-lookup"><span data-stu-id="697a0-119">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="697a0-120">数据表</span><span class="sxs-lookup"><span data-stu-id="697a0-120">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="697a0-121">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="697a0-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
