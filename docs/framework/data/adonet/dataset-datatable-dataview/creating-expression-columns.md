---
title: 创建表达式列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: 6e19e4e7cc0ea92e9d93e45c2a50d009e46b78c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175495"
---
# <a name="creating-expression-columns"></a><span data-ttu-id="8301d-102">创建表达式列</span><span class="sxs-lookup"><span data-stu-id="8301d-102">Creating Expression Columns</span></span>
<span data-ttu-id="8301d-103">您可以为列定义表达式，让它能够包含根据同一行中其他列值或根据表中多行的列值计算而得的值。</span><span class="sxs-lookup"><span data-stu-id="8301d-103">You can define an expression for a column, enabling it to contain a value calculated from other column values in the same row or from the column values of multiple rows in the table.</span></span> <span data-ttu-id="8301d-104">要定义要计算的表达式，可使用目标列的 <xref:System.Data.DataColumn.Expression%2A> 属性，并使用 <xref:System.Data.DataColumn.ColumnName%2A> 属性在表达式中引用其他列。</span><span class="sxs-lookup"><span data-stu-id="8301d-104">To define the expression to be evaluated, use the <xref:System.Data.DataColumn.Expression%2A> property of the target column, and use the <xref:System.Data.DataColumn.ColumnName%2A> property to refer to other columns in the expression.</span></span> <span data-ttu-id="8301d-105">用于表达式列的 <xref:System.Data.DataColumn.DataType%2A> 必须适合于表达式将返回的值。</span><span class="sxs-lookup"><span data-stu-id="8301d-105">The <xref:System.Data.DataColumn.DataType%2A> for the expression column must be appropriate for the value that the expression returns.</span></span>  
  
 <span data-ttu-id="8301d-106">下表列出了表中表达式列的几种可能用法。</span><span class="sxs-lookup"><span data-stu-id="8301d-106">The following table lists several possible uses for expression columns in a table.</span></span>  
  
|<span data-ttu-id="8301d-107">表达式类型</span><span class="sxs-lookup"><span data-stu-id="8301d-107">Expression type</span></span>|<span data-ttu-id="8301d-108">示例</span><span class="sxs-lookup"><span data-stu-id="8301d-108">Example</span></span>|  
|---------------------|-------------|  
|<span data-ttu-id="8301d-109">比较</span><span class="sxs-lookup"><span data-stu-id="8301d-109">Comparison</span></span>|<span data-ttu-id="8301d-110">"总 > = 500"</span><span class="sxs-lookup"><span data-stu-id="8301d-110">"Total >= 500"</span></span>|  
|<span data-ttu-id="8301d-111">计算</span><span class="sxs-lookup"><span data-stu-id="8301d-111">Computation</span></span>|<span data-ttu-id="8301d-112">"UnitPrice \* Quantity"</span><span class="sxs-lookup"><span data-stu-id="8301d-112">"UnitPrice \* Quantity"</span></span>|  
|<span data-ttu-id="8301d-113">聚合</span><span class="sxs-lookup"><span data-stu-id="8301d-113">Aggregation</span></span>|<span data-ttu-id="8301d-114">Sum(Price)</span><span class="sxs-lookup"><span data-stu-id="8301d-114">Sum(Price)</span></span>|  
  
 <span data-ttu-id="8301d-115">可以设置**表达式**上的现有属性**DataColumn**对象，或者您可以将该属性用作第三个参数传递给<xref:System.Data.DataColumn>构造函数，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="8301d-115">You can set the **Expression** property on an existing **DataColumn** object, or you can include the property as the third argument passed to the <xref:System.Data.DataColumn> constructor, as shown in the following example.</span></span>  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 <span data-ttu-id="8301d-116">表达式可以引用其他表达式列，但循环引用（其中两个表达式相互引用）将产生异常。</span><span class="sxs-lookup"><span data-stu-id="8301d-116">Expressions can reference other expression columns; however, a circular reference, in which two expressions reference each other, will generate an exception.</span></span> <span data-ttu-id="8301d-117">有关编写表达式的规则，请参阅<xref:System.Data.DataColumn.Expression%2A>的属性**DataColumn**类。</span><span class="sxs-lookup"><span data-stu-id="8301d-117">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8301d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="8301d-118">See also</span></span>

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="8301d-119">数据表架构定义</span><span class="sxs-lookup"><span data-stu-id="8301d-119">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [<span data-ttu-id="8301d-120">数据表</span><span class="sxs-lookup"><span data-stu-id="8301d-120">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="8301d-121">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="8301d-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
